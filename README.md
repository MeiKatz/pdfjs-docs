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
#### Operands
* `x`: *`number`*
* `y`: *`number`*

#### PDF Specification
Begin a new subpath by moving the current point to coordinates (`x`, `y`), omitting any connecting line segment. If the previous path construction operator in the current path was also **`m`**, the new **`m`** overrides it; no vestige of the previous **`m`** operation remains in the path.

#### Source
* [PDF Specification / Table 59 – Path Construction Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2836](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2836)

### 14: lineTo (`l`)
#### Operands
* `x`: *`number`*
* `y`: *`number`*

#### PDF Specification
Append a straight line segment from the current point to the point (`x`, `y`). The new current point shall be (`x`, `y`). 

#### Source
* [PDF Specification / Table 59 – Path Construction Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2837](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2837)

### 15: curveTo (`c`)
#### Operands
* `x1`: *`number`*
* `y1`: *`number`*
* `x2`: *`number`*
* `y2`: *`number`*
* `x3`: *`number`*
* `y3`: *`number`*

#### PDF Specification
Append a cubic Bézier curve to the current path. The curve shall extend from the current point to the point (`x3`, `y3`), using (`x1`, `y1`) and (`x2`, `y2`) as the Bézier control points. The new current point shall be (`x3`, `y3`). 

#### Source
* [PDF Specification / Table 59 – Path Construction Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2838](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2838)

### 16: curveTo2 (`v`)
#### Operands
* `x2`: *`number`*
* `y2`: *`number`*
* `x3`: *`number`*
* `y3`: *`number`*

#### PDF Specification
Append a cubic Bézier curve to the current path. The curve shall extend from the current point to the point (`x3`, `y3`), using the current point and (`x2`, `y2`) as the Bézier control points. The new current point shall be (`x3`, `y3`). 

#### Source
* [PDF Specification / Table 59 – Path Construction Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2839](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2839)

### 17: curveTo3 (`y`)
#### Operands
* `x1`: *`number`*
* `y1`: *`number`*
* `x3`: *`number`*
* `y3`: *`number`*

#### PDF Specification
Append a cubic Bézier curve to the current path. The curve shall extend from the current point to the point (`x3`, `y3`), using (`x1`, `y1`) and (`x3`, `y3`) as the Bézier control points. The new current point shall be (`x3`, `y3`). 

#### Source
* [PDF Specification / Table 59 – Path Construction Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2840](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2840)

### 18: closePath (`h`)
#### Operands
*none*

#### PDF Specification
Close the current subpath by appending a straight line segment from the current point to the starting point of the  
subpath. If the current subpath is already closed, **`h`** shall do nothing. 

This operator terminates the current subpath. Appending another segment to the current path shall begin a new subpath, even if the new segment begins at the endpoint reached by the **`h`** operation. 

#### Source
* [PDF Specification / Table 59 – Path Construction Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2841](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2841)

### 19: rectangle (`re`)
#### Operands
* `x`: *`number`*
* `y`: *`number`*
* `width`: *`number`*
* `height`: *`number`*

#### PDF Specification
Append a rectangle to the current path as a complete subpath, with lower-left corner (`x`, `y`) and dimensions `width` and `height` in user space. The operation

```
x y width height re
```
is equivalent to
```
x y m
(x + width) y l
(x + width) (y + height) l
x (y + height) l
h
```

#### Source
* [PDF Specification / Table 59 – Path Construction Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987642)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2842](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2842)

### 20: stroke (`S`)
#### Operands
*none*

#### PDF Specification
Stroke the path.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2843](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2843)

### 21: closeStroke (`s`)
#### Operands
*none*

#### PDF Specification
[Close](#18-closepath-h) and [stroke](#20-stroke-s) the path. This operator shall have the same effect as the sequence `h S`. 

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2844](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2844)

### 22: fill (`f` / `F`)
#### Operands
*none*

