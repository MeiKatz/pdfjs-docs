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

### 11: restore
*no parameters*

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

### 18: closePath(/* ??? */) //

### 19: rectangle(/* ??? */) //

### 20: stroke
* `consumePath`: ?

### 21: closeStroke
*no parameters*

### 22: fill
* `consumePath`: ?

### 23: eoFill
*no parameters*

### 24: fillStroke
*no parameters*

### 25: eoFillStroke
*no parameters*

### 26: closeFillStroke
*no parameters*

### 27: closeEOFillStroke
*no parameters*

### 28: endPath
*no parameters*

### 29: clip
*no parameters*

### 30: eoClip
*no parameters*

### 31: beginText
*no parameters*

### 32: endText
*no parameters*

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
