The Flexible Box Layout Model (flexbox) is a layout model designed for one-dimensional content. It excels at taking a bunch of items which have different sizes, and returning the best layout for those items.

This is the ideal layout model for this sidebar pattern. Flexbox not only helps lay the sidebar and content out inline, but where there's not enough space remaining, the sidebar will break onto a new line. Instead of setting rigid dimensions for the browser to follow, with flexbox, you can instead provide flexible boundaries to hint how the content could display.

The main axis and the cross axis #
The key to understanding flexbox is to understand the concept of a main axis and a cross axis. The main axis is the one set by your flex-direction property. If that is row your main axis is along the row, if it is column your main axis is along the column.

Flex items move as a group on the main axis. Remember: we've got a bunch of things and we are trying to get the best layout for them as a group.

The cross axis runs in the other direction to the main axis, so if flex-direction is row the cross axis runs along the column.

You can do two things on the cross axis. You can move the items individually or as a group, so they align against each other and the flex container. Also, if you have wrapped flex lines, you can treat those lines as a group to control how space is assigned to those lines. You will see how this all works in practice throughout this guide, for now just keep in mind that the main axis follows your flex-direction.

<div class="container" id="container">
  <div>One</div>
  <div>Item two</div>
  <div>The item we will refer to as three</div>
</div>

To use flexbox you need to declare that you want to use a flex formatting context and not regular block and inline layout. Do this by changing the value of the display property to flex.

.container {
  display: flex;
}

All CSS properties have initial values which control how they behave "out of the box" when you haven't applied any CSS to change that initial behavior. The children of our flex container become flex items as soon as their parent gets display: flex, so these initial values mean that we start seeing some flexbox behavior.

Controlling the direction of items #
Even though you haven't added a flex-direction property yet, the items display as a row because the initial value of flex-direction is row. If you want a row then you don't need to add the property. To change the direction, add the property and one of the four values:

row: the items lay out as a row.
row-reverse: the items lay out as a row from the end of the flex container.
column: the items lay out as a column.
column-reverse : the items lay out as a column from the end of the flex container.

Reversing the flow of items and accessibility #
You should be cautious when using any properties that reorder the visual display away from how things are ordered in the HTML document, as it can negatively impact accessibility. The row-reverse and column-reverse values are a good example of this. The reordering only happens for the visual order, not the logical order. This is important to understand as the logical order is the order that a screen reader will read out the content, and anyone navigating using the keyboard will follow.

You can see in the following video how in a reversed column layout, tabbing between links becomes disconnected as the keyboard navigation follows the DOM not the visual display.

Writing modes and direction #
Flex items lay out as a row by default. A row runs in the direction that sentences flow in your writing mode and script direction. This means that if you are working in Arabic, which has a right-to-left (rtl) script direction, the items will line up on the right. Tab order would also begin on the right as this is the way sentences are read in Arabic.

Therefore the way flex items behave by default is linked to the writing mode of the document. Most tutorials are written using English, or another horizontal, left to right writing mode. This would make it easy to assume that flex items line up on the left, and run horizontally.

With the main and cross axis plus the writing mode to consider, the fact that we talk about start and end rather than top, bottom, left, and right in flexbox might be easier to understand. Each axis has a start and an end. The start of the main axis is referred to as main-start. So our flex items initially line up from main-start. The end of that axis is main-end. The start of the cross axis is cross-start and the end cross-end.

A labelled diagram of the above terms

.container {
  display: flex;
  flex-wrap: wrap;


1. Flexbox is designed for one-dimensional content. Explain what this means.
It provides better alignment.
2. Explain the difference between the main axis and cross axis.
They can display as a row, or a column.

3. How can using certain properties of flexbox negatively impact accessibility?
It changes the order in which it's displayed

1. What are some advantages of using flexbox over float?
gives you control over your work

2. How does this topic connect with your long term goals?
give you control over how you things to look
