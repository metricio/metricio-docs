+++
title = "Number"
+++

The number widget can be found at  **src/widgets/number/widget.jsx**. Because the number widget is the most commonly used widget, the background colours are randomised to keep the dashboards unique. So don't be surprised if you see them change colour.

#### Usage

``` javascript
  import NumberWidget from '../widgets/number/widget';
```

``` html
  <NumberWidget
    name="MyCatWidget"
    title="Catz Conversion"
    metric="%"
  />
```

#### Props

| **Prop** | **Description** | **Required**
|:--|:--|:--|
| name | Name of widget. Used to update the widget when a job completes | Yes
| title | Title of widget. Usually displayed above the metric value | Yes
| metric | Metric to use for value passed to widget e.g. % | Optional
| format | How to format the widget value. See [Numeral](http://numeraljs.com/#format) docs. | Optional
| size | Size of the widget: *small* (default) or *medium* can be used | Optional

#### Data Stucture

When building a job for a number widget, a single value should be used e.g.

``` json
data: { value: 1.4 };
```

#### Example

![](https://res.cloudinary.com/metricio/image/upload/v1510872139/catz-conversion_tpym8o.png)
