+++
title = "Ping"
+++

The ping widget is used to display the outcome of a request to an API endpoint or website and report whether the response was a 200 and how long it took to get that response. If the response was 200, then the widget will remain **orange**. However, if the response is anything other than 200 the widget will be **red**.

#### Usage

``` javascript
  import PingWidget from '../widgets/ping/widget';
```

``` html
  <PingWidget
    socket={socket}
    name="GooglePing"
    title="Google"
  />
```

#### Props

| **Prop** | **Description** | **Required**
|:--|:--|:--|
| socket | Socket that widget should use for updates | Yes
| name | Name of widget. Used to update the widget when a job completes | Yes
| title | Title of widget. Usually displayed above the metric value | Yes
| size | Size of the widget: *small* (default) or *medium* can be used | Optional

#### Data Stucture

When building a job for a ping widget, a status value and and time value should be sent e.g.

``` javascript
  // Successful
  data: {
    status: 200, // HTTP Status Code
    time: 726, // Request Time (ms)
  }

  // Failed
  data: {
    status: 500,
    time: 0,
  }
```

#### Example

![](https://res.cloudinary.com/metricio/image/upload/v1508770493/ping-successfull_cbrs7o.png)
![](https://res.cloudinary.com/metricio/image/upload/v1508770492/ping-down_xnlyld.png)
