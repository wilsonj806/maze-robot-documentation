# index.html Structure

## Requirements

Requirements done by FCC and [Link here](https://learn.freecodecamp.org/responsive-web-design/responsive-web-design-projects/build-a-technical-documentation-page)

## Personal Requirements:

- Use CSS Variables at least once
- Use simple colors and play with transparency
- Functional over pretty
- Should have a toggle button that shows an element (via animation, like it should slide into view on clicking the button)
- Try to use CSS Grid although do note that it isn't supported on any Internet Explorer browser below V16
- Look into `@media print {}` so that you can hide the nav bar when you print the thing out
- Develop for mobile first again
- Use `code` elements to style any pieces of code shown
    - i.e if you show pieces of code, style them to be like Markdown code blocks
- Try integrating Sass into the workflow
      
## What's in this document

This document contains notes on how to structure this project and why. It will also include Emmet shortcuts that can be copied and pasted into the actual `index.html` file when you make it
    
## Class Naming Convention
`
nav= navbar although Bootstrap uses it
wrp = wrapper
ctr= container
qte = quote
btn or butn = button
ftr = feature
ol = ordered list 
usli = unstyled list
scn = screen
dpy = display
mob = mobile
hdr = header
tbl = table
req = requirements
bom = bill of materials
doc = documentation
rw = row
ovrvw = overview
sub = sub-section

`
    
## Theory Crafting

### Sections of the index.html page

0. Body
1. Nav
2. Introduction
3. Requirements
4. Bill of Materials
5. Code overview
6. Imrovements/ fixes
7. Supporting documentation

### `<body>` structure and notes

The `<body>` element should branch to two sections: `<nav>` and `<main>`. On larger screens body should be set to `display:flex;` so you can justify the two in a row

Overarching requirements for the entire `<body>` are:

- at least 10 `p` elements
- at least 5 `li` elements
- at least 1 `@media` query

Structure of `<body>` as follows:

`
body
|- nav
|   |- ul and whatever else
|- main
|   |- section
|   |- section
|   |- etc

`
### `<nav>` structure and notes

The `<nav>` needs to fullfill several requirements and they are as follows:
    1. The nav bar **MUST** have an `id` value of `id=navbar`
    2. The nav bar must have a `<header>` that describes the topic of documentation
    3. The nav bar should have anchor elements `<a>` to link to parts of the page, header comes first duh
    4. The nav bar links should all have a `.nav-link` class appended to it
    5. On laptop screens and larger, the nav bar should be displayed on the side at all times
    
Structure for `<nav>` as follows:   

`
nav#navbar
|- header.nav-hdr>{MEC 550 Maze Solving Robot Documentation}
|- ul.nav-li
|   |-li.nav-wrp
|       |- a.nav-link
|   |- (li.nav-wrp>a.nav-link)*6 


`

### General notes for the main content

Main content has a set of general requirements

- Every section should have it's own `<section>` tag with the class `.main-section`
- Every section should start with a `<header>`
- `<main>` should have and id of `id=main-doc`
- There should be at least 5 `<code>` elements used in `main` 

So the structure of `main` is as follows:

`
main#main-doc
|- section.main-section.ctr-intro
|   |- img
|   |- p>{text here}
|   |- etc
|- section.main-section.ctr-req
|- section.main-section.ctr-bom
|- section.main-section.ctr-code
|- section.main-section.ctr-fixes
|- section.main-section.ctr-doc
</main>

`

#### Introduction structure and notes

The introduction has a couple of things and also needs to fulfill a couple of requirements:

- a picture
- paragraph 1 for describing the project, the purpose of the page, and the content of this page
    - probably going to end up being two `<p>` elements or even a list, it's fairly flexible
-
    
Structure for the *Introduction* section are as follows:
    
 `
section.main-section.ctr-intro
|- header.sec-hdr>{Introduction}
|- img
|- p

`

#### Requirements structure and notes

The requirements section has the following:

- A list of the requirements for the project
- Why the requirements are what they are

Structure for the *Requirements* section are as follows:

`

section.main-section.ctr-req
|- header.sec-hdr>{Requirements}
|- p>{text here}
|- ol.ctr-ol
|   |-li>{requirement1}
|   |- (li.wrp-ol>{requirementx})*999
|- p

`
### Bill of Materials structure and notes

There's not much to the *Bill of Materials* section but it should include:

- A description of what's going to be in the bill of materials
- The actual bill of materials table
    - Said table should include model numbers and what system it's in
- A general systems/ subsystems overview

Structure for the *Bill of Materials* section is as follows:

`
section.main-section.ctr-bom
|- header.sec-hdr>{Bill of Materials}
|- p>{text here}
|- table.tbl-bom
|   |-tr.rw-hdr.rw-1>(th.tbl-hdr>{row element$})*6
    |-(tr.rw-hdr.rw-$>(td.tbl-col>{table entry})*6)*5

`

### Code Overview structure and notes

There's quite a bit that needs to happen here and it should include the following:

- At minimum, there should be at least 5 `code` elements here (especially since it's probably not going to be anywhere else)
- The code for the following sections should be included:
    - IR sensor calibration code and method
    - Ultrasonic sensor distance code/ calibration/ operating procedure
    - Maze solving algorithm
    - Color sensor calibration and theory
    - How the robot hypothetically grabs a ball
    - Wall avoidance system
- There should be an overview of how the systems interact together
- There should be an overview of the wall avoidance system
- There should be an overview of how the robot navigations through the maze
- There should be an overview of how all of these systems fit together software-wise

Structure for the *Code Overview*

`

section.main-section.ctr-ovrvw
|- header.sec-hdr>{Code Overview}
|- p>{Description of how everything should fit together and the various subsystems that need software}
|- img>{needs a flow chart of the subsystems}
|
|- h3.sub-hdr{Maze Navigation Overview}
|- p>{maze navigation}
|
|- h3.sub-hdr>{IR sensor calibration}
|- p>{text about the calibration}
|- code>{code should probably follow but this might need rethinking}
|
|- h3.sub-hdr>{Wall Avoidance System}
|- img>{Image of control system block diagram}
|- p>{control systems thing}
|- code>{code snippets for it or just a big bit of psuedocode}




`
