+++
title = "Text"
+++

The text widget is the most basic widget available. This widget displays text based on the output of a job, e.g. showing if you are deployed to green or blue if you do blue/green deployments.

#### Usage

``` javascript
  import TextWidget from '../widgets/text/widget';
```

``` html
  <TextWidget
    name="Deployment"
    title="Green/Blue"
  />
```

#### Props

| **Prop** | **Description** | **Required**
|:--|:--|:--|
| name | Name of widget. Used to update the widget when a job completes | Yes
| title | Title of widget. Usually displayed above the metric value | Yes
| size | Size of the widget: *small* (default) or *medium* can be used | Optional

#### Data Stucture

When building a job for a text widget, a single value should be provided e.g.

``` javascript
data: { value: 'green' };
```

#### Example

![](https://res.cloudinary.com/metricio/image/upload/v1508768794/test-widget_yqdmxd.png)
