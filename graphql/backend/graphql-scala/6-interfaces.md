At this point you should know the basics, so it’s a perfect time for some hands-on training. The following paragraph will give you hints on what needs to be done. Try implementing it yourself. At the end I will add an example solution in case you are stuck. Later in this chapter we will learn about interfaces and how they relate to the work you’ve done.

### Your DIY kit

Before you go further, try to implement the changes yourself. I think, at this point, you have the necessary knowledge to add the `User` and `Vote` models. I’ll show what to do later in this chapter, but try to implement it yourself first.

What you have to do:

1.  Add `User` class with fields: `id`, `name`, `email`, `password` and `createdAt`
2.  Add `Vote` class with fields: `id`, `createdAt`, `userId`, `linkId`(you don’t have to to define any relations for now)
3.  Create database tables for both,
4.  Add object types for both,
5.  Add fetchers for both,
6.  Implement `HasId` type class,
7.  Add fields in main `ObjectType` which allows for fetching a list of entities like `users` and `votes`

Please, go ahead with your implementation … I will wait here

### User entity

Let’s start from the user entity:

Add `User.scala`class to `models` package object with the following content:

    case class User(id: Int, name: String, email: String, password: String, createdAt: DateTime = DateTime.now)

Database setup.

Add the following content to the `DBSchema` class (after `Links` definition):

    class UsersTable(tag: Tag) extends Table[User](tag, "USERS"){
      def id = column[Int]("ID", O.PrimaryKey, O.AutoInc)
      def name = column[String]("NAME")
      def email = column[String]("EMAIL")
      def password = column[String]("PASSWORD")
      def createdAt = column[DateTime]("CREATED_AT")

      def * = (id, name, email, password, createdAt).mapTo[User]
    }

    val Users = TableQuery[UsersTable]

Sample entities:

In DBSchema in the function `databaseSetup`, add an action `Users.schema.create` at beginning of the function and then add a few users later in this function:

    Users forceInsertAll Seq(
        User(1, "mario", "mario@example.com", "s3cr3t"),
        User(2, "Fred", "fred@flinstones.com", "wilmalove")
      )

Add a function responsible for user retrieval:

In `DAO` class add a function:

    def getUsers(ids: Seq[Int]): Future[Seq[User]] = {
        db.run(
          Users.filter(_.id inSet ids).result
        )
    }

Dont’ forget about `import com.howtographql.scala.sangria.models.User`…

GraphQL part:

In `GraphQLSchema` add :

    val UserType = deriveObjectType[Unit, User]() //ObjectType for user
    implicit val userHasId = HasId[User, Int](_.id) //HasId type class
    val usersFetcher = Fetcher(
        (ctx: MyContext, ids: Seq[Int]) => ctx.dao.getUsers(ids)
    )// resolver

Add fetcher to resolvers.

And lastly add the new fetcher to the resolvers list. In the same file, replace constant `Resolver` with:

    val Resolver = DeferredResolver.fetchers(linksFetcher, usersFetcher)

Add fields to main ObjectType:

Add to `QueryType.fields`:

    Field("users",
            ListType(UserType),
            arguments = List(Ids),
            resolve = c => usersFetcher.deferSeq(c.arg(Ids))
    )

We’re ready… you can now execute a query like this:

    query {
        users(ids: [1, 2]){
          id
          name
          email
          createdAt
        }
    }

### Vote entity

If you want, you can make similar changes for `Vote` entity. And then follow the instructions and check everything works.

Create `Vote` class

    case class Vote(id: Int, userId: Int, linkId: Int, createdAt: DateTime = DateTime.now)

Database setup.

Add the following content to the `DBSchema` class:

    class VotesTable(tag: Tag) extends Table[Vote](tag, "VOTES"){
        def id = column[Int]("ID", O.PrimaryKey, O.AutoInc)
        def userId = column[Int]("USER_ID")
        def linkId = column[Int]("LINK_ID")
        def createdAt = column[DateTime]("CREATED_AT")

        def * = (id, userId, linkId, createdAt).mapTo[Vote]
      }

      val Votes = TableQuery[VotesTable]

