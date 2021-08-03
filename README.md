# Project 3: From Portland to Portland

The 3nd project of my journey of becoming a front end developer.

## Intro

This is a project about traveling across the US, from Portland, ME. to Portland, OR.

I made this website to display all the blocks and elements correctly on popular screen sizes with a well planned layout and the @media rule.

All block and element are named and nested according to the BEM methodology.

## Overview

* **Layout plan**

* **Flex and Grid containers**

* **@media rule**

### Layout plan

Page is divided to 7 section block - 
* Header
* Intro
* Lead
* Photo-grid
* Places
* Cover
* Footer

Each block is either a flex container or a grid, excluding the the Intro block which is a block container in order to make this section match the design for big screens as well as the smaller screens.

For big screens i.e. 1024px and above, the Intro text should be alligned to the left of the block matching the other sections left border while maintaining a fixed width which is smaller then the Intro block. For smaller screens, i.e. below 1024px, the Intro text width expand from 690px to 720px to match the block width and then keep shrinking according to the block's width.

All the text elements in the Intro block have the same width, 690px for big screens and 720px / 288px for smaller screens i.e. 768px and 320px. If i were to nest the text elements in the Intro block, i had to set the block with fixed side margins or to give each text element its own width. It's better to avoid both cases in order to make the main block indepandent without any margins that can move other blocks around it and to be able to cntrol the text width from a single selector.

Instead of nesting the Intro text elements in the Intro block, i nested a 690px flex container element in the Intro block, and i nested the texts elements in the container elements.

Doing so allowed me to easily control the block elements with a single @media rule for the Intro Container and then over-ride the container width from the main Intro Block while maintaining the desigen brief.

### Flex and Grid containers

abc

### @media rule

abc
