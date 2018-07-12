# CSS Structure

## Class Naming Convention

```
nav = navbar although Bootstrap uses it as well
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
hfix = hardware fixes
sfix = softwarefixes
col = column
```
   
## CSS classes/ selectors, etc by section

### Global

```
a
li
p
h1,h2,h3,h4,h5,h6
table
```
### Nav specific

```
.nav-hdr
.nav-wrp
.nav-link
```

### Main content global

```
.main-section
.btn
.sec-hdr
.sub-hdr
```

### Section container classes

```
.ctr-intro
.ctr-req
.ctr-bom
```

### Other container/ other general classes

```
.ctr-ul
.ctr-ol
.btn
```

### Table classes

```
.tbl-bom
.rw-hdr
.rw-$
.tbl-hdr
.tbl-col
```

## Structure planning

So if we're using Sass as our CSS preprocessor, our file flow might look like the below, where we're largely importing a bunch of partials and compiling them all in one `.scss` file to compile.

```
-scss/
|- main.scss
|- _config.scss
|- _content.scss
|- _viewports.scss
|- _modules/
|   |- _tables.scss
|   |- _buttons.scss
```
Where the files do the following:

- `base.scss` includes styling for `p` elements, `h*` elements, fonts, colors, normalizing, etc
- `content.scss` includes the `nav` styling, general container styling, table styling and etc
-  `viewports.scss` includes `@media` queries
- The `modules` folder stores the styling for modules like tables or buttons


