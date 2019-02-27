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
      - [CSS-in-JS](#css-in-js)
      - [Global Styles without Shared Layout Components](#global-styles-without-shared-layout-components)
    - [CSS Modules](#css-modules)


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
There are many ways to style your components with Gatsby (It is React after all!). Below are an example of some ways to approach it.
#### Global Styles
Styles can be applied through a global style sheet. There are three approaches that can be used.
##### Shared Layout Component
Shared layout components are essentially reusable parts for common elements on your site. You can use this with a standard CSS file to style your components.

Create a layout component and an accompanying CSS file like below:
```
└───src/
      └───components/
      │   │─  MyComponent.js
      │   └─  MyComponent.css
```
> You can also separate out `MyComponent` to a separate folder within the `component` folder that contains `MyComponent.js`, `styles.css`, and `index.js` (which will export the component) instead. This is how many React libraries and applications structure it.

Fill the `MyComponent.css` file with some styles and import it into the `MyComponent` component:
```jsx
import React from "react"
import "./layout.css"

export default ({ children }) => <div>{children}</div>
```

The component can now be used in a page and the global styles will be applied.

##### CSS-in-JS
CSS-in-JS can be used via plugins in Gatsby. Install your library of choice using npm and include it as a plugin using your `gatsby.config.js` file. 

Follow the instructions of whichever plugin you're integrating. Some plugins include [Emotion](https://www.gatsbyjs.org/docs/emotion) and [Styled Components](https://www.gatsbyjs.org/docs/styled-components/).

##### Global Styles without Shared Layout Components
If you just want a stylesheet that applies for all components, you can do this by importing/requiring the stylesheet from `gatsby-browser.js`. This will not work for CSS-in-JS (Use shared layout components or a `global-styles.js`).

#### CSS Modules
CSS modules provide a more modular approach to styling components.

**Example**
To use CSS modules, you need a component and an accompany CSS file with the same name that ends with `*.module.css`.

```
└───src/
      └───pages/
      │   │─  MyComponent.js
      │   └─  MyComponent.module.css
```
Import the stylesheet into your component to use it. However, this part is slightly different. CSS modules actually import an object with all the classes of your CSS file as keys. These are guaranteed to be unique. You can use them like so:
```css
/* MyComponent.module.css */
.ugly {
  font-size: 14px;
  color: pink;
  background-color: green;
}
```
```jsx
// MyComponent.js
import React from 'react';
import styles from './MyComponent.module.css';

export default () => (
  <div>
    <p className={styles.ugly}>This is some ugly text</p>
  </div>
)
```

<div align="right">
    <b><a href="#top">↥ back to top</a></b>
</div>
