# Documentation for Mozilla's PDF.js library
## Operations
### 1: dependency
* dependencies: *array*
dependencies: list of dependency object ids

### 2: setLineWidth
* width: *number*
sets line width

### 3: setLineCap
* style: *number* - either 0 (butt), 1 (round), or 2 (square)
sets line cap style; determines how the end points of every line are drawn; can be either 0, 1, or 2:
* 0 = "butt"
* 1 = "round"
* 2 = "square"

see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineCap

### 4: setLineJoin
* style: *number* - either 0 (miter), 1 (round), or 2 (bevel)
sets line join style; determines how two connecting segments (of lines, arcs or curves) with non-zero lengths in a shape are joined together; can be either 0, 1, or 2:
* 0 = "miter"
* 1 = "round"
* 2 = "bevel"

see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin

### 5: setMiterLimit
* limit: *number*
sets the miter limit ratio in space units

see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/miterLimit

### 6: setDash
* dashArray: *array*
* dashPhase: *number*
sets the line dash pattern used when stroking lines, using an array of values which specify alternating lengths of lines and gaps which describe the pattern
* dashArray: An Array of numbers which specify distances to alternately draw a line and a gap (in coordinate space units). If the number of elements in the array is odd, the elements of the array get copied and concatenated; see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setLineDash
* dashPhase: A float specifying the amount of the offset; see also: https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset

### 7: setRenderingIntent
* intent: ?
unsure what it does. see: https://github.com/mozilla/pdf.js/blob/66ffdc4c5b63a135f201508264761fce17c08059/src/display/canvas.js#L888

### 8: setFlatness(flatness: ?)
unsure what it does. see: https://github.com/mozilla/pdf.js/blob/66ffdc4c5b63a135f201508264761fce17c08059/src/display/canvas.js#L893

### 9: setGState(states: array)

### 10: save()

### 11: restore()

### 12: transform(horizScaling: number, horizSkewing: number, vertSkewing: number, vertScaling: number, horizMoving: number,  vertMoving: number)

### 13: moveTo //

### 14: lineTo //

### 15: curveTo(/* ??? */) //

### 16: curveTo2(/* ??? */) //

### 17: curveTo3(/* ??? */) //

### 18: closePath(/* ??? */) //

### 19: rectangle(/* ??? */) //
  stroke(consumePath) {}
  closeStroke() {}
  fill(consumePath) {}
  eoFill() {}
  fillStroke() {}
  eoFillStroke() {}
  closeFillStroke() {}
  closeEOFillStroke() {}
  endPath() {}
  clip() {}
  eoClip() {}
  beginText() {}
  endText() {}
  setCharSpacing(spacing) {}
  setWordSpacing(spacing) {}
  setHScale(scale) {}
  setLeading(leading) {}
  setFont(fontRefName, size) {}
  setTextRenderingMode(mode) {}
  setTextRise(rise) {}
  moveText(x, y) {}
  setLeadingMoveText(x, y) {}
  setTextMatrix(hScaling, hSkewing, vSkewing,
    vScaling, hMoving,  vMoving) {}
  nextLine() {}
  showText(glyphs) {}
  showSpacedText: 45, // ??
  nextLineShowText: 46, // ??
  nextLineSetSpacingShowText: 47, // ??
  setCharWidth(xWidth, yWidth) {}
  setCharWidthAndBounds(xWidth, yWidth, llx, lly, urx, ury)
  setStrokeColorSpace: 50, // ??
  setFillColorSpace: 51, // ??
  setStrokeColor: 52, // ??
  setStrokeColorN() {}
  setFillColor: 54, // ??
  setFillColorN() {}
  setStrokeGray: 56, // ??
  setFillGray: 57, // ??
  setStrokeRGBColor(r, g, b) {}
  setFillRGBColor(r, g, b) {}
  setStrokeCMYKColor: 60, // ??
  setFillCMYKColor: 61, // ??
  shadingFill(patternIR) {}
  beginInlineImage() {} // unreachable
  beginImageData() {} // unreachable
  endInlineImage: 65, // ??
  paintXObject() {} // unsupported
  markPoint(tag) {} // todo
  markPointProps(tag, properties) {} // todo
  beginMarkedContent(tag) {} // todo
  beginMarkedContentProps(tag, properties) {} // todo
  endMarkedContent() {} // todo
  beginCompat() {} // compatibility
  endCompat() {} // compatibility
  paintFormXObjectBegin(matrix, bbox) {}
  paintFormXObjectEnd() {}
  beginGroup(group) {}
  endGroup(group) {}
  beginAnnotations() {}
  endAnnotations() {}
  beginAnnotation(rect, transform, matrix) {}
  endAnnotation() {}
  paintJpegXObject(objId, w, h) {}
  paintImageMaskXObject(img) {}
  paintImageMaskXObjectGroup(images) {}
  paintImageXObject(objId) {}
  paintInlineImageXObject(imgData) {}
  paintInlineImageXObjectGroup(imgData, map)
  paintImageXObjectRepeat(objId, scaleX, scaleY, positions) {}
  paintImageMaskXObjectRepeat(imgData, scaleX, scaleY, positions) {}
  paintSolidColorImageMask() {}
  constructPath(ops, args) {}
