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

## use

```
nuxt generate or nuxt dev
```

## License

[MIT](https://github.com/1056ng/nuxt-cms-md/blob/master/LICENSE)
