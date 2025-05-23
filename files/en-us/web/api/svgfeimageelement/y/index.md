---
title: "SVGFEImageElement: y property"
short-title: y
slug: Web/API/SVGFEImageElement/y
page-type: web-api-instance-property
browser-compat: api.SVGFEImageElement.y
---

{{APIRef("SVG")}}

The **`y`** read-only property of the {{domxref("SVGFEImageElement")}} interface describes the vertical coordinate of the position of an SVG filter primitive as a {{domxref("SVGAnimatedLength")}}.

It reflects the {{SVGAttr("y")}} attribute of the {{SVGElement("feImage")}} element, which fetches image data from an external source and provides the pixel data as output. The attribute is a [`<length>`](/en-US/docs/Web/SVG/Guides/Content_type#length) or [`<percentage>`](/en-US/docs/Web/SVG/Guides/Content_type#percentage). The `<coordinate>` is a length in the user coordinate system that is the given distance from the origin of the filter along the y-axis. If the `y` attribute is a percent value, the property value is a relative to the height of the filter region in user coordinate system units. The default value is `0`.

## Value

An {{domxref("SVGAnimatedLength")}}.

## Example

```js
const feImage = document.querySelector("feImage");
const topPosition = feImage.y;
console.log(topPosition.baseVal.value); // the `y` value
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("SVGFEImageElement.x")}}
- [SVG tutorial: Filter effects](/en-US/docs/Web/SVG/Tutorials/SVG_from_scratch/Filter_effects)
- [SVG Filter primitive attributes](/en-US/docs/Web/SVG/Reference/Attribute#filters_attributes)
- CSS {{cssxref("blend-mode")}} data type
- CSS {{cssxref("mix-blend-mode")}} property
