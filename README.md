# Documentation for Mozilla's PDF.js library
## Operations
### 1: dependency
* `dependencies`: *`array`* - list of dependency object ids

### 2: setLineWidth (`w`)
* `width`: *`number`*

sets line width

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2823](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2823)

### 3: setLineCap (`J`)
* `style`: *`number`* - either `0` (butt), `1` (round), or `2` (square)
sets line cap style; determines how the end points of every line are drawn;

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2824](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2824)
* https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineCap

### 4: setLineJoin (`j`)
* `style`: *`number`* - either `0` (miter), `1` (round), or `2` (bevel)

sets line join style; determines how two connecting segments (of lines, arcs or curves) with non-zero lengths in a shape are joined together;

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2825](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2825)
* https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin

### 5: setMiterLimit (`M`)
* `limit`: *`number`*

sets the miter limit ratio in space units

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2826](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2826)
* https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/miterLimit

### 6: setDash (`d`)
* `dashArray`: *`array`* - An Array of numbers which specify distances to alternately draw a line and a gap (in coordinate space units). If the number of elements in the array is odd, the elements of the array get copied and concatenated;

  see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setLineDash
* `dashPhase`: *`number`* - A float specifying the amount of the offset;

  see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset

sets the line dash pattern used when stroking lines, using an array of values which specify alternating lengths of lines and gaps which describe the pattern

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2827](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2827)

### 7: setRenderingIntent (`ri`)
// todo
* `intent`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2828](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2828)

### 8: setFlatness (`i`)
// todo
* `flatness`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2829](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2829)

