**Note:** The final project for this tutorial can be found on [GitHub](https://github.com/howtographql/react-urql). You can always use it as a reference whenever you get lost throughout the course of the following chapters. Also note that each code block is annotated with a filename. These annotations directly link to the corresponding file on GitHub, so you can clearly see where to put the code and what the end result will look like.

**Need some help?** No tutorial is perfect and questions always come up, so [feel free to reach out to us and the community over on the urql Spectrum](https://spectrum.chat/urql), if you have any questions or need some help!

### Overview

In the previous tutorials, you learned about major concepts and benefits of GraphQL. Now is the time to get your hands dirty and start out with an actual project!

You’re going to build a simple clone of [Hackernews](https://news.ycombinator.com/). Here’s a list of the features the app will have:

- Display a list of links
- Search the list of links
- Users can authenticate
- Authenticated users can create new links
- Authenticated users can upvote links (one vote per link and user)
- Realtime updates when other users upvote a link or create a new one

In this track, you’ll use the following technologies for building the app:

- Frontend:
  - [React](https://facebook.github.io/react/): Frontend framework for building user interfaces
  - [urql](https://github.com/FormidableLabs/urql): Flexible and extensible GraphQL client for React
  - <span class="citation" data-cites="urql/exchange-graphcache">\[@urql/exchange-graphcache\]</span>(https://github.com/FormidableLabs/urql-exchange-graphcache): A normalized cache implementation for urql
- Backend:
  - [`graphql-yoga`](https://github.com/prisma/graphql-yoga/): Fully-featured GraphQL Server with focus on easy setup, performance & great developer experience
  - [Prisma](https://www.prisma.io/): Open-source GraphQL API layer that turns your database into a GraphQL API

You’ll create the React project with [`create-react-app`](https://github.com/facebookincubator/create-react-app), a popular command-line tool that gives you a blank project with all required build configuration already setup.

### Why a GraphQL Client?

In the [Clients](/advanced/0-clients/) section in the GraphQL part, we already covered the responsibilities of a GraphQL client on a higher level, now it’s time to get more concrete.

In short, you should use a GraphQL client for tasks that are repetitive and agnostic to the app you’re building. For example, being able to send queries and mutations without having to worry about lower-level networking details or maintaining a local cache. This is functionality you’ll want in any frontend application that’s talking to a GraphQL server - why build it yourself when you can use one of the amazing GraphQL clients out there?

There are a few GraphQL client libraries available, that all give you varying degrees of control over ongoing GraphQL operations and come with various different benefits and drawbacks. For very simple use cases (such as writing scripts), [`graphql-request`](https://github.com/prisma/graphql-request) might already be enough for your needs. Libraries like it are thin layers around sending HTTP requests to your GraphQL API.

Chances are that you’re writing a somewhat larger application where you want to benefit from caching, optimistic UI updates and other handy features. In these cases you’ll likely want to use a full GraphQL client that handles the lifecycle of all your GraphQL operations. You have the choice between [urql](https://github.com/FormidableLabs/urql), [Apollo Client](https://github.com/apollographql/apollo-client), and [Relay](https://facebook.github.io/relay/).

### urql vs Apollo vs Relay

The most common question heard from people that are getting started with GraphQL on the frontend is which GraphQL client they should use. We’ll try to provide a few hints that’ll help you decide which of these clients is the right one for your next project!

[Relay](https://facebook.github.io/relay/) is Facebook’s homegrown GraphQL client that they open-sourced alongside GraphQL in 2015. It incorporates all the learnings that Facebook gathered since they started using GraphQL in 2012. Relay is heavily optimized for performance and comes with an opinionated structure that helps you manage a high level of complexity with ease. An interesting side-note is that Relay itself actually started out as a _routing_ framework that eventually got combined with data loading responsibilities. It thus evolved into a powerful data management solution that can be used in JavaScript apps to interface with GraphQL APIs.

The performance benefits of Relay come at the cost of a notable learning curve. Relay is a pretty complex framework and understanding all its bits and pieces does require some time to really get into it. The overall situation in that respect has improved with the release of the 1.0 version, called [Relay Modern](http://facebook.github.io/relay/docs/en/introduction-to-relay.html), but if you’re looking for something to customize or easy to get started with, Relay might not be the right choice just yet.

[Apollo Client](https://github.com/apollographql/apollo-client) is a community-driven effort to build an easy-to-understand, flexible and powerful GraphQL client. Apollo has the ambition to build one library for every major development platform that people use to build web and mobile applications. Right now there is a JavaScript client with bindings for popular frameworks like [React](https://github.com/apollographql/react-apollo), [Angular](https://github.com/apollographql/apollo-angular), [Ember](https://github.com/bgentry/ember-apollo-client) or [Vue](https://github.com/Akryum/vue-apollo) as well as early versions of [iOS](https://github.com/apollographql/apollo-ios) and [Android](https://github.com/apollographql/apollo-android) clients. Apollo is production-ready and has handy features like caching, optimistic UI, subscription support and many more.

[urql](https://github.com/FormidableLabs/urql) is a more dynamic approach on GraphQL clients and a newer project compared to Relay and Apollo. While it’s highly focused on React, at its core it focuses on simplicity and extensibility. It comes with the barebones to build an efficient GraphQL client, but gives you full control over how it processes GraphQL operations and results via “Exchanges”. Together with the first-party exchange [`@urql/exchange-graphcache`](https://github.com/FormidableLabs/urql-exchange-graphcache) it is basically equivalent in functionality with Apollo, but with a smaller footprint and a very focused API.
