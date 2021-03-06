In this section, you’ll learn how to use the [`vue-router`](https://github.com/vuejs/vue-router) library with Apollo to implement some navigation functionality!

### Create a Header

Before moving on to configure the different routes for your application, you need to create an `AppHeader` component that users can use to navigate between the different parts of your app.

Create a new file in `src/components` and call it `AppHeader.vue`. Then paste the following code inside of it:

    <template>
      <div class="flex pa1 justify-between nowrap orange">
        <div class="flex flex-fixed black">
          <div class="fw7 mr1">Hacker News</div>
          <router-link to="/" class="ml1 no-underline black">new</router-link>
          <div class="ml1">|</div>
          <router-link to="/create" class="ml1 no-underline black">submit</router-link>
        </div>
      </div>
    </template>

    <script>
      export default {
        name: 'AppHeader'
      }
    </script>

This simply renders two `RouterLink` components that users can use to navigate between the `LinkList` and the `CreateLink` components.

### Setup routes

You’ll configure the different routes for the app in `src/router/index.js`.

Open the corresponding file `src/router/index.js` and update the code to match the following:

    import Vue from 'vue'
    import Router from 'vue-router'

    // 1
    import CreateLink from '../components/CreateLink'
    import LinkList from '../components/LinkList'

    Vue.use(Router)

    export default new Router({
      // 2
      routes: [
        {
          path: '/',
          component: LinkList
        },
        {
          path: '/create',
          component: CreateLink
        }
      ],
      // 3
      mode: 'history'
    })

Let’s take a closer look to better understand what’s going on:

1.  Here you import the `CreateLink` and `LinkList` components which will be rendered for different routes
2.  Here you map each route to the component that should be rendered
3.  Here you set mode to ‘history’ to remove the hash from the URLs

You now need to make some small updates to `src/main.js`.

Open up `src/main.js` and add the following import:

    import router from './router'

Still in `src/main.js`, add `router` to the Vue instance:

    new Vue({
      el: '#app',
      provide: apolloProvider.provide(),
      router,
      render: h => h(App)
    })

You need to update one more file, `src/App.vue`.

In `src/App.vue` update your template to the following (`router-view` is where the component for the current route will be rendered):

    <template>
      <div id="app">
        <div class="center w85">
          <app-header></app-header>
          <div class='ph3 pv1 background-gray'>
            <router-view></router-view>
          </div>
        </div>
      </div>
    </template>

Still in `src/App.vue`, import `AppHeader` and add it to the `components` object, and remove `CreateLink` and `LinkList`. Your `script` block should now look like this:

    <script>
      import AppHeader from './components/AppHeader'

      export default {
        name: 'app',
        components: {
          AppHeader
        }
      }
    </script>

That’s it. You can now access two URLs: `http://localhost:8080/` will render `LinkList` and `http://localhost:8080/create` will render the `CreateLink` component you just wrote in the previous section.

![Access the app at localhost:8080](http://imgur.com/bcHzt5W.gif)

### Implement navigation

To wrap up this section, you need to implement an automatic redirect from `CreateLink` to `LinkList` after a mutation is performed.

First, open `src/components/CreateLink.vue` and add `ALL_LINKS_QUERY` to your imports like so:

    import { ALL_LINKS_QUERY, CREATE_LINK_MUTATION } from '../constants/graphql'

Still in `src/components/CreateLink.vue` update the `createLink` method to look like the following:

    createLink () {
      const { description, url } = this.$data
      this.$apollo.mutate({
        mutation: CREATE_LINK_MUTATION,
        variables: {
          description,
          url
        },
        // 1
        update: (store, { data: { createLink } }) => {
          const data = store.readQuery({
            query: ALL_LINKS_QUERY
          })
          data.allLinks.push(createLink)
          store.writeQuery({ query: ALL_LINKS_QUERY, data })
        }
      // 2
      }).then((data) => {
        this.$router.push({path: '/'})
      // 3
      }).catch((error) => {
        console.error(error)
      })
    }

Let’s unpack what’s going on here:

1.  You add an `update` method which queries the current cache (`store`) and updates it with the result of your mutation.
2.  Here you define a success handler which routes to `/` upon a successful mutation
3.  Here you define an error handler which logs the error when a mutation fails

After the mutation is performed, `vue-router` will now navigate back to the `LinkList` component that’s accessible on the root route: `/`.
