# Markup Language Specification


# Italic

Text that is _surrounded on both sides_ by single underscores
should be placed inside the HTML \<em> tag like this:

Text that is \<em>surrounded on both sides\</em> by single underscores
should be placed inside the HTML \<em> tag.


# Bold

__Text highlighted with two underscores characters__ should be made bold using the \<strong> tag.


# Escape character

Any character can be escaped so that it is not considered part of the markup.

This should not be separated by the \<em> tag.

The escape character disappears from the result only if it escapes something.

The escape characters here should remain.

The escape character can also be escaped: \\_this will be separated by the \<em> tag.


# Interaction of tags

Inside __double_ selection, _single_ also__ works.

But not the other way around — inside _single_ __double__ does not_ work.

Underscores inside text with numbers_12_3 are not considered as highlighting and should remain underscore characters.

However, they can highlight part of a word: at _the_beginning_, and in the_middle_, and at the_end_._

At the same time, highlighting in different w_ords does not work.

__Unpaired_ characters within a single paragraph are not considered as highlighting.

Underscores that begin highlighting must be followed by a non-space character. Otherwise, these_ underscores_ are not considered as highlighting
and remain simply underscore characters.

Underscores that end highlighting must follow a non-space character. Otherwise, these _underscores_ are _not_ considered as the end of highlighting
and remain simply underscore characters.

In the case of __intersection of _double__ and single_ underscores, neither of them is considered a highlight.

If there is an empty string ____ inside the underscores, they remain underscores.


# Header

A paragraph starting with "#" is separated by the \<h1> tag into the heading.
The heading text may contain all other markup symbols with the specified rules.

Thus

# Heading __with _different_ symbols__

will turn into:

\<h1>Heading \<strong>with \<em>different\</em> symbols\</strong>\</h1>


# Bulleted list

An unordered list item must be wrapped in the appropriate HTML tags and the unordered list tag:

- First item

will become

<ul><li>First item</li></ul>

When working with multiple list items, they are nested in the unordered list tag:

For example,

- First item\n- Second item

will become

<ul><li>First item</li><li>Second item</li></ul>

In all this, the tag must only work at the beginning of the line.

For example, the following line will not be changed

First - item

However, if there is an unordered list item sign at the beginning of the line, it will wrap the line, but the element that was not at the beginning of the line will remain unchanged:

- First - item

will become

<ul><li>First - item</li></ul>