<b><a id="top" href="../../../README.md">< Back</a></b>

# Getting Started with Gatsby<!-- omit in toc -->

- [Introduction](#introduction)
- [Requirements](#requirements)
- [Basic Setup](#basic-setup)
- [Gatsby Basics](#gatsby-basics)
  - [Overview](#overview)
  - [Gatsby-Specific Configuration](#gatsby-specific-configuration)
  - [Styling](#styling)
    - [Global Styles](#global-styles)
      - [Shared Layout Component](#shared-layout-component)


## Introduction
Gatsby is a static site generator for React. It uses a query language called GraphQL for querying data from APIs.

## Requirements
- Node.js
- npm
- Prettier (*Optional*)

## Basic Setup
1. In a terminal, run `npx gatsby new project-name https://github.com/gatsbyjs/gatsby-starter-hello-world`. This creates a new Gatsby project with the Gatsby "Hello World" starter to get you going. You can also omit using the starter for a barebones project.
2. Run `npm run develop` in the directory to open a development server at `localhost:8000`.

## Gatsby Basics
### Overview
You develop your application like you would a standard React app using create-react-app. The `static` folder contains your static assets that webpack will ignore (e.g. images, icons, etc.) and the `src` contains the source code that makes up your application. The `public` folder contains your HTML template and your builds.

In Gatsby, React components in `src/pages/*.js` automatically become pages. You can link between pages using the `<Link to="/page/" />` component.

When you're done with your site, you can build the site using `npm run build`.

### Gatsby-Specific Configuration
Gatsby has four unique files that can be used to customize Gatsby and utilize their APIs.

- `gatsby-browser.js` - [Gatsby browser APIs](https://www.gatsbyjs.org/docs/browser-apis/) can be used here. Another use case for this file is to also inject global styles to your application. 
- `gatsby-config` - The main configuration for your Gatsby site. Specify metadata, include Gatsby plugins, and more. Check the [config docs](https://www.gatsbyjs.org/docs/gatsby-config/).
- `gatsby-node.js` - [Gatsby node APIs](https://www.gatsbyjs.org/docs/node-apis/) can be used here. This is for customizing/extending the build process.
- `gatsby-ssr.js` - Use the [Gatsby server-side rendering APIs](https://www.gatsbyjs.org/docs/ssr-apis/) here if you're using SSR and need to make customizations.

### Styling
There are many ways to style your application with Gatsby (It is React after all!).
#### Global Styles
Styles can be applied through a global style sheet. There are three approaches that can be used.
##### Shared Layout Component
Layout components are essentially reusable parts for common elements on your site. You can use this with a standard CSS file to style your components.

Create a layout component and an accompanying CSS file like below:
```
└───src/
      └───components/
      │   │─  MyComponent.js
      │   └─  MyComponent.css
```
> You can also separate out `MyComponent` to a separate folder within the `component` folder and have a `styles.css` and `index.js` (which will export the component) instead. This is how many React libraries and applications structure it.

Fill the `MyComponent.css` file with some styles and import it into the `MyComponent` component:
```jsx
import React from "react"
import "./layout.css"

export default ({ children }) => <div>{children}</div>
```

The component can now be used in a page and the global styles will be applied.

<div align="right">
    <b><a href="#top">↥ back to top</a></b>
</div>
