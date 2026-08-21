WHAT I LEARNT ABOUT FLOAT AND GRID
CSS float and CSS grid represent two fundamentally different eras of web layout design. While float was originally engineered to wrap text around images, developers spent over a decade repurposing it for multi-column web page layouts. In contrast, CSS Grid is a modern, purpose-built two-dimensional layout system designed specifically to handle both rows and columns simultaneously.
The float property was originally designed to allow text to wrap around images, similar to how images appear in newspapers and magazines. Common values include left, right, and none.

For example:

.image {
  float: left;
  width: 300px;
  margin-right: 20px;
}
This causes the image to move to the left and allows surrounding text to flow around it.

Floats were later widely used to create webpage layouts before modern layout systems such as Flexbox and Grid became popular. For example, several elements could be floated left to create columns.

However, floats can make layouts more complicated. A parent element containing floated children may collapse because floated elements are removed from the normal document flow. Developers therefore historically had to use techniques such as clear: both or clearfixes to solve these problems.

Example:

.column {
  float: left;
  width: 33.33%;
}

.clear {
  clear: both;
}

Float is still useful when you specifically want content, particularly text, to wrap around an image. However, it is generally not the preferred method for creating complete page layouts today.

CSS Grid
CSS Grid is a modern layout system specifically designed for creating two-dimensional layouts. It allows developers to control both rows and columns at the same time.

A grid container can be created with:

.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}

This creates three equal columns with a 30-pixel gap between them.

Grid is particularly useful for layouts containing multiple cards, images, galleries, dashboards, and sections. For example, a website could display three columns on a desktop and change to one column on mobile:

.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}

@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr;
  }
}

Grid also provides precise control over rows and columns. Developers can specify how much space each element occupies using properties such as grid-column, grid-row, and grid-template-areas.

Float vs Grid
The main difference is that Float was designed primarily for flowing content around elements, while Grid was designed specifically for page layout.

Float works mostly in one direction and depends heavily on the normal document flow. Grid provides explicit control over both horizontal and vertical positioning.

For modern website development, CSS Grid is generally more appropriate for complex layouts such as image galleries and multi-column sections. Float remains useful when text needs to wrap naturally around an image.

In short, Float is useful for content wrapping, while Grid is better suited for structured page layouts.
