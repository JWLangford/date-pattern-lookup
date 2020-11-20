# Date Pattern Lookup

A simple library to get the date pattern for a locale. Useful if you have a date input that allows for inline editing and requires a date format / pattern to build the appropriate input mask.

### [Demo Sandbox](https://codesandbox.io/s/zen-worker-o7l9y?file=/src/App.js)

## Getting Started

### Installation

```
yarn add date-pattern-lookup
```

## Usage

```javascript
import { shortPatternLookup } from "date-pattern-lookup";
```

## Example

Below example uses the `KeyboardDatePicker` from [Material-UI pickers](https://material-ui-pickers.dev/api/KeyboardDatePicker)

```javascript
import { shortpattern } from "date-pattern-lookup";
import { KeyboardDatePicker } from "@material-ui/pickers";

function MyDatePicker() {
  const code = "en-US";
  const pattern = shortPatternLookup.get(code);
  // pattern = M/d/yyyy

  return (
    <KeyboardDatePicker
      clearable
      value={selectedDate}
      placeholder={pattern}
      onChange={(date) => handleDateChange(date)}
      format={pattern}
    />
  );
}
```

### Options

| Property           | type | Description                                            |
| ------------------ | ---- | ------------------------------------------------------ |
| shortPatternLookup | Map  | returns the short date pattern for the provided locale |
