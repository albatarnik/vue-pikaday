# About:

A lightweight VueJs component wrapper for [Pikaday](https://github.com/Pikaday/Pikaday)

[![NPM version][npm-image]][npm-url]
[![License][license-image]][license-url]

<!-- [![Downloads][downloads-image]][downloads-url] -->

### Higly customizable Pikaday Vue Component

- Simple and Lightweight
- Dependencies: Pikaday and [Moment.js][moment]
- Same configuration of Pikaday can be applied.

![Pikaday Screenshot][screenshot]

## Install

You can install it via npm:

```sh
npm i light-vue-pikaday
```

Then where you want to use the pikaday, you should import and register the component.

```js
import PikadayPicker from "light-vue-pikaday";

// register the component
components: {
  PikadayPicker;
}
```

Then you can simply place the component where you want

```vuejs
<pikaday-picker value="2020-03-20"></pikaday-picker>
```

### Example:

```vuejs

<template>
  <div id="app">
    <pikaday-picker :value="value" format="DD/MM/YYYY" :options="options"></pikaday-picker>
  </div>
</template>

<script>
import PikadayPicker from "light-vue-pikaday";
export default {
  name: "app",

  data() {
    return {
      value: "08/03/1994",
      options: {
        disableWeekends: true,
        yearRange: [1990, 2000]
      }
    };
  },
  components: {
    PikadayPicker
  }
};
</script>

```

## Pikaday Component Props:

`pikaday-picker` accepets the following props:

### value

`required`
It's the default value of the date picker.

### format

`optional`

`default`: `YYYY-MM-DD`

Any [Moment.js][moment] format can be used

### options

`optional`

`default`: `{}`

Object that can have any configuration that [Pikaday](https://github.com/Pikaday/Pikaday) has.

These are a list of configuration that you can pass, source: [Pikaday](https://github.com/Pikaday/Pikaday)

- `field` bind the datepicker to a form field
- `trigger` use a different element to trigger opening the datepicker, see [trigger example][] (default to `field`)
- `bound` automatically show/hide the datepicker on `field` focus (default `true` if `field` is set)
- `ariaLabel` data-attribute on the input field with an aria assistance tekst (only applied when `bound` is set)
- `position` preferred position of the datepicker relative to the form field, e.g.: `top right`, `bottom right` **Note:** automatic adjustment may occur to avoid datepicker from being displayed outside the viewport, see [positions example][] (default to 'bottom left')
- `reposition` can be set to false to not reposition datepicker within the viewport, forcing it to take the configured `position` (default: true)
- `container` DOM node to render calendar into, see [container example][] (default: undefined)
- `formatStrict` the default flag for moment's strict date parsing
- `toString(date, format)` function which will be used for custom formatting. This function will take precedence over `moment`.
- `parse(dateString, format)` function which will be used for parsing input string and getting a date object from it. This function will take precedence over `moment`.
- `defaultDate` the initial date to view when first opened
- `setDefaultDate` Boolean (true/false). make the `defaultDate` the initial selected value
- `firstDay` first day of the week (0: Sunday, 1: Monday, etc)
- `minDate` the minimum/earliest date that can be selected (this should be a native Date object - e.g. `new Date()` or `moment().toDate()`)
- `maxDate` the maximum/latest date that can be selected (this should be a native Date object - e.g. `new Date()` or `moment().toDate()`)
- `disableWeekends` disallow selection of Saturdays or Sundays
- `disableDayFn` callback function that gets passed a Date object for each day in view. Should return true to disable selection of that day.
- `yearRange` number of years either side (e.g. `10`) or array of upper/lower range (e.g. `[1900,2015]`)
- `showWeekNumber` show the ISO week number at the head of the row (default `false`)
- `pickWholeWeek` select a whole week instead of a day (default `false`)
- `isRTL` reverse the calendar for right-to-left languages
- `i18n` language defaults for month and weekday names (see internationalization below)
- `yearSuffix` additional text to append to the year in the title
- `showMonthAfterYear` render the month after year in the title (default `false`)
- `showDaysInNextAndPreviousMonths` render days of the calendar grid that fall in the next or previous months (default: false)
- `enableSelectionDaysInNextAndPreviousMonths` allows user to select date that is in the next or previous months (default: false)
- `numberOfMonths` number of visible calendars
- `mainCalendar` when `numberOfMonths` is used, this will help you to choose where the main calendar will be (default `left`, can be set to `right`). Only used for the first display or when a selected date is not already visible
- `events` array of dates that you would like to differentiate from regular days (e.g. `['Sat Jun 28 2017', 'Sun Jun 29 2017', 'Tue Jul 01 2017',]`)
- `theme` define a classname that can be used as a hook for styling different themes, see [theme example][] (default `null`)
- `blurFieldOnSelect` defines if the field is blurred when a date is selected (default `true`)
- `onSelect` callback function for when a date is selected
- `onOpen` callback function for when the picker becomes visible
- `onClose` callback function for when the picker is hidden
- `onDraw` callback function for when the picker draws a new month
- `keyboardInput` enable keyboard input support (default `true`)

## License

[MIT][license-url] © [Kamal Albatarni][author]

<!-- Definitions -->

[npm-image]: https://img.shields.io/npm/v/light-vue-pikaday.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/light-vue-pikaday
[license-image]: https://img.shields.io/:license-mit-blue.svg?style=flat-square
[license-url]: LICENSE.md
[screenshot]: https://raw.github.com/Pikaday/Pikaday/master/examples/screenshot.png "Screenshot"
[downloads-image]: http://img.shields.io/npm/dm/light-vue-pikaday.svg?style=flat-square
[moment]: http://momentjs.com/
[downloads-url]: https://npmjs.org/package/light-vue-pikaday
[positions example]: https://pikaday.com/examples/positions.html "Pikaday using different position options"
[container example]: https://pikaday.com/examples/container.html "Pikaday using custom calendar container"
[author]: https://kamal.guru
[wiki]: https://wikipedia.org/wiki/Linked_list
