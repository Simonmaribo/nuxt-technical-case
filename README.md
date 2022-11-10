# nuxt-technical-case

# What's the meaning of the case?
You are able to try out building something with our tech setup, and we can afterwards have a constructive talk about how you approached a technical implementation/problem.


# What is the case?
We need some way of showing all of our campaigns horizontally. But there may be too many for the users screen, meaning we need to introduce some smart way of scrolling.


Implement a container component that shows the cards inside it horizontally overflow, and add buttons/arrows so the user can scroll without using the scrollbar.
Even though there is tons of libraries solving this, try solving it without adding anything new to package.json ;)

Consider creating more than the container component to make the code base more readable, for-example create a campaign card component, and applying a bit of css to make it more than just plain html elements. If time, make UX even better by disabling/hiding the buttons when they are not "usable/doing anything".

*Tip: nuxt.js auto imports using filename of the file in the `components`*



## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run start

```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## Fetching data
We have implemented a simple GET REST service that resolves dummy campaign information, this endpoint is available at https://technical-case.dreaminfluencers.com/ .

## Design
We have a Figma design available that shows how the design could look like.
https://www.figma.com/file/AaLshtmpoOV9ynUwXNUVsn/Code-Task-(Swimlane)?node-id=1%3A3058 (If you have issues inspecting design information, try logging into figma)

[![figma](https://r2.dreaminfluencers.com/campaigns.png "figma")](https://r2.dreaminfluencers.com/campaigns.png "figma")

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).


### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).
