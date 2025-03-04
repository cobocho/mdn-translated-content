---
title: <input type="search">
slug: Web/HTML/Element/input/search
---

{{HTMLSidebar}}

{{HTMLElement("input")}} элементы с типом **`search`** это текстовые поля разработанные для ввода пользователем поисковых запросов. Функциональность идентична элементам с типом [`text`](/ru/docs/Web/HTML/Element/input/text), но может отличаться стилизация за счёт {{Glossary("user agent")}}, а также наличием специального **не стандартизированного** события {{domxref("HTMLElement/search_event", "onsearch")}}.

{{EmbedInteractiveExample("pages/tabbed/input-search.html", "tabbed-standard")}}

| **[Value](#value)**             | A {{domxref("DOMString")}} representing the value contained in the search field.                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Events**                      | {{domxref("HTMLElement/change_event", "change")}} and {{domxref("HTMLElement/input_event", "input")}}                                                                                                                                                                                                                                                                                       |
| **Supported Common Attributes** | [`autocomplete`](/ru/docs/Web/HTML/Element/input#autocomplete), [`list`](/ru/docs/Web/HTML/Element/input#list), [`maxlength`](/ru/docs/Web/HTML/Element/input#maxlength), [`minlength`](/ru/docs/Web/HTML/Element/input#minlength), [`pattern`](/ru/docs/Web/HTML/Element/input#pattern), [`placeholder`](/ru/docs/Web/HTML/Element/input#placeholder), [`required`](/ru/docs/Web/HTML/Element/input#required), [`size`](/ru/docs/Web/HTML/Element/input#size). |
| **IDL attributes**              | `value`                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Methods**                     | {{domxref("HTMLInputElement.select", "select()")}}, {{domxref("HTMLInputElement.setRangeText", "setRangeText()")}}, {{domxref("HTMLInputElement.setSelectionRange", "setSelectionRange()")}}.                                                                                                                                                               |

## Value

The [`value`](/ru/docs/Web/HTML/Element/input#value) attribute contains a {{domxref("DOMString")}} representing the value contained in the search field. You can retrieve this using the {{domxref("HTMLInputElement.value")}} property in JavaScript.

```js
searchTerms = mySearch.value;
```

If no validation constraints are in place for the input (see [Validation](#validation) for more details), the value can be any text string or an empty string (`""`).

## Additional attributes

In addition to the attributes that operate on all {{HTMLElement("input")}} elements regardless of their type, search field inputs support the following attributes:

| Attribute                     | Description                                                                                                                         |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [`list`](#list)               | The id of the `<datalist>` element that contains the optional pre-defined autocomplete options                                        |
| [`maxlength`](#maxlength)     | The maximum number of characters the input should accept                                                                            |
| [`minlength`](#minlength)     | The minimum number of characters long the input can be and still be considered valid                                                |
| [`pattern`](#pattern)         | A regular expression the input's contents must match in order to be valid                                                           |
| [`placeholder`](#placeholder) | An exemplar value to display in the input field whenever it is empty                                                                |
| [`readonly`](#readonly)       | A Boolean attribute indicating whether or not the contents of the input should be read-only                                         |
| [`size`](#size)               | A number indicating how many characters wide the input field should be                                                              |
| [`spellcheck`](#spellcheck)   | Controls whether or not to enable spell checking for the input field, or if the default spell checking configuration should be used |

{{page("/en-US/docs/Web/HTML/Element/input/text", "list", 0, 1, 2)}}

### {{htmlattrdef("maxlength")}}

The maximum number of characters (as UTF-16 code units) the user can enter into the search field. This must be an integer value 0 or higher. If no `maxlength` is specified, or an invalid value is specified, the search field has no maximum length. This value must also be greater than or equal to the value of `minlength`.

The input will fail [constraint validation](/ru/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is greater than `maxlength` UTF-16 code units long.

### {{htmlattrdef("minlength")}}

The minimum number of characters (as UTF-16 code units) the user can enter into the search field. This must be a non-negative integer value smaller than or equal to the value specified by `maxlength`. If no `minlength` is specified, or an invalid value is specified, the search input has no minimum length.

The search field will fail [constraint validation](/ru/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is fewer than `minlength` UTF-16 code units long.

### {{htmlattrdef("pattern")}}

{{page("/en-US/docs/Web/HTML/Element/input/text", "pattern-include")}}

See the section [Specifying a pattern](#specifying_a_pattern) for details and an example.

{{page("/en-US/docs/Web/HTML/Element/input/text", "placeholder", 0, 1, 2)}}

{{page("/en-US/docs/Web/HTML/Element/input/text", "readonly", 0, 1, 2)}}

{{page("/en-US/docs/Web/HTML/Element/input/text", "size", 0, 1, 2)}}

### {{htmlattrdef("spellcheck")}}

{{page("/en-US/docs/Web/HTML/Element/input/text", "spellcheck-include")}}

## Non-standard attributes

The following non-standard attributes are available to search input fields. As a general rule, you should avoid using them unless it can't be helped.

| Attribute                         | Description                                                                                                                                                                                                                                                             |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`autocorrect`](#autocorrect)     | Whether or not to allow autocorrect while editing this input field. **Safari only.**                                                                                                                                                                                    |
| [`incremental`](#incremental)     | Whether or not to send repeated {{event("search")}} events to allow updating live search results while the user is still editing the value of the field. **WebKit and Blink only (Safari, Chrome, Opera, etc.).**                                                  |
| [`mozactionhint`](#mozactionhint) | A string indicating the type of action that will be taken when the user presses the <kbd>Enter</kbd> or <kbd>Return</kbd> key while editing the field; this is used to determine an appropriate label for that key on a virtual keyboard. **Firefox for Android only.** |
| [`results`](#results)             | The maximum number of items that should be displayed in the drop-down list of previous search queries. **Safari only.**                                                                                                                                                 |

### {{htmlattrdef("autocorrect")}} {{non-standard_inline}}

{{page("/en-US/docs/Web/HTML/Element/input/text", "autocorrect-include")}}

### {{htmlattrdef("incremental")}} {{non-standard_inline}}

The Boolean attribute `incremental` is a WebKit and Blink extension (so supported by Safari, Opera, Chrome, etc.) which, if present, tells the {{Glossary("user agent")}} to process the input as a live search. As the user edits the value of the field, the user agent sends {{event("search")}} events to the {{domxref("HTMLInputElement")}} object representing the search box. This allows your code to update the search results in real time as the user edits the search.

If `incremental` is not specified, the {{event("search")}} event is only sent when the user explicitly initiates a search (such as by pressing the <kbd>Enter</kbd> or <kbd>Return</kbd> key while editing the field).

The `search` event is rate-limited so that it is not sent more more frequently than an implementation-defined interval.

### {{htmlattrdef("mozactionhint")}} {{non-standard_inline}}

{{page("/en-US/docs/Web/HTML/Element/input/text", "mozactionhint-include")}}

### {{htmlattrdef("results")}} {{non-standard_inline}}

The `results` attribute—supported only by Safari—is a numeric value that lets you override the maximum number of entries to be displayed in the {{HTMLElement("input")}} element's natively-provided drop-down menu of previous search queries.

The value must be a non-negative decimal number. If not provided, or an invalid value is given, the browser's default maximum number of entries is used.

## Using search inputs

`<input>` elements of type `search` are very similar to those of type `text`, except that they are specifically intended for handling search terms. They are basically equivalent in behavior, but user agents may choose to style them differently by default (and, of course, sites may use stylesheets to apply custom styles to them).

### Basic example

```html
<form>
  <div>
    <input type="search" id="mySearch" name="q">
    <button>Search</button>
  </div>
</form>
```

This renders like so:

{{EmbedLiveSample("Basic_example", 600, 40)}}

`q` is the most common `name` given to search inputs, although it's not mandatory. When submitted, the data name/value pair sent to the server will be `q=searchterm`.

> **Примечание:** You must remember to set a [`name`](/ru/docs/Web/HTML/Element/input#name) for your input, otherwise nothing will be submitted.

### Differences between search and text types

The main basic differences come in the way browsers handle them. The first thing to note is that some browsers show a cross icon that can be clicked on to remove the search term instantly if desired. The following screenshot comes from Chrome:

![](chrome-cross-icon.png)

In addition, modern browsers also tend to automatically store search terms previously entered across domains, which then come up as autocomplete options when subsequent searches are performed in search inputs on that domain. This helps users who tend to do searches on the same or similar search queries over time. This screenshot is from Firefox:

![](firefox-auto-complete.png)At this point, let's look at some useful techniques you can apply to your search forms.

### Setting placeholders

You can provide a useful placeholder inside your search input that could give a hint on what to do using the [`placeholder`](/ru/docs/Web/HTML/Element/input#placeholder) attribute. Look at the following example:

```html
<form>
  <div>
    <input type="search" id="mySearch" name="q"
     placeholder="Search the site...">
    <button>Search</button>
  </div>
</form>
```

You can see how the placeholder is rendered below:

{{EmbedLiveSample("Setting_placeholders", 600, 40)}}

### Search form labels and accessibility

One problem with search forms is their accessibility; a common design practice is not to provide a label for the search field (although there might be a magnifying glass icon or similar), as the purpose of a search form is normally fairly obvious for sighted users due to placement ([this example shows a typical pattern](https://mdn.github.io/learning-area/accessibility/aria/website-aria-roles/)).

This could, however, cause confusion for screenreader users, since they will not have any verbal indication of what the search input is. One way around this that won't impact on your visual design is to use [WAI-ARIA](/ru/docs/Learn/Accessibility/WAI-ARIA_basics) features:

- A `role` attribute of value `search` on the `<form>` element will cause screenreaders to announce that the form is a search form.
- If that isn't enough, you can use an `aria-label` attribute on the {{HTMLElement("input")}} itself. This should be a descriptive text label that will be read out by the screenreader; it's used as a non-visual equivalent to `<label>`.

Let's have a look at an example:

```html
<form role="search">
  <div>
    <input type="search" id="mySearch" name="q"
     placeholder="Search the site..."
     aria-label="Search through site content">
    <button>Search</button>
  </div>
</form>
```

You can see how this is rendered below:

{{EmbedLiveSample("Search_form_labels_and_accessibility", 600, 40)}}

There is no visual difference from the previous example, but screenreader users have way more information available to them.

> **Примечание:** See [Signposts/Landmarks](/ru/docs/Learn/Accessibility/WAI-ARIA_basics#SignpostsLandmarks) for more information about such accessibility features.

### Physical input element size

The physical size of the input box can be controlled using the [`size`](/ru/docs/Web/HTML/Element/input#size) attribute. With it, you can specify the number of characters the input box can display at a time. In this example, for instance, the search box is 30 characters wide:

```html
<form>
  <div>
    <input type="search" id="mySearch" name="q"
    placeholder="Search the site..." size="30">
    <button>Search</button>
  </div>
</form>
```

The result is this wider input box:

{{ EmbedLiveSample('Physical_input_element_size', 600, 40) }}

## Validation

`<input>` elements of type `search` have the same validation features available to them as regular `text` inputs. It is less likely that you'd want to use validation features in general for search boxes. In many cases, users should just be allowed to search for anything, but there are a few cases to consider, such as searches against data of a known format.

> **Примечание:** HTML form validation is _not_ a substitute for scripts that ensure that the entered data is in the proper format. It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to simply bypass your HTML entirely and submit the data directly to your server. If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data (or data which is too large, is of the wrong type, and so forth) is entered into your database.

### A note on styling

There are useful pseudo-classes available for styling valid/invalid form elements: {{cssxref(":valid")}} and {{cssxref(":invalid")}}. In this section, we'll use the following CSS, which will place a check (tick) next to inputs containing valid values, and a cross next to inputs containing invalid values.

```css
input:invalid ~ span:after {
    content: '✖';
    padding-left: 5px;
    position: absolute;
}

input:valid ~ span:after {
    content: '✓';
    padding-left: 5px;
    position: absolute;
}
```

The technique also requires a {{htmlelement("span")}} element to be placed after the form element, which acts as a holder for the icons. This was necessary because some input types on some browsers don't display icons placed directly after them very well.

### Making input required

You can use the [`required`](/ru/docs/Web/HTML/Element/input#required) attribute as an easy way of making entering a value required before form submission is allowed:

```html
<form>
  <div>
    <input type="search" id="mySearch" name="q"
    placeholder="Search the site..." required>
    <button>Search</button>
    <span class="validity"></span>
  </div>
</form>
```

```css hidden
input {
  margin-right: 10px;
}

input:invalid ~ span:after {
    content: '✖';
    padding-left: 5px;
    position: absolute;
}

input:valid ~ span:after {
    content: '✓';
    padding-left: 5px;
    position: absolute;
}
```

This renders like so:

{{ EmbedLiveSample('Making_input_required', 600, 40) }}

In addition, if you try to submit the form with no search term entered into it, the browser will show a message. The following example is from Firefox:

![form field with attached message that says Please fill out this field](firefox-required-message.png)

Different messages will be shown when you try to submit the form with different types of invalid data contained inside the inputs; see the below examples.

### Input value length

You can specify a minimum length, in characters, for the entered value using the [`minlength`](/ru/docs/Web/HTML/Element/input#minlength) attribute; similarly, use [`maxlength`](/ru/docs/Web/HTML/Element/input#maxlength) to set the maximum length of the entered value.

The example below requires that the entered value be 4–8 characters in length.

```html
<form>
  <div>
    <label for="mySearch">Search for user</label>
    <input type="search" id="mySearch" name="q"
    placeholder="User IDs are 4–8 characters in length" required
    size="30" minlength="4" maxlength="8">
    <button>Search</button>
    <span class="validity"></span>
  </div>
</form>
```

```css hidden
input {
  margin-right: 10px;
}

input:invalid ~ span:after {
    content: '✖';
    padding-left: 5px;
    position: absolute;
}

input:valid ~ span:after {
    content: '✓';
    padding-left: 5px;
    position: absolute;
}
```

This renders like so:

{{ EmbedLiveSample('Input_value_length', 600, 40) }}

If you try to submit the form with less than 4 characters, you'll be given an appropriate error message (which differs between browsers). If you try to go beyond 8 characters in length, the browser won't let you.

### Specifying a pattern

You can use the [`pattern`](/ru/docs/Web/HTML/Element/input#pattern) attribute to specify a regular expression that the inputted value must follow to be considered valid (see [Validating against a regular expression](/ru/docs/Learn/HTML/Forms/Form_validation#Validating_against_a_regular_expression) for a simple crash course).

Let's look at an example. Say we wanted to provide a product ID search form, and the IDs were all codes of two letters followed by four numbers. The following example covers it:

```html
<form>
  <div>
    <label for="mySearch">Search for product by ID:</label>
    <input type="search" id="mySearch" name="q"
    placeholder="two letters followed by four numbers" required
    size="30" pattern="[A-z]{2}[0-9]{4}">
    <button>Search</button>
    <span class="validity"></span>
  </div>
</form>
```

```css hidden
input {
  margin-right: 10px;
}

input:invalid ~ span:after {
    content: '✖';
    padding-left: 5px;
    position: absolute;
}

input:valid ~ span:after {
    content: '✓';
    padding-left: 5px;
    position: absolute;
}
```

This renders like so:

{{ EmbedLiveSample('Specifying_a_pattern', 600, 40) }}

## Examples

You can see a good example of a search form used in context at our [website-aria-roles](https://github.com/mdn/learning-area/tree/master/accessibility/aria/website-aria-roles) example ([see it live](http://mdn.github.io/learning-area/accessibility/aria/website-aria-roles/)).

## Specifications

| Specification                                                                                                                                                            | Status                           | Comment            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------- | ------------------ |
| {{SpecName('HTML WHATWG', 'input.html#text-(type=text)-state-and-search-state-(type=search)', '&lt;input type="search"&gt;')}} | {{Spec2('HTML WHATWG')}} | Initial definition |
| {{SpecName('HTML5.1', 'sec-forms.html#text-typetext-state-and-search-state-typesearch', '&lt;input type="search"&gt;')}}         | {{Spec2('HTML5.1')}}     | Initial definition |

## Browser compatibility

{{Compat}}

## See also

- [HTML Forms](/ru/docs/Learn/HTML/Forms)
- {{HTMLElement("input")}} and the {{domxref("HTMLInputElement")}} interface it's based upon
- [`<input type="text">`](/ru/docs/Web/HTML/Element/input/text)
- [Compatibility of CSS properties](/ru/docs/Learn/HTML/Forms/Property_compatibility_table_for_form_widgets)
