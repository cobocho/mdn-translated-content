---
title: <th>
slug: Web/HTML/Element/th
---

{{HTMLSidebar}}

The **HTML `<th>` element** defines a cell as header of a group of table cells. The exact nature of this group is defined by the [`scope`](/ko/docs/Web/HTML/Element/th#scope) and [`headers`](/ko/docs/Web/HTML/Element/th#headers) attributes.

{{EmbedInteractiveExample("pages/tabbed/th.html","tabbed-taller")}}

<p class="hidden">The source for this interactive example is stored in a GitHub repository. If you'd like to contribute to the interactive examples project, please clone <a href="https://github.com/mdn/interactive-examples">https://github.com/mdn/interactive-examples </a>and send us a pull request.</p>

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ko/docs/Web/Guide/HTML/Content_categories"
          >Content categories</a
        >
      </th>
      <td>None.</td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/ko/docs/Web/Guide/HTML/Content_categories#Flow_content"
          >Flow content</a
        >, but with no header, footer, sectioning content, or heading content
        descendants.
      </td>
    </tr>
    <tr>
      <th scope="row">Tag omission</th>
      <td>
        The start tag is mandatory.<br />The end tag may be omitted, if it is
        immediately followed by a {{HTMLElement("th")}} or
        {{HTMLElement("td")}} element or if there are no more data in its
        parent element.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted parents</th>
      <td>A {{HTMLElement("tr")}} element.</td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>Any</td>
    </tr>
    <tr>
      <th scope="row">DOM interface</th>
      <td>{{domxref("HTMLTableHeaderCellElement")}}</td>
    </tr>
  </tbody>
</table>

## Attributes

This element includes the [global attributes](/ko/docs/Web/HTML/Global_attributes).

- {{htmlattrdef("abbr")}}
  - : This attribute contains a short abbreviated description of the cell's content. Some user-agents, such as speech readers, may present this description before the content itself.
- {{htmlattrdef("align")}} {{deprecated_inline}}

  - : This enumerated attribute specifies how the cell content's horizontal alignment will be handled. Possible values are:

    - `left`: The content is aligned to the left of the cell.
    - `center`: The content is centered in the cell.
    - `right`: The content is aligned to the right of the cell.
    - `justify` (with text only): The content is stretched out inside the cell so that it covers its entire width.
    - `char` (with text only): The content is aligned to a character inside the `<th>` element with minimal offset. This character is defined by the [`char`](/ko/docs/Web/HTML/Element/th#char) and [`charoff`](/ko/docs/Web/HTML/Element/th#charoff) attributes.

    The default value when this attribute is not specified is `left`.

    > **참고:**Do not use this attribute as it is obsolete in the latest standard.- To achieve the same effect as the `left`, `center`, `right` or `justify` values, apply the CSS {{cssxref("text-align")}} property to the element.
    >
    > - To achieve the same effect as the `char` value, give the {{cssxref("text-align")}} property the same value you would use for the [`char`](/ko/docs/Web/HTML/Element/th#char). {{unimplemented_inline}} in CSS3.

- {{htmlattrdef("axis")}} {{deprecated_inline}}

  - : This attribute contains a list of space-separated strings. Each string is the `id` of a group of cells that this header applies to.

    > **참고:** Do not use this attribute as it is obsolete in the latest standard: use the [`scope`](/ko/docs/Web/HTML/Element/th#scope) attribute instead.

- {{htmlattrdef("bgcolor")}} {{Non-standard_inline}}

  - : This attribute defines the background color of each cell in a column. It consists of a 6-digit hexadecimal code as defined in [sRGB](https://www.w3.org/Graphics/Color/sRGB) and is prefixed by '#'. This attribute may be used with one of sixteen predefined color strings:

    |     | `black` = "#000000"   |     | `green` = "#008000"  |
    | --- | --------------------- | --- | -------------------- |
    |     | `silver` = "#C0C0C0"  |     | `lime` = "#00FF00"   |
    |     | `gray` = "#808080"    |     | `olive` = "#808000"  |
    |     | `white` = "#FFFFFF"   |     | `yellow` = "#FFFF00" |
    |     | `maroon` = "#800000"  |     | `navy` = "#000080"   |
    |     | `red` = "#FF0000"     |     | `blue` = "#0000FF"   |
    |     | `purple` = "#800080"  |     | `teal` = "#008080"   |
    |     | `fuchsia` = "#FF00FF" |     | `aqua` = "#00FFFF"   |

    > **참고:** Do not use this attribute, as it is non-standard and only implemented in some versions of Microsoft Internet Explorer: The {{HTMLElement("th")}} element should be styled using [CSS](/ko/docs/Web/CSS). To create a similar effect use the {{cssxref("background-color")}} property in [CSS](/ko/docs/Web/CSS) instead.

- {{htmlattrdef("char")}} {{deprecated_inline}}

  - : The content in the cell element is aligned to a character. Typical values include a period (.) to align numbers or monetary values. If [`align`](/ko/docs/Web/HTML/Element/th#align) is not set to `char`, this attribute is ignored.

    > **참고:** Do not use this attribute as it is obsolete in the latest standard. To achieve the same effect, you can specify the character as the first value of the {{cssxref("text-align")}} property, {{unimplemented_inline}} in CSS3.

- {{htmlattrdef("charoff")}} {{deprecated_inline}}

  - : This attribute is used to shift column data to the right of the character specified by the **char** attribute. Its value specifies the length of this shift.

    > **참고:**Do not use this attribute as it is obsolete in the latest standard.

- {{htmlattrdef("colspan")}}
  - : This attribute contains a non-negative integer value that indicates for how many columns the cell extends. Its default value is `1`. Values higher than 1000 will be considered as incorrect and will be set to the default value (1).
- {{htmlattrdef("headers")}}
  - : This attribute contains a list of space-separated strings, each corresponding to the **id** attribute of the {{HTMLElement("th")}} elements that apply to this element.
- {{htmlattrdef("height")}} {{deprecated_inline}}

  - : This attribute is used to define a recommended cell height.

    > **참고:**Do not use this attribute as it is obsolete in the latest standard: use the CSS {{cssxref("height")}} property instead.

- {{htmlattrdef("rowspan")}}
  - : This attribute contains a non-negative integer value that indicates for how many rows the cell extends. Its default value is `1`; if its value is set to `0`, it extends until the end of the table section ({{HTMLElement("thead")}}, {{HTMLElement("tbody")}}, {{HTMLElement("tfoot")}}, even if implicitly defined), that the cell belongs to. Values higher than 65534 are clipped down to 65534.
- {{htmlattrdef("scope")}}

  - : This enumerated attribute defines the cells that the header (defined in the {{HTMLElement("th")}}) element relates to. It may have the following values:

    - `row`: The header relates to all cells of the row it belongs to.
    - `col`: The header relates to all cells of the column it belongs to.
    - `rowgroup`: The header belongs to a rowgroup and relates to all of its cells. These cells can be placed to the right or the left of the header, depending on the value of the [`dir`](/ko/docs/Web/HTML/Global_attributes/dir) attribute in the {{HTMLElement("table")}} element.
    - `colgroup`: The header belongs to a colgroup and relates to all of its cells.
    - `auto`

    The default value when this attribute is not specified is `auto`.

- {{htmlattrdef("valign")}} {{deprecated_inline}}

  - : This attribute specifies how a text is vertically aligned inside a cell. Possible values for this attribute are:

    - `baseline`: Positions the text near the bottom of the cell and aligns it with the [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29) of the characters instead of the bottom. If characters don't descend below the baseline, the baseline value achieves the same effect as `bottom`.
    - `bottom`: Positions the text near the bottom of the cell.
    - `middle`: Centers the text in the cell.
    - and `top`: Positions the text near the top of the cell.

    > **참고:** Do not use this attribute as it is obsolete in the latest standard: use the CSS {{cssxref("vertical-align")}} property instead.

- {{htmlattrdef("width")}} {{deprecated_inline}}

  - : This attribute is used to define a recommended cell width. Additional space can be added with the {{domxref("HTMLTableElement.cellSpacing", "cellspacing")}} and {{domxref("HTMLTableElement.cellPadding", "cellpadding")}} properties and the width of the {{HTMLElement("col")}} element can also create extra width. But, if a column's width is too narrow to show a particular cell properly, it will be widened when displayed.

    > **참고:** Do not use this attribute as it is obsolete in the latest standard: use the CSS {{cssxref("width")}} property instead.

## Examples

See {{HTMLElement("table")}} for examples on `<th>`.

## 명세서

{{Specifications}}

## 브라우저 호환성

{{Compat}}

## See also

- Other table-related HTML Elements: {{HTMLElement("caption")}}, {{HTMLElement("col")}}, {{HTMLElement("colgroup")}}, {{HTMLElement("table")}}, {{HTMLElement("tbody")}}, {{HTMLElement("td")}}, {{HTMLElement("tfoot")}}, {{HTMLElement("thead")}}, {{HTMLElement("tr")}}.
