---
title: aria-valuemin
slug: Web/Accessibility/ARIA/Reference/Attributes/aria-valuemin
page-type: aria-attribute
spec-urls: https://w3c.github.io/aria/#aria-valuemin
sidebar: accessibilitysidebar
---

The `aria-valuemin` attribute defines the minimum allowed value for a range widget.

## Description

The `aria-valuemin` attribute defines the minimum value allowed for range widgets. It is similar to the `min` attribute of {{HTMLElement('progress')}}, {{HTMLElement('meter')}}, and {{HTMLElement('input')}} of type [`range`](/en-US/docs/Web/HTML/Reference/Elements/input/range), [`number`](/en-US/docs/Web/HTML/Reference/Elements/input/number) and all the date-time types.

When creating a range type role, including [`meter`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/meter_role), [`scrollbar`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/scrollbar_role), [`slider`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/slider_role), and [`spinbutton`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/spinbutton_role) on a non-semantic element, the `aria-valuemin` enables defining a minimum that is less than the maximum value and is a required attribute of `slider`, `scrollbar` and `spinbutton`.

Declaring the minimum and maximum values allows assistive technologies to convey the size of the range to users.

The maximum value is defined with [`aria-valuemax`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-valuemax).

> [!WARNING]
> The [`range`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/range_role) role itself should **NOT** be used as it is an ["abstract"](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles#6._abstract_roles). The `aria-valuemin` attribute is used on all of the range roles subtypes.

## Values

- `<number>`
  - : A decimal number, below the maximum value.

## Associated interfaces

- {{domxref("Element.ariaValueMin")}}
  - : The [`ariaValueMin`](/en-US/docs/Web/API/Element/ariaValueMin) property, part of the {{domxref("Element")}} interface, reflects the value of the `aria-valuemin` attribute.
- {{domxref("ElementInternals.ariaValueMin")}}
  - : The [`ariaValueMin`](/en-US/docs/Web/API/ElementInternals/ariaValueMin) property, part of the {{domxref("ElementInternals")}} interface, reflects the value of the `aria-valuemin` attribute.

## Associated roles

Used in roles:

- [`meter`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/meter_role)
- [`scrollbar`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/scrollbar_role)
- [`separator`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/separator_role)
- [`slider`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/slider_role)
- [`spinbutton`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/spinbutton_role)

Inherited into roles:

- [`meter`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/meter_role)
- [`progressbar`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/progressbar_role)
- [`scrollbar`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/scrollbar_role)
- [`slider`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/slider_role)
- [`spinbutton`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/spinbutton_role)

## Specifications

{{Specifications}}

## See also

- [`range` role](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/range_role)
- [`<input type="range>` element `min` attribute](/en-US/docs/Web/HTML/Reference/Elements/input/range#min)
- [`aria-valuemax`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-valuemax)
- [`aria-valuenow`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-valuenow)
