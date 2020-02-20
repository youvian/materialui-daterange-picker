# react-daterange-picker

A react date range picker implementation using @material-ui.

<a href='https://www.npmjs.com/package/materialui-daterange-picker'>
    <img src='https://img.shields.io/npm/v/materialui-daterange-picker.svg' alt='Latest npm version'>
</a>

## Live Demo

Check out the project running at https://pedro-lb.github.io/react-daterange-picker/

## Usage

```bash
npm install materialui-daterange-picker --save

# or with yarn
yarn add materialui-daterange-picker
```

![Screenshot](/screenshot.png?raw=true "Screenshot")

## Basic example using hooks
```tsx
import React from "react";
import { DateRangePicker, DateRange } from "materialui-daterange-picker";

type Props = {}

const App: React.FunctionComponent<Props> = props => {
  const [open, setOpen] = React.useState(false);
  const [dateRange, setDateRange] = React.useState<DateRange>({});

  return (
    <DateRangePicker
      open={open}
      onChange={range => setDateRange(range)}
    />
  );
}

export default App;
```


## Basic Example
```tsx
import React from "react";
import { DateRangePicker, DateRange } from "materialui-daterange-picker";

type Props = {}

type State = {
	open: boolean,
	dateRange: DateRange
}

class App extends React.Component<Props, State> {
  state = {
    open: true,
    dateRange: {}
  };

  render() {
    return (
      <DateRangePicker
        open={this.state.open}
        onChange={range => this.setState({ dateRange: range })}
      />
    );
  }
}

export default App;
```

## Types
```ts
interface DateRange {
    startDate?: Date,
    endDate?: Date
}

interface DefinedRange {
    label: string,
    startDate: Date,
    endDate: Date
}
```

## Props

Name | Type | Required | Default value | Description
:--- | :--- | :--- | :--- | :---
`onChange` | `(DateRange) => void` | _required_ | - | handler function for providing selected date range
`toggle` | `() => void` | _required_ | - | function to show / hide the DateRangePicker
`initialDateRange` | `DateRange` | | `{}` | initially selected date range
`minDate` | `Date | string` | | 10 years ago | min date allowed in range
`maxDate` | `Date | string` | | 10 years from now | max date allowed in range
`definedRanges` | `DefinedRange[]` | | - | custom defined ranges to show in the list
`definedRanges` | `DefinedRange[]` | | - | custom defined ranges to show in the list
`closeOnClickOutside` | `boolean` | | true | defines if DateRangePicker will be closed when clicking outside of it
