# ExperienceCard Component Documentation

## Table of Contents

* [1. Overview](#1-overview)
* [2. Component Structure](#2-component-structure)
    * [2.1. Styled Components](#21-styled-components)
    * [2.2. `ExperienceCard` Function Component](#22-experiencecard-function-component)
* [3. Props](#3-props)
* [4. Styling](#4-styling)
* [5. Responsiveness](#5-responsiveness)
* [6. Algorithm Explanation](#6-algorithm-explanation)


## 1. Overview

The `ExperienceCard` component is a React component designed to display information about a work experience, including role, company, dates, description, skills, and optionally, a document link. It utilizes styled-components for styling and incorporates responsive design principles.


## 2. Component Structure

### 2.1. Styled Components

The component leverages styled-components to define the visual presentation.  Several styled components are used to structure and style different parts of the experience card:

| Component Name | Description |
|---|---|
| `Document` | Styles the image element representing a downloadable document.  Uses hover effects to show/hide the image and modify opacity. |
| `Description` | Styles the container for the experience description and skills. Includes responsive font size adjustments. |
| `Span` | Styles the description text, implementing a multi-line ellipsis for truncation. This ensures long descriptions don't overflow the card.  Hover effect removes truncation. |
| `Card` | The main container for the entire experience card.  Includes box shadow, hover effects (box shadow and vertical translation), and responsive padding and width adjustments.  It utilizes hover effects to control the visibility of the `Document` component and modifies `Span` to allow full description display. |
| `Top` | Container for the image and role/company/date information. |
| `Image` | Styles the image element displaying the company logo or other relevant image. Includes responsive height adjustment.|
| `Body` | Container for the `Role`, `Company`, and `Date` components, arranging them vertically. |
| `Role` | Styles the role title. |
| `Company` | Styles the company name. |
| `Date` | Styles the employment date. |
| `Skills` | Styles the container for listed skills. |
| `ItemWrapper` | Styles the wrapper for skill items, enabling wrapping for multiple skills. |
| `Skill` | Styles individual skill items. |


### 2.2. `ExperienceCard` Function Component

The `ExperienceCard` component is a functional component that accepts an `experience` object as a prop.  It renders the experience details using JSX.  The component dynamically renders the description and skills based on the presence of these properties in the `experience` object. The document link, if provided, is rendered as a hyperlink with the styled `Document` component acting as a visual cue.


## 3. Props

The `ExperienceCard` component accepts a single prop:

| Prop Name | Type | Description | Required |
|---|---|---|---|
| `experience` | Object | An object containing experience details.  | Yes |

The `experience` object is expected to have the following properties:

| Property Name | Type | Description |
|---|---|---|
| `img` | String | URL of the company logo or other image. | Yes |
| `role` | String | The job title. | Yes |
| `company` | String | The company name. | Yes |
| `date` | String | The employment dates (e.g., "2020-2022"). | Yes |
| `desc` | String | The experience description. | No |
| `skills` | Array of Strings | An array of skills used in the role. | No |
| `doc` | String | URL of a document related to the experience (e.g., resume). | No |


## 4. Styling

The component uses styled-components for styling, providing a clean and maintainable way to manage the visual aspects.  The styles include hover effects, responsive design for different screen sizes (using media queries), and consistent styling across elements.  The color scheme is dynamic, using theme props for flexibility.


## 5. Responsiveness

The component is responsive, adapting its layout and styling based on the screen size.  Media queries are used to adjust font sizes, padding, and the width of the card for smaller screens (max-width: 768px).


## 6. Algorithm Explanation

The component doesn't employ any complex algorithms.  Its logic is primarily focused on conditional rendering based on the presence of optional props (`desc`, `skills`, `doc`).  The skill list is generated using the `.map()` function to iterate through the `skills` array. The description utilizes `-webkit-line-clamp` for truncating long descriptions, and hover effects dynamically alter this property to show the full text.  No significant computational tasks are performed.
