# Responsive Web Design and Regular Expressions

[Home](https://sayefdeen.github.io/reading-notes301/).

## Regex.

Regular expressions (regex or regexp) are extremely useful in **extracting information from any text** by searching for one or more matches of a specific search pattern (i.e. a specific sequence of ASCII or unicode characters), fields of application range from validation to parsing/replacing strings, passing through translating data to other formats and web scraping.

One of the most interesting featuers is that once you've learned the syntax, you can actually use this tool in (almost) all programming languages.

**Anchors ^ and \$**

|   Regex    |                         Usage                         |
| :--------: | :---------------------------------------------------: |
|    ^The    |        matches ant string that start with The         |
|   end\$    |         matches ant string that ends with end         |
| ^The end\$ | exact string match (start with The and ends with end) |
|    roar    |     match any string that has the text roar in it     |
|    roar    |     match any string that has the text roar in it     |

---

**Quntifiers \* + ? and {}**

|   Regex    |                                     Usage                                      |
| :--------: | :----------------------------------------------------------------------------: |
|   abc\*    |            matches a string that has ab followed by zero or more c             |
|    abc+    |             matches a string that has ab followed by one or more c             |
|    abc?    |             matches a string that has ab followed by zero or one c             |
|   abc{2}   |                  matches a string that has ab followed by 2 c                  |
|  abc{2,}   |              matches a string that has ab followed by 2 or more c              |
|  abc{2,5}  |              matches a string that has ab followed by 2 up to 5 c              |
|  a(bc)\*   | matches a string that has a followed by zero or more copies of the sequence bc |
| a(bc){2,5} |  matches a string that has a followed by 2 up to 5 copies of the sequence bc   |

---

**Character classes**

| Regex |                               Usage                               |
| :---: | :---------------------------------------------------------------: |
|  \d   |            matches a single character that is a digit             |
|  \D   |               matches a single non-digit character                |
|  \w   | matches a word character (alphanumeric character plus underscore) |
|  \s   | matches a word character (alphanumeric character plus underscore) |
|   .   |                       matches any character                       |

---

**Flags**

1. g (global) : does not return after the first match, retarting the subsequent searches from the end of the previous match.

2. m (multi-line) when enabled `^` and `$` will match the start and end of a line, instead of the whole string.

3. i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC).

## Summary

The application fields of regex can be multiple such as :

1. Data Validation.

2. Data Scraping : find all pages that contain a certain set of words eventually in a specific order

3. Data Wrangling : transform data from raw to another format

4. String Parsing : catch all URL GET parameters, capture text inside a set of parenthesis.

5. String Replacement.

6. Syntax Highlightning.

---

## Grid display.

CSS Grid Layout is the most powerful layout system available in CSS. It is a 2-dimensional system, meaning it can handle both columns and rows, unlike flexbox which is largely a 1-dimensional system.

[Complete Guid To Grid](https://css-tricks.com/snippets/css/complete-guide-grid/).

1.  Parent Elements (Grid Container).

    - `display : grid | inline-grid `:

      - grid : generate a block-level grid

      - inline-grid : generate an inline-level grid.

    - `grid-template-columns : [Name] value`
    - `grid-template-row : [Name] value` :

      - [Name] : an artbitrary name of your choosing

      - value : can be a length, a percentage , or a fraction of the free space in the grid (using `fr` unit).

    - `column-gap | row-gap ` : Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

2.  Children Elements (Grid Items).
    Note : float, display: inline-block, display: table-cell, vertical-align and column- properties have no effect on a grid item

        * `grid-column-start | grid-column-end | grid-row-start | grid-row-end` : Determines a grid item’s location within the grid by referring to specific grid lines

        * `justify-self` : Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis). This value applies to a grid item inside a single cell.

        * `align-self` : Aligns a grid item inside a cell along the block (column) axis (as opposed to justify-self which aligns along the inline (row) axis). This value applies to the content inside a single grid item.