#### PDF Specification
Fill the path, using the [nonzero winding number rule](http://en.wikipedia.org/wiki/Nonzero-rule) to determine the region to fill. Any subpaths that are open shall be implicitly closed before being filled.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
* [https://github.com/mozilla/pdf.js/.../src/core/evaluator.js#L2845-L2846](https://github.com/mozilla/pdf.js/blob/842e9206c059d36b9592e1e1b214985da6b57170/src/core/evaluator.js#L2845-L2846)

### 23: eoFill (`f*`)
#### Operands
*none*

#### PDF Specification
Fill the path, using the [even-odd rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule). to determine the region to fill.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
* 

### 24: fillStroke (`B`)
#### Operands
*none*

#### PDF Specification
[Fill](#22-fill) and then [stroke](#20-stroke-s) the path, using the [nonzero winding number rule](http://en.wikipedia.org/wiki/Nonzero-rule) to determine the region to fill. This operator  shall produce the same result as constructing two identical path objects, painting the first with `f` and the second with `S`.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
*

### 25: eoFillStroke (`B*`)
#### Operands
*none*

#### PDF Specification
[Fill](#23-eofill) and then [stroke](#20-stroke-s) the path, using the [even-odd rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule) to determine the region to fill. This operator shall produce the same result as `B`, except that the path is  filled  as  if  with `f*` instead of `f`.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
*

### 26: closeFillStroke (`b`)
#### Operands
*none*

#### PDF Specification
[Close](#18-closepath-h), [fill](#22-fill), and then [stroke](#20-stroke-s) the path, using the [nonzero winding number rule](http://en.wikipedia.org/wiki/Nonzero-rule) to determine the region to fill. This operator shall have the same effect as the sequence `h B`.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
* 

### 27: closeEOFillStroke (`b*`)
#### Operands
*none*

#### PDF Specification
[Close](#18-closepath-h), [fill](#23-eofill), and then [stroke](#20-stroke-s) the path, using the [even-odd rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule) to determine the region to fill. This operator shall have the same effect as the sequence `h B*`.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
* 

### 28: endPath (`n`)
#### Operands
*none*

#### PDF Specification
End the path object without filling or stroking it. This operator shall be a path-painting no-op, used primarily for  the side effect of changing the current clipping path.

#### Source
* [PDF Specification / Table 60 – Path-Painting Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.3987646)
*

### 29: clip (`W`)
#### Operands
*none*

#### PDF Specification
Modify the current clipping path by intersecting it with the current path, using the [nonzero winding number rule](http://en.wikipedia.org/wiki/Nonzero-rule) to determine which regions lie inside the clipping path. 

#### Source
* [PDF Specification / Table 61 – Clipping Path Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1850168)
*

### 30: eoClip (`W*`)
#### Operands
*none*

#### PDF Specification
Modify the current clipping path by intersecting it with the current path, using the [even-odd rule](http://en.wikipedia.org/wiki/Even%E2%80%93odd_rule) to determine which regions lie inside the clipping path.

#### Source
* [PDF Specification / Table 61 – Clipping Path Operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G7.1850168)
*

### 31: beginText (`BT`)
#### Operands
*none*

#### PDF Specification
Begin a text object, initializing the text matrix and the text line matrix to the identity matrix. Text objects shall not be nested; a second **`BT`** shall not appear before an **`ET`**. 

#### Source
* [PDF Specification / Table 107 – Text object operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958458)
* 

### 32: endText (`ET`)
#### Operands
*none*

#### PDF Specification
End a text object, discarding the text matrix.

#### Source
* [PDF Specification / Table 107 – Text object operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958458)
*

### 33: setCharSpacing (`Tc`)
#### Operands
* `charSpace`: *`number`*

#### PDF Specification
Set the character spacing to `charSpace`, which shall be a number expressed in unscaled text space units. Character spacing shall be used by the **`Tj`**, **`TJ`**, and **`'`** operators. Initial value: `0`. 

#### Source
* [PDF Specification / Table 105 – Text state operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454)
*

### 34: setWordSpacing (`Tw`)
#### Operands
* `wordSpace`: *`number`*

#### Source
* [PDF Specification / Table 105 – Text state operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454)
*

### 35: setHScale (`Tz`)
#### Operands
* `scale`: *`number`*

#### Source
* [PDF Specification / Table 105 – Text state operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454)
*

### 36: setLeading (`TL`)
#### Operands
* `leading`: *`number`*

#### Source
* [PDF Specification / Table 105 – Text state operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454)
* 

### 37: setFont (`Tf`)
#### Operands
* `font`: *`string`*
* `size`: *`number`*

#### Source
* [PDF Specification / Table 105 – Text state operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454)
*

### 38: setTextRenderingMode (`Tr`)
#### Operands
* `render`: ?

#### Source
* [PDF Specification / Table 105 – Text state operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454)
*

### 39: setTextRise (`Ts`)
#### Operands
* `rise`: ?

#### Source
* [PDF Specification / Table 105 – Text state operators](https://www.adobe.com/content/dam/acom/en/devnet/pdf/PDF32000_2008.pdf#G8.1958454)
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
