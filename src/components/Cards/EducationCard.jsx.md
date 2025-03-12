# EducationCard Component Documentation

## Table of Contents

* [1. Overview](#1-overview)
* [2. Component Structure](#2-component-structure)
* [3. Styling](#3-styling)
* [4. Props](#4-props)
* [5. Responsiveness](#5-responsiveness)
* [6. Hover Effects](#6-hover-effects)
* [7. Algorithm Explanation (if applicable)](#7-algorithm-explanation-if-applicable)


## 1. Overview

The `EducationCard` component is a React component designed to display information about a person's education. It uses styled-components for styling and presents information in a visually appealing and concise manner.  The card includes the school name, degree, date of attendance, grade received, a brief description, and an optional image.

## 2. Component Structure

The `EducationCard` component renders a card-like structure containing the following elements:

| Element      | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| `Top`        | Container for the image and school information.                             |
| `Image`      | Displays an image related to the educational institution.                   |
| `Body`       | Container for the school name, degree, and date.                             |
| `Name`       | Displays the name of the educational institution.                            |
| `Degree`     | Displays the degree obtained.                                                |
| `Date`       | Displays the dates of attendance.                                            |
| `Grade`      | Displays the grade received.                                                 |
| `Description`| Displays a description of the education. Uses a `Span` for text truncation. |
| `Span`       | Applies CSS to truncate the description text using `-webkit-line-clamp`.  |
| `Document`   | A hidden image that appears on hover.                                     |

The structure is designed to be responsive and adapts well to different screen sizes.


## 3. Styling

The component utilizes `styled-components` for styling.  Key styling aspects include:

* **Card:** Rounded corners, box shadow, padding, hover effects (box-shadow and transform), and responsive adjustments for smaller screens (padding, gap, and width).  A subtle border is added for visual separation.
* **Image:** Fixed height, background color, and rounded corners, with responsive adjustments for height on smaller screens.
* **Text Elements (`Name`, `Degree`, `Date`, `Grade`):**  Font sizes, weights, and colors are defined, with responsive adjustments for smaller screens.  Color is dynamically determined by the `theme` prop.
* **Description:** Uses `theme` prop for dynamic color. Text is truncated using CSS for better layout management.
* **Hover Effects:** On hover, the card gets a more pronounced box shadow, moves slightly up, shows a hidden image (`Document`), and displays the full description text, overriding `-webkit-line-clamp`.


## 4. Props

The `EducationCard` component accepts a single prop:

| Prop     | Type     | Description                                                     |
|----------|----------|-----------------------------------------------------------------|
| `education` | Object   | An object containing the education details.                     |
| `education.img` | String   | URL of the image.                                                |
| `education.school` | String   | Name of the educational institution.                             |
| `education.degree` | String   | Degree obtained.                                                |
| `education.date` | String   | Dates of attendance.                                            |
| `education.grade` | String   | Grade received.                                                 |
| `education.desc` | String   | Description of the education.                                   |


## 5. Responsiveness

The component is designed to be responsive using CSS media queries targeting screen widths of 768px or less.  Adjustments are made to font sizes, padding, gap between elements, and the width of the card itself to ensure optimal display on smaller screens.


## 6. Hover Effects

The component includes hover effects to enhance user interaction:

* **Card:** On hover, a more prominent box shadow is applied, and the card is slightly lifted using the `transform` property.
* **Hidden Image:** A hidden image (`Document`) is revealed on hover, providing additional information or visual context.
* **Description:** The truncated description is fully displayed on hover by overriding the `-webkit-line-clamp` style.


## 7. Algorithm Explanation (if applicable)

The component does not contain complex algorithms.  The styling uses standard CSS techniques and responsive design principles.  The text truncation relies on the browser's rendering engine and the `-webkit-line-clamp` CSS property. No custom algorithms are implemented within the component's logic.
