# Documentation for Mozilla's PDF.js library
## Operations
### 1: dependency
* `dependencies`: *`array`* - list of dependency object ids

### 2: setLineWidth
* `width`: *`number`*

sets line width

### 3: setLineCap
* `style`: *`number`* - either `0` (butt), `1` (round), or `2` (square)
sets line cap style; determines how the end points of every line are drawn;

see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineCap

### 4: setLineJoin
* `style`: *`number`* - either `0` (miter), `1` (round), or `2` (bevel)

sets line join style; determines how two connecting segments (of lines, arcs or curves) with non-zero lengths in a shape are joined together;

see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin

### 5: setMiterLimit
* `limit`: *`number`*

sets the miter limit ratio in space units

see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/miterLimit

### 6: setDash
* `dashArray`: *`array`* - An Array of numbers which specify distances to alternately draw a line and a gap (in coordinate space units). If the number of elements in the array is odd, the elements of the array get copied and concatenated;

  see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setLineDash
* `dashPhase`: *`number`* - A float specifying the amount of the offset;

  see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset

sets the line dash pattern used when stroking lines, using an array of values which specify alternating lengths of lines and gaps which describe the pattern

### 7: setRenderingIntent
// todo
* `intent`: ?

unsure what it does. see: https://github.com/mozilla/pdf.js/blob/66ffdc4c5b63a135f201508264761fce17c08059/src/display/canvas.js#L888

### 8: setFlatness
// todo
* `flatness`: ?

unsure what it does. see: https://github.com/mozilla/pdf.js/blob/66ffdc4c5b63a135f201508264761fce17c08059/src/display/canvas.js#L893

### 9: setGState
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

### 10: save
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


### 11: restore
*no parameters*

Restores the [previously saved values](#10-save).

### 12: transform
* `horizScaling`: *`number`*
* `horizSkewing`: *`number`*
* `vertSkewing`: *`number`*
* `vertScaling`: *`number`*
* `horizMoving`: *`number`*
* `vertMoving`: *`number`*

### 13: moveTo //

### 14: lineTo //

### 15: curveTo(/* ??? */) //

### 16: curveTo2(/* ??? */) //

### 17: curveTo3(/* ??? */) //

### 18: closePath
Causes the point of the pen to move back to the start of the current sub-path. It tries to add a straight line (but does not actually draw it) from the current point to the start.

### 19: rectangle(/* ??? */) //

### 20: stroke
*no parameters*

Draws the shape by stroking its outline.

### 21: closeStroke
*no parameters*

Same as [`closePath`](#18-closepath) followed by a [`stroke`](#20-stroke).

### 22: fill
*no parameters*

Fills the current path with the current fill style (color and opacity) using the [non-zero winding rule](http://en.wikipedia.org/wiki/Nonzero-rule).

### 23: eoFill
*no parameters*

Fills the current path with the current fill style (color and opacity) using the [even-odd winding rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule).

### 24: fillStroke
*no parameters*

Same as [`fill`](#22-fill) and [`stroke`](#20-stroke) but in one operation.

### 25: eoFillStroke
*no parameters*

Same as [`eoFill`](#23-eofill) and [`stroke`](#20-stroke) but in one operation.

### 26: closeFillStroke
*no parameters*

Same as [`closePath`](#18-closepath) followed by a [`fillStroke`](#24-fillstroke) but in one operation.

### 27: closeEOFillStroke
*no parameters*

Same as [`closePath`](#18-closepath) followed by a [`eoFillStroke`](#25-eofillstroke) but in one operation.

### 28: endPath
*no parameters*

Finalize all current path operations and run pending actions.

### 29: clip
*no parameters*

Turns the path currently being built into the current clipping path. Uses the [non-zero winding rule](http://en.wikipedia.org/wiki/Nonzero-rule) for clipping.

### 30: eoClip
*no parameters*

Turns the path currently being built into the current clipping path. Uses the [even-odd winding rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule) for clipping.

### 31: beginText
*no parameters*

Starts a new text block. Resets the text matrix, the pointer position (x and y), and the line position (x and y).

### 32: endText
*no parameters*

Finalize all current text operations and run pending actions.

### 33: setCharSpacing
* `spacing`: *`number`*

### 34: setWordSpacing
* `spacing`: *`number`*

### 35: setHScale
* `scale`: *`number`*

### 36: setLeading
* `leading`: *`number`*

### 37: setFont
* `fontRefName`: *`string`*
* `size`: *`number`*

### 38: setTextRenderingMode
* `mode`: ?

### 39: setTextRise
* `rise`: ?

### 40: moveText
* `x`: *`number`*
* `y`: *`number`*

### 41: setLeadingMoveText
* `x`: *`number`*
* `y`: *`number`*

### 42: setTextMatrix
* `horizScaling`: *`number`*
* `horizSkewing`: *`number`*
* `vertSkewing`: *`number`*
* `vertScaling`: *`number`*
* `horizMoving`: *`number`*
* `vertMoving`: *`number`*

### 43: nextLine
*no parameters*

### 44: showText
* `glyphs`: *`array`*

### 45: showSpacedText: 45, // ??

### 46: nextLineShowText: 46, // ??

### 47: nextLineSetSpacingShowText: 47, // ??

### 48: setCharWidth
* `xWidth`: *`number`*
* `yWidth`: *`number`*

### 49: setCharWidthAndBounds
* `xWidth`: *`number`*
* `yWidth`: *`number`*
* `llx`: ?
* `lly`: ?
* `urx`: ?
* `ury`: ?

### 50: setStrokeColorSpace: 50, // ??

### 51: setFillColorSpace: 51, // ??

### 52: setStrokeColor: 52, // ??

### 53: setStrokeColorN
*no parameters*

### 54: setFillColor: 54, // ??

### 55: setFillColorN
*no parameters*

### 56: setStrokeGray: 56, // ??

### 57: setFillGray: 57, // ??

### 58: setStrokeRGBColor
* `r`: *`number`* - value between 0 and 255
* `g`: *`number`* - value between 0 and 255
* `b`: *`number`* - value between 0 and 255

### 59: setFillRGBColor
* `r`: *`number`* - value between 0 and 255
* `g`: *`number`* - value between 0 and 255
* `b`: *`number`* - value between 0 and 255

### 60: setStrokeCMYKColor
currently unused

### 61: setFillCMYKColor
currently unused

### 62: shadingFill
* `patternIR`: ?

### 63: beginInlineImage() {} // unreachable

### 64: beginImageData() {} // unreachable

### 65: endInlineImage
currenty unused

### 66: paintXObject() {} // unsupported

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
