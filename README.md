# Nuxt CMS By Markdown
nuxt module for cms by markdown

## structure

[Example here](https://github.com/1056ng/nuxt-cms-md-example)

```
nuxt-project
├── models
│   └── blogs
│       ├── apple.md
│       └── grape.md
│       └── kiwi.md
│       └── lemon.md
│       └── images
│           └── ....
└── pages
    └── index.vue
    └── blogs
        └── _id.md
```

## nuxt.config.js

```
module.exports = {
  modules: [
    ['nuxt-cms-md'],
  ],
}
```

## index.vue

```
<template>
  <ul>
    <li v-for="blog in blogs">
      <nuxt-link :to="{ path: `/blogs/${blog.id}/` }">Read {{ blog.id }}</nuxt-link>
    </li>
  </ul>
</template>

<script>
export default {
  asyncData() {
    return {
      blogs: require('~/static/models/blogs/list.json')
    }
  },
}
</script>

```

## blogs/\_id.vue

```
<template>
  <div>
    <div>記事id: {{ blog.id }}</div>
    <div>
      <div>記事tags</div>
      <div v-for="tag in blog.tags">　{{ tag }}</div>
    </div>
    <div v-html="blog.html"></div>
    <nuxt-link :to="{ path: `/` }">Back List</nuxt-link>
  </div>
</template>

<script>
export default {
  asyncData({ params }) {
    return {
      blog: require(`~/static/models/blogs/${params.id}.json`),
    }
  },
}
</script>
```

## use

```
nuxt generate or nuxt dev
```

## License

[MIT](https://github.com/1056ng/nuxt-cms-md/blob/master/LICENSE)
