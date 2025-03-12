# ProjectCards Component Documentation

## Table of Contents

* [1. Overview](#1-overview)
* [2. Component Structure](#2-component-structure)
    * [2.1. Styled Components](#21-styled-components)
    * [2.2. Functional Component `ProjectCards`](#22-functional-component-projectcards)
* [3. Algorithm Explanation](#3-algorithm-explanation)


## 1. Overview

The `ProjectCards` component renders a visually appealing card displaying project information.  It utilizes styled-components for styling and accepts a `project` object as a prop, dynamically rendering project details. A hover effect reveals a hidden "View Project" button (currently commented out). The component also handles opening a modal (controlled by the `setOpenModal` prop) when clicked.


## 2. Component Structure

### 2.1. Styled Components

The component leverages styled-components to define the visual presentation.  Key aspects include:

| Styled Component | Description | Key Styling Features |
|---|---|---|
| `Button` | Hidden button revealed on hover. | `display: none;` (initially hidden), `width: 100%;`, theme-based colors and fonts, rounded corners, hover transition |
| `Card` | Container for project information. | `width: 330px;`, `height: 490px;`, theme-based background color, box shadow, hover effects (translateY, box-shadow, filter),  flexbox layout for internal elements. |
| `Image` | Displays project image. | `width: 100%;`, `height: 180px;`, theme-based background color, rounded corners, box shadow |
| `Tags` | Displays project tags. | Flexbox for horizontal/wrapping display of tags, gap for spacing |
| `Tag` | Individual project tag. | Theme-based colors, rounded corners, padding |
| `Details` | Container for title, date, and description. | Flexbox for vertical arrangement of elements |
| `Title` | Project title. | Font size, weight, color, text truncation using `-webkit-line-clamp` for multi-line text handling |
| `Date` | Project date. | Font size, weight, color, responsive font size adjustment for smaller screens |
| `Description` | Project description. | Font weight, color, text truncation using `-webkit-line-clamp`  |
| `Members` | Displays project members' avatars. | Flexbox for horizontal arrangement of avatars |
| `Avatar` | Individual member's avatar image. | Size, rounded corners, background color, box shadow, border |


All styled components utilize a theme prop (`({ theme }) => theme.property`) allowing for centralized theme management and consistent styling across the application.


### 2.2. Functional Component `ProjectCards`

The `ProjectCards` component is a functional React component. It receives the following props:

* `project`: An object containing project data (image, tags, title, date, description, members).
* `setOpenModal`: A function to update the modal's state.

The component's logic involves mapping over the `project.tags` and `project.member` arrays to render individual tags and member avatars respectively.  The `onClick` handler on the `Card` calls `setOpenModal` to open the modal, passing the updated state and the current project data.

The `project` object prop is expected to have the following structure:

```json
{
  "image": "path/to/image.jpg",
  "tags": ["tag1", "tag2", "tag3"],
  "title": "Project Title",
  "date": "2024-10-27",
  "description": "Project description...",
  "member": [
    { "img": "path/to/avatar1.jpg" },
    { "img": "path/to/avatar2.jpg" }
  ]
}
```



## 3. Algorithm Explanation

The core logic within `ProjectCards` is straightforward.  The `map` function is used twice:

1. **Tags Rendering:**  `project.tags?.map((tag, index) => (<Tag>{tag}</Tag>))` iterates through the `project.tags` array (using optional chaining `?.` for null safety). For each tag, it creates a `<Tag>` component displaying the tag's text.

2. **Members Rendering:** `project.member?.map((member) => (<Avatar src={member.img}/>))` iterates through the `project.member` array (using optional chaining). For each member, it creates an `<Avatar>` component, displaying the member's avatar image.

No complex algorithms are employed; the component's functionality relies primarily on React's rendering capabilities and the `map` function for iterative data processing. The text truncation in `Title` and `Description` components leverages CSS's `-webkit-line-clamp` property, which is a simple CSS technique rather than a programmatic algorithm.
