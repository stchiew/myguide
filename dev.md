---
title: Dev
nav_order: 6
layout: home
---

# Scaffolding

## Scaffolding Your First Vite Project

```
npm create vite@latest
```

Then follow the prompts!

You can also directly specify the project name and the template you want to use via additional command line options. For example, to scaffold a Vite + Vue project, run:

```
# npm 7+, extra double-dash is needed:
npm create vite@latest my-vue-app -- --template react-ts
```
## Testing the app

```
npm install
npm run dev
```

## Building the app for production

```
npm run build
```

### Testing the App Locally
Once you've built the app, you may test it locally by running npm run preview command.

```
$ npm run preview
```

The vite preview command will boot up a local static web server that serves the files from dist at http://localhost:4173. It's an easy way to check if the production build looks OK in your local environment.


## References

- [Vite Documenation](https://vite.dev/guide/#scaffolding-your-first-vite-project)
