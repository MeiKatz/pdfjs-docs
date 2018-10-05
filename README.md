# Documentation for Mozilla's PDF.js library
## Operations
### 1: dependency
* `dependencies`: *`array`* - list of dependency object ids

### 2: setLineWidth (`w`)
* `width`: *`number`*

sets line width

Source:
* 
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2823](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2823)

### 3: setLineCap (`J`)
* `style`: *`number`* - either `0` (butt), `1` (round), or `2` (square)
sets line cap style; determines how the end points of every line are drawn;

Source:
*
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2824](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2824)
* https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineCap

### 4: setLineJoin (`j`)
* `style`: *`number`* - either `0` (miter), `1` (round), or `2` (bevel)

sets line join style; determines how two connecting segments (of lines, arcs or curves) with non-zero lengths in a shape are joined together;

Source:
*
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2825](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2825)
* https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin

### 5: setMiterLimit (`M`)
* `limit`: *`number`*

sets the miter limit ratio in space units

Source:
* 
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2826](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2826)
* https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/miterLimit

### 6: setDash (`d`)
* `dashArray`: *`array`* - An Array of numbers which specify distances to alternately draw a line and a gap (in coordinate space units). If the number of elements in the array is odd, the elements of the array get copied and concatenated;

  see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setLineDash
* `dashPhase`: *`number`* - A float specifying the amount of the offset;

  see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset

sets the line dash pattern used when stroking lines, using an array of values which specify alternating lengths of lines and gaps which describe the pattern

Source:
*
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2827](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2827)

### 7: setRenderingIntent (`ri`)
// todo
* `intent`: ?

Source:
* 
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2828](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2828)

### 8: setFlatness (`i`)
// todo
* `flatness`: ?

Source:
* 
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
* 
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
* 
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2831](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2831)

### 11: restore (`Q`)
*no parameters*

Restores the [previously saved values](#10-save).

Source:
* 
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2832](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2832)

### 12: transform (`cm`)
* `horizScaling`: *`number`*
* `horizSkewing`: *`number`*
* `vertSkewing`: *`number`*
* `vertScaling`: *`number`*
* `horizMoving`: *`number`*
* `vertMoving`: *`number`*

Source:
* 
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

Starts a new text block. Resets the text matrix, the pointer position (x and y), and the line position (x and y).

### 32: endText (`ET`)
*no parameters*

Finalize all current text operations and run pending actions.

### 33: setCharSpacing (`Tc`)
* `spacing`: *`number`*

### 34: setWordSpacing (`Tw`)
* `spacing`: *`number`*

### 35: setHScale (`Tz`)
* `scale`: *`number`*

### 36: setLeading (`TL`)
* `leading`: *`number`*

### 37: setFont (`Tf`)
* `fontRefName`: *`string`*
* `size`: *`number`*

### 38: setTextRenderingMode (`Tr`)
* `mode`: ?

### 39: setTextRise (`Ts`)
* `rise`: ?

### 40: moveText (`Td`)
* `x`: *`number`*
* `y`: *`number`*

### 41: setLeadingMoveText (`TD`)
* `x`: *`number`*
* `y`: *`number`*

### 42: setTextMatrix (`Tm`)
* `horizScaling`: *`number`*
* `horizSkewing`: *`number`*
* `vertSkewing`: *`number`*
* `vertScaling`: *`number`*
* `horizMoving`: *`number`*
* `vertMoving`: *`number`*

### 43: nextLine (`T*`)
*no parameters*

### 44: showText (`Tj`)
* `glyphs`: *`array`*

### 45: showSpacedText (`TJ`)
* ?

### 46: nextLineShowText (`\'`)
* ?

### 47: nextLineSetSpacingShowText (`"`)
* ?
* ?
* ?

### 48: setCharWidth (`d0`)
* `xWidth`: *`number`*
* `yWidth`: *`number`*

### 49: setCharWidthAndBounds (`d1`)
* `xWidth`: *`number`*
* `yWidth`: *`number`*
* `llx`: ?
* `lly`: ?
* `urx`: ?
* `ury`: ?

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
* ? (33) / variable
*no parameters*

### 54: setFillColor
* ?
* ?
* ?
* ? // variable

### 55: setFillColorN
* ? (33) // variable
*no parameters*

### 56: setStrokeGray
* ?

### 57: setFillGray
* ?

### 58: setStrokeRGBColor
* `r`: *`number`* - value between 0 and 255
* `g`: *`number`* - value between 0 and 255
* `b`: *`number`* - value between 0 and 255

### 59: setFillRGBColor
* `r`: *`number`* - value between 0 and 255
* `g`: *`number`* - value between 0 and 255
* `b`: *`number`* - value between 0 and 255

### 60: setStrokeCMYKColor
* ?
* ?
* ?
* ?

### 61: setFillCMYKColor
* ?
* ?
* ?
* ?

### 62: shadingFill
* `patternIR`: ?

### 63: beginInlineImage
*no parameters*

### 64: beginImageData
*no parameters*

### 65: endInlineImage
* ?

### 66: paintXObject
* ?

### 67: markPoint // todo
* `tag`: ?

### 68: markPointProps // todo
* `tag`: ?
* `properties`: ?

### 69: beginMarkedContent // todo
* `tag`: ?

### 70: beginMarkedContentProps // todo
* `tag`: ?
* `properties`: ?

### 71: endMarkedContent // todo
*no parameters*

### 72: beginCompat // compatibility
*no parameters*

### 73: endCompat // compatibility
*no parameters*

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
