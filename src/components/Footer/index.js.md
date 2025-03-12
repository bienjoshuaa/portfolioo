# Footer Component Documentation

[Linked Table of Contents](#linked-table-of-contents)

## Linked Table of Contents

* [1. Overview](#1-overview)
* [2. Component Structure](#2-component-structure)
    * [2.1. `FooterContainer`](#21-footercontainer)
    * [2.2. `FooterWrapper`](#22-footerwrapper)
    * [2.3. `Logo`](#23-logo)
    * [2.4. `Nav`](#24-nav)
    * [2.5. `NavLink`](#25-navlink)
    * [2.6. `SocialMediaIcons`](#26-socialmediaicons)
    * [2.7. `SocialMediaIcon`](#27-socialmediaicon)
    * [2.8. `Copyright`](#28-copyright)
* [3. Styling](#3-styling)
* [4. Responsiveness](#4-responsiveness)
* [5. Functionality](#5-functionality)


## 1. Overview

The `Footer` component is a React component designed to provide a consistent footer section across the application.  It includes a logo, navigation links, social media icons, and a copyright notice.  The component leverages styled-components for styling and Material UI icons for social media representations.


## 2. Component Structure

The `Footer` component utilizes a nested structure of styled components to create a visually appealing and organized footer.

| Component Name        | Description                                                                     |
|-----------------------|---------------------------------------------------------------------------------|
| `FooterContainer`     | The outermost container, providing overall width and padding.                  |
| `FooterWrapper`       | Wraps the footer content, controlling layout and alignment.                      |
| `Logo`                | Displays the website's logo.                                                    |
| `Nav`                 | Contains navigation links to various sections of the website.                   |
| `NavLink`             | Represents an individual navigation link.                                       |
| `SocialMediaIcons`   | Container for social media icons.                                                |
| `SocialMediaIcon`     | Represents a single social media icon link.                                     |
| `Copyright`           | Displays the copyright information.                                             |


### 2.1. `FooterContainer`

This component uses styled-components to set the overall width and padding for the footer.  A commented-out `linear-gradient` suggests an earlier design choice.

### 2.2. `FooterWrapper`

This component sets the max-width for the footer content, ensuring it remains appropriately sized on larger screens. It uses `flex-direction: column` to stack elements vertically and `gap` for spacing.

### 2.3. `Logo`

A styled `h1` element displaying the website's logo. The color is dynamically pulled from the theme.

### 2.4. `Nav`

A styled `nav` element containing navigation links. Media queries are used to adjust the layout for smaller screens. The algorithm for responsiveness involves wrapping links and adjusting spacing and font size below 768px.

### 2.5. `NavLink`

A styled `<a>` element representing each navigation link.  It includes hover effects and responsive font sizing.

### 2.6. `SocialMediaIcons`

A simple styled `div` to arrange social media icons horizontally.

### 2.7. `SocialMediaIcon`

A styled `<a>` element for each social media icon.  Similar to `NavLink`, it uses hover effects and dynamic color from the theme.

### 2.8. `Copyright`

A styled `<p>` element displaying copyright information.


## 3. Styling

The component utilizes styled-components for styling, allowing for dynamic styling based on the application's theme.  The theme provides values for `text_primary`, `primary`, and `soft2` colors, allowing for consistent branding.  Hover effects are implemented on navigation links and social media icons to provide visual feedback to the user.

## 4. Responsiveness

The `Nav` component employs media queries (`@media (max-width: 768px)`) to adapt its layout for smaller screens.  This ensures that the navigation links wrap onto multiple lines and the font size adjusts accordingly, maintaining usability on various screen sizes. The algorithm used is a simple media query that triggers style changes when the viewport width falls below 768 pixels.

## 5. Functionality

The `Footer` component renders the footer section.  Social media links use the `Bio` object imported from `../../data/constants` to dynamically set the URLs. The `target="display"` attribute opens these links in a new tab, improving user experience.  The copyright notice provides standard copyright information.  No complex algorithms are used within the component itself; it primarily focuses on rendering pre-defined content and links.