### 9: setGState (`gs`)
* `states`: *`array`* - An array of key-value pairs where the first element of the pair is the key and the second element is the value.
  Keys may be any of the following:
  * `LW` ([setLineWidth](#2-setlinewidth))
  * `LC` ([setLineCap](#3-setlinecap))
  * `LJ` ([setLineJoin](#4-setlinejoin))
  * `ML` ([setMiterLimit](#5-setmiterlimit))
  * `D` ([setDash](#6-setdash))
  * `RI` ([setRenderingIntent](#7-setrenderingintent))
  * `FL` ([setFlatness](#8-setflatness))
  * `Font` ([setFont](#37-setfont))
  * `CA` (stroke alpha)
  * `ca` (fill alpha)
  * `BM` (global composite operation)
  * `SMask`.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2830](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2830)

### 10: save (`q`)
*no parameters*

Saves the following properties:
* font
  * font size
  * font size scale
  * font weight (only svg)
  * font matrix
* text
  * text matrix
  * text matrix scale
  * text horizontal scale
  * text rendering mode
  * text rise
* spacing
  * character spacing
  * word spacing
* color
  * fill color
  * stroke color
* alpha
  * alpha is shape (only canvas)
  * fill alpha
  * stroke alpha
* line
  * line width
  * line join (only svg)
  * line cap (only svg)
* leading ?
* pattern fill ?
* current point (x, y) (in user coordinates)
* start of text line (x, y) (in text coordinates)
* active s-mask
* resume s-mask context
* dash array (only svg)
* dash phase (only svg)
* dependencies (only svg)
* active clip url (only svg)
* clip group (only svg)
* mask id (only svg)

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2831](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2831)

### 11: restore (`Q`)
*no parameters*

Restores the [previously saved values](#10-save).

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2832](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2832)

### 12: transform (`cm`)
* `horizScaling`: *`number`*
* `horizSkewing`: *`number`*
* `vertSkewing`: *`number`*
* `vertScaling`: *`number`*
* `horizMoving`: *`number`*
* `vertMoving`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793795
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2833](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2833)

### 13: moveTo (`m`)
* `x`: *`number`*
* `y`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2836](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2836)

### 14: lineTo (`l`)
* `x`: *`number`*
* `y`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2837](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2837)

### 15: curveTo (`c`)
* `x1`: *`number`*
* `y1`: *`number`*
* `x2`: *`number`*
* `y2`: *`number`*
* `x3`: *`number`*
* `y3`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2838](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2838)

### 16: curveTo2 (`v`)
* `x2`: *`number`*
* `y2`: *`number`*
* `x3`: *`number`*
* `y3`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2839](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2839)

### 17: curveTo3 (`y`)
* `x1`: *`number`*
* `y1`: *`number`*
* `x3`: *`number`*
* `y3`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2840](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2840)

### 18: closePath (`h`)
Causes the point of the pen to move back to the start of the current sub-path. It tries to add a straight line (but does not actually draw it) from the current point to the start.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2841](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2841)

### 19: rectangle (`re`)
* `x`: *`number`*
* `y`: *`number`*
* `width`: *`number`*
* `height`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2842](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2842)

### 20: stroke (`S`)
*no parameters*

Draws the shape by stroking its outline.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2843](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2843)

### 21: closeStroke (`s`)
*no parameters*

Same as [`closePath`](#18-closepath) followed by a [`stroke`](#20-stroke).

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2844](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2844)

### 22: fill (`f` / `F`)
*no parameters*

Fills the current path with the current fill style (color and opacity) using the [non-zero winding rule](http://en.wikipedia.org/wiki/Nonzero-rule).

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2845-L2846](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2845-L2846)

### 23: eoFill (`f*`)
*no parameters*

Fills the current path with the current fill style (color and opacity) using the [even-odd winding rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule).

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
* 

### 24: fillStroke (`B`)
*no parameters*

Same as [`fill`](#22-fill) and [`stroke`](#20-stroke) but in one operation.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
*

### 25: eoFillStroke (`B*`)
*no parameters*

Same as [`eoFill`](#23-eofill) and [`stroke`](#20-stroke) but in one operation.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
*

### 26: closeFillStroke (`b`)
*no parameters*

Same as [`closePath`](#18-closepath) followed by a [`fillStroke`](#24-fillstroke) but in one operation.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
* 

### 27: closeEOFillStroke (`b*`)
*no parameters*

Same as [`closePath`](#18-closepath) followed by a [`eoFillStroke`](#25-eofillstroke) but in one operation.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
* 

### 28: endPath (`n`)
*no parameters*

Finalize all current path operations and run pending actions.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646
*

### 29: clip (`W`)
*no parameters*

Turns the path currently being built into the current clipping path. Uses the [non-zero winding rule](http://en.wikipedia.org/wiki/Nonzero-rule) for clipping.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1850168
*

### 30: eoClip (`W*`)
*no parameters*

Turns the path currently being built into the current clipping path. Uses the [even-odd winding rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule) for clipping.

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1850168
*

### 31: beginText (`BT`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958458
* 

Starts a new text block. Resets the text matrix, the pointer position (x and y), and the line position (x and y).

### 32: endText (`ET`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958458
*

Finalize all current text operations and run pending actions.

### 33: setCharSpacing (`Tc`)
* `spacing`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454
*

### 34: setWordSpacing (`Tw`)
* `spacing`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454
*

### 35: setHScale (`Tz`)
* `scale`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454
*

### 36: setLeading (`TL`)
* `leading`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454
* 

### 37: setFont (`Tf`)
* `fontRefName`: *`string`*
* `size`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454
*

### 38: setTextRenderingMode (`Tr`)
* `mode`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454
*

### 39: setTextRise (`Ts`)
* `rise`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454
*

### 40: moveText (`Td`)
* `x`: *`number`*
* `y`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1849331
* 

### 41: setLeadingMoveText (`TD`)
* `x`: *`number`*
* `y`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1849331
*

### 42: setTextMatrix (`Tm`)
* `horizScaling`: *`number`*
* `horizSkewing`: *`number`*
* `vertSkewing`: *`number`*
* `vertScaling`: *`number`*
* `horizMoving`: *`number`*
* `vertMoving`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1849331
*

### 43: nextLine (`T*`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1849331
*

### 44: showText (`Tj`)
* `glyphs`: *`array`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1898300
* 

### 45: showSpacedText (`TJ`)
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1898300
* 

### 46: nextLineShowText (`'`)
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1898300
*

### 47: nextLineSetSpacingShowText (`"`)
* ?
* ?
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1898300
*

### 48: setCharWidth (`d0`)
* `xWidth`: *`number`*
* `yWidth`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1853938
*

### 49: setCharWidthAndBounds (`d1`)
* `xWidth`: *`number`*
* `yWidth`: *`number`*
* `llx`: ?
* `lly`: ?
* `urx`: ?
* `ury`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1853938
*

### 50: setStrokeColorSpace (`CS`)
* `name`: *`string`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 51: setFillColorSpace (`cs`)
* `name`: *`string`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 52: setStrokeColor (`SC`)
For gray color spaces (DeviceGray, CalGray or Indexed):
* `scale`: *`number`*

For RGB color spaces (DeviceRGB, CalRGB or Lab):
* `r`: *`number`*
* `g`: *`number`*
* `b`: *`number`*

For CMYK color spaces (DeviceCMYK):
* `c`: *`number`*
* `m`: *`number`*
* `y`: *`number`*
* `k`: *`number`*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 53: setStrokeColorN (`SCN`)
* `c1` ... `cn` (`n` <= 32)
or
* `c1` ... `cn` (`n` <= 32)
* `name`

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
*

### 54: setFillColor (`sc`)
* ?
* ?
* ?
* ? // variable

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 55: setFillColorN (`scn`)
* ? (33) // variable

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 56: setStrokeGray (`G`)
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 57: setFillGray (`g`)
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 58: setStrokeRGBColor (`RG`)
* `r`: *`number`* - value between 0 and 255
* `g`: *`number`* - value between 0 and 255
* `b`: *`number`* - value between 0 and 255

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 59: setFillRGBColor (`rg`)
* `r`: *`number`* - value between 0 and 255
* `g`: *`number`* - value between 0 and 255
* `b`: *`number`* - value between 0 and 255

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 60: setStrokeCMYKColor (`K`)
* ?
* ?
* ?
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 61: setFillCMYKColor (`k`)
* ?
* ?
* ?
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3793574
* 

### 62: shadingFill (`sh`)
* `patternIR`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1851121
*

### 63: beginInlineImage (`BI`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1852045
* 

### 64: beginImageData (`ID`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1852045
*

### 65: endInlineImage (`EI`)
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1852045
*

### 66: paintXObject (`Do`)
* ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987702
*

### 67: markPoint (`MP`)
* `tag`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G13.2438921
*

### 68: markPointProps (`DP`)
* `tag`: ?
* `properties`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G13.2438921
*

### 69: beginMarkedContent (`BMC`)
* `tag`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G13.2438921
*

### 70: beginMarkedContentProps (`BDC`)
* `tag`: ?
* `properties`: ?

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G13.2438921
* 

### 71: endMarkedContent (`EMC`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G13.2438921
* 

### 72: beginCompat (`BX`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G6.1913072
*

### 73: endCompat (`EX`)
*no parameters*

Source:
* https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G6.1913072
* 

### 74: paintFormXObjectBegin
* `matrix`: ?
* `bbox`: ?

### 75: paintFormXObjectEnd
*no parameters*

### 76: beginGroup
* `group`: ?

### 77: endGroup
* `group`: ?

### 78: beginAnnotations
*no parameters*

### 79: endAnnotations
*no parameters*

### 80: beginAnnotation
* `rect`: ?
* `transform`: ?
* `matrix`: ?

### 81: endAnnotation
*no parameters*

### 82: paintJpegXObject
* `objId`: ?
* `w`: ?
* `h`: ?

### 83: paintImageMaskXObject
* `img`: ?

### 84: paintImageMaskXObjectGroup
* `images`: ?

### 85: paintImageXObject
* `objId`: ?

### 86: paintInlineImageXObject
* `imgData`: ?

### 87: paintInlineImageXObjectGroup
* `imgData`: ?
* `map`: ?

### 88: paintImageXObjectRepeat
* `objId`: ?
* `scaleX`: ?
* `scaleY`: ?
* `positions`: ?

### 89: paintImageMaskXObjectRepeat
* `imgData`: ?
* `scaleX`: ?
* `scaleY`: ?
* `positions`: ?

### 90: paintSolidColorImageMask
*no parameters*

### 91: constructPath
* `ops`: ?
* `args`: ?
