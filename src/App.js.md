# Internal Code Documentation: App.js

## Table of Contents

* [1. Overview](#1-overview)
* [2. File Imports](#2-file-imports)
* [3. Styled Components](#3-styled-components)
    * [3.1 Body Component](#31-body-component)
    * [3.2 Wrapper Component](#32-wrapper-component)
* [4. App Component](#4-app-component)
    * [4.1 State Variables](#41-state-variables)
    * [4.2 JSX Structure](#42-jsx-structure)
* [5. Component Hierarchy](#5-component-hierarchy)


## 1. Overview

This document details the `App.js` file, the main application component of the project.  It outlines the structure, imports, styling, and component interactions.


## 2. File Imports

The `App.js` file utilizes several imports to construct the application's user interface and functionality:

| Import Statement                     | Description                                                                     |
|--------------------------------------|---------------------------------------------------------------------------------|
| `{ ThemeProvider } from "styled-components"` | Provides theme context for styled components.                                     |
| `{ useState, useEffect } from "react"` | React Hooks for managing state and side effects.                              |
| `{ darkTheme, lightTheme } from './utils/Themes.js'` | Imports pre-defined light and dark themes.                                      |
| `Navbar from "./components/Navbar"`    | Imports the navigation bar component.                                           |
| `'./App.css'`                         | Imports the application's CSS stylesheet.                                      |
| `{ BrowserRouter as Router } from 'react-router-dom'` | Enables client-side routing within the application.                          |
| `HeroSection from "./components/HeroSection"` | Imports the hero section component.                                           |
| `About from "./components/About"`       | Imports the "About" section component.                                          |
| `Skills from "./components/Skills"`     | Imports the skills section component.                                           |
| `Projects from "./components/Projects"`   | Imports the projects section component.                                        |
| `Footer from "./components/Footer"`     | Imports the footer component.                                                   |
| `ProjectDetails from "./components/ProjectDetails"` | Imports the detailed project view component (modal).                            |
| `styled from "styled-components"`     | Imports the styled-components library for CSS-in-JS styling.                 |


## 3. Styled Components

The application uses styled-components to define CSS styles directly within JavaScript.

### 3.1 Body Component

The `Body` component styles the main body content area:

```javascript
const Body = styled.div`
  background-color: ${({ theme }) => theme.bg};
  width: 100%;
  overflow-x: hidden;
`;
```

This applies a background color based on the current theme, sets the width to 100% of the viewport, and hides any horizontal scrollbars.


### 3.2 Wrapper Component

The `Wrapper` component applies a gradient background and a custom clip-path for visual styling:

```javascript
const Wrapper = styled.div`
  background: linear-gradient(38.73deg, rgba(204, 0, 187, 0.15) 0%, rgba(201, 32, 184, 0) 50%), linear-gradient(141.27deg, rgba(0, 70, 209, 0) 50%, rgba(0, 70, 209, 0.15) 100%);
  width: 100%;
  clip-path: polygon(0 0, 100% 0, 100% 100%,30% 98%, 0 100%);
`;
```

It uses two overlapping linear gradients to create a unique background effect and a non-rectangular `clip-path` to shape the element.


## 4. App Component

The `App` function is the root component of the application.

### 4.1 State Variables

The `App` component manages two state variables using the `useState` hook:

*   `darkMode`: A boolean value indicating whether the dark theme is active.  Defaults to `true`.
*   `openModal`: An object with `state` (boolean, indicating whether the project details modal is open) and `project` (holds data for the currently viewed project). Defaults to `{ state: false, project: null }`.


### 4.2 JSX Structure

The `App` component renders the following structure using JSX:

1.  A `ThemeProvider` to apply the selected theme (`darkTheme` or `lightTheme`).
2.  A `Router` from `react-router-dom` for routing functionality (though not explicitly used in this snippet).
3.  The `Navbar` component for navigation.
4.  The `Body` component wrapping the main content.
5.  The `HeroSection` component.
6.  The `Wrapper` component containing the `Skills` component.
7.  The `Projects` component, which passes `openModal` and `setOpenModal` to manage the project details modal.
8.  The `Footer` component.
9.  Conditionally renders `ProjectDetails` component when `openModal.state` is true.

The `Projects` component is responsible for handling opening the modal by updating `openModal` state.  The `ProjectDetails` component uses  `openModal` and `setOpenModal` to display project details and close itself.


## 5. Component Hierarchy

The application's component hierarchy is as follows:

```
App
├── Navbar
├── Body
│   ├── HeroSection
│   ├── Wrapper
│   │   └── Skills
│   ├── Projects
│   │   └── ProjectDetails (Conditional)
│   └── Footer
└── Router
```