The next step is creating relations.

In file `DBSchema` in function databaseSetup: Add an action `Votes.schema.create` at beginning of the sentence and then add few users later in this function:

    Votes forceInsertAll Seq(
      Vote(id = 1, userId = 1, linkId = 1),
      Vote(id = 2, userId = 1, linkId = 2),
      Vote(id = 3, userId = 1, linkId = 3),
      Vote(id = 4, userId = 2, linkId = 2),
    )

Add votes retrieval function.

In `DAO` class add a function:

    def getVotes(ids: Seq[Int]): Future[Seq[Vote]] = {
        db.run(
          Votes.filter(_.id inSet ids).result
        )
    }

GraphQL part:

In `GraphQLSchema` add :

    implicit val VoteType = deriveObjectType[Unit, Vote]()
    implicit val voteHasId = HasId[Vote, Int](_.id)

    val votesFetcher = Fetcher(
      (ctx: MyContext, ids: Seq[Int]) => ctx.dao.getVotes(ids)
    )

Add fetcher to resolvers.

Add the new fetcher to the resolvers list. In the same file, replace constant `Resolver` with:

    val Resolver = DeferredResolver.fetchers(linksFetcher, usersFetcher, votesFetcher)

Add fields to main ObjectType:

Add to `QueryType.fields`:

    //val Ids = Argument("ids", ListInputType(IntType))
    Field("votes",
            ListType(VoteType),
            arguments = List(Ids),
            resolve = c => votesFetcher.deferSeq(c.arg(Ids))
    )

The following query should now execute successfully:

    query {
      votes(ids: [1, 2]){
        id
        createdAt
      }
    }

### Finding common parts

As you can see some code is very similar. Like `HasId` for all three types:

    implicit val linkHasId = HasId[Link, Int](_.id)
    implicit val userHasId = HasId[User, Int](_.id)
    implicit val voteHasId = HasId[Vote, Int](_.id)

What if you want to add more entities? You will have to duplicate this code.

The solution for this is an interface. We can provide an interface that will be extended by any of the entities. This way, for example, you will need just one HasId

Create trait `Identifiable` into the `models` package object:

    trait Identifiable {
      val id: Int
    }

And then extend this trait by all of those classes like:

    case class Link(...) extends Identifiable
    case class User(...) extends Identifiable
    case class Vote(...) extends Identifiable

Now we can replace all above `HasId` type classes with the single one. But now we will move it into companion object so it will be accessible whenever we import the trait.

Remove `linkHasId`, `userHasId` and `voteHasId`, and add companion object to the `Identifiable` trait:

    //add to imports:
    import sangria.execution.deferred.HasId

    //add int he body
    object Identifiable {
        implicit def hasId[T <: Identifiable]: HasId[T, Int] = HasId(_.id)
    }

The next step is providing GraphQL’s interface type for that trait.

Add a definition of the interface and change the `LinkType` for the following:

    val IdentifiableType = InterfaceType(
      "Identifiable",
      fields[Unit, Identifiable](
        Field("id", IntType, resolve = _.value.id)
      )
    )

    implicit val LinkType = deriveObjectType[Unit, Link](
        Interfaces(IdentifiableType)
    )

Make similar changes to `UserType` and `VoteType`.

Now if you look into the schema definition in graphiql console you will see that all three models implement the `Identifiable` interface.

So far so good. We made many changes in this chapter, so if you like you can compare current state o files with the following snippets.

[GraphQLSchema.scala](https://gist.github.com/marioosh/6f75f24bb5e5fd6fc3d46472147c4551#file-graphqlschema-scala)  
[models/package.scala](https://gist.github.com/marioosh/6f75f24bb5e5fd6fc3d46472147c4551#file-models_package-scala)  
[DAO.scala](https://gist.github.com/marioosh/6f75f24bb5e5fd6fc3d46472147c4551#file-dao-scala)  
[DBSchema.scala](https://gist.github.com/marioosh/6f75f24bb5e5fd6fc3d46472147c4551#file-dbschema-scala)

---

Ok, that’s all for this chapter. In the next one you will learn about relations.
