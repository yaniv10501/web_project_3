# Project 3: From Portland to Portland

The 3rd project of my journey of becoming a front-end developer.

[Link to the page](https://yaniv10501.github.io/web_project_3/)

## Description

This is a project about traveling across the US, from Portland, ME. to Portland, OR.

I made this website to display all the blocks and elements correctly on popular screen sizes with a well-planned layout and the @media rule.

All blocks and elements are named and nested according to the BEM methodology.

## Overview

* **Layout plan**

* **Flex and Grid containers**

* **@media rule**

### Layout plan

Page is divided into 7 section blocks -

* Header
* Intro
* Lead
* Photo-grid
* Places
* Cover
* Footer

Each block is either a flex container or a grid, excluding the Intro and Cover blocks.

**Intro**

The Intro Block is a block container, I chose block over flex or grid in order to make this section match the design for big screens as well as the smaller screens.

For big screens i.e. 1024px and above, the Intro text should be aligned to the left of the block matching the other sections left border while maintaining a fixed width that is smaller than the Intro block. For smaller screens, i.e. below 1024px, the Intro text width expands from 690px to 720px to match the block width and then keeps shrinking according to the block's width.

All the text elements in the Intro block have the same width, 690px for big screens and 720px / 288px for smaller screens i.e. 768px and 320px. If I were to nest the text elements in the Intro block, I had to set the block with fixed side margins or to give each text element its own width. It's better to avoid both cases in order to make the main block independent without any margins that can move other blocks around it and to be able to control the text width from a single selector.

Instead of nesting the Intro text elements in the Intro block, I nested a 690px flex container element in the Intro block, and I nested the texts elements in the container elements.

Doing so allowed me to easily control the block elements with a single @media rule for the Intro Container and then over-ride the container width from the main Intro Block while maintaining the design brief.

**Cover**

The Cover Block is in a relative position, I chose this setting so I can tweak the image opacity without harming the text while they all nested in the same block. To achieve this I nested all the elements in the Cover-Overlay element and used the ::before pseudo-element with absolute position to place the image in the same place as the cover block.

To make the block a link with a transition effect I nested the Cover-Overlay block in the Cover-Link block and I used the :hover pseudo-class to change the Cover-Overlay::before opacity.

### Flex and Grid containers

**Header**

The Header Block is a flex container, i chose flex over grid becuase i nested the language links in an unorderd list.

~~The Header Block is a grid container, I choose grid over flex in order to make a gap between the logo and the language links without nesting the links in a separate container. If I were to use a flex container, the obvious justify setting would be "space-between" so the elements would spread to the borders of the block, but that would force me to nest the language links in a separate container in order to make them both appear on the right side of the container.~~

~~Using a grid with 1 row set to 1fr, 1 column set to 1fr and 2 columns set to auto make the logo take all the space needed and leaving the language links with just enough space for the text and margin. Another advantage for using a grid is the process of adding or changing the elements, the size of the grid cells will automatically adjust for the content, and if you want to add another language link all you gotta do is add a column to the grid in the repeat function, and set the cells for the links in the lang-link selector.~~

**Places**

In Places Block there are 5 Place Blocks set to grid, I chose a grid over a wrapped flex container because for the big screens I needed the cells to automatically adjust according to the content height while maintaining the width and position of the elements. I made a 2X2 grid with a fixed width for the image and texts, 1fr width for the text and link, auto height for the text and image, and 1fr height for the header and link.

To make the link and URL-heading maintain their position while the title change height e.g. New Hampshire on 1280px screen, I set both with align-self for flex-end, and I also set the URL-heading with a margin-bottom to match the design.

**Footer**

The Footer Block is a flex container because I nested the links in a nav tags.

~~The Footer Block is a grid container that achieves the same goal as the header block for minimum nesting. For smaller screens, the grid changes from a single row to a single column to match the design.~~

### @media rule

There are 5 breakpoints -
* 1220px
* 990px
* 758px
* 700px
* 658px

For most breakpoints the width of the blocks or elements change to fit in the page, there are also some changes in the containers and the text properties.
