+++
title = "Build Status"
+++

The build status widget is designed to show the outcome of a build process. Usually as part of a continuous integration process. The widget has two design states **success** and **fail**. Success is **green** and fail is **red**. Any other state is **blue** e.g. pending or running.

#### Usage
``` javascript
  import BuildStatusWidget from '../widgets/build-status/widget';
```
``` html
  <BuildStatusWidget
    name="DemoMaster"
    title="Build - Master"
    size="medium"
  />
```

#### Props

| **Prop** | **Description** | **Required**
|:--|:--|:--|
| name | Name of widget. Used to update the widget when a job completes | Yes
| title | Title of widget. Usually displayed above the outcome value | Yes
| size | Size of the widget: *small* (default) or *medium* can be used | Optional

#### Data Stucture

When building a job for the build-status widget, a single value should be used e.g.

``` javascript
// Successfull build
data: { outcome: 'success' };

// Failed build
data: { outcome: 'fail' };
```

#### Example

![](https://res.cloudinary.com/metricio/image/upload/v1508768124/ci-success_mwot07.png)
![](https://res.cloudinary.com/metricio/image/upload/v1508768123/ci-fail_m7aodc.png)
![](https://res.cloudinary.com/metricio/image/upload/v1508768123/ci-pending_sshk5p.png)

{{% notice note %}}
Sizes will vary as widgets are responsive to the viewport
{{% /notice %}}
