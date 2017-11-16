+++
title = "Dashboards"
description = ""
weight = 3
+++

You can add as many dashboards as you want, as long as they are inside the **src/dashboards** folder. A dashboard must have a **.jsx** extension. All new dashboards will be available after a server restart: `http://localhost:3000/{dashboard-name-here}`.

#### Example

Create new file:

```shell
touch src/dashboards/catz.jsx
```

Add the following to `src/dashboards/catz.jsx`:

``` javascript
import React from 'react';
import ReactDOM from 'react-dom';

// This is the default stylesheet feel free to add your own
import '../styles/default.scss';

// Import the dashboard widget
import Dashboard from '../widgets/dashboard';

// Import the widgets you want to show on your dashboard
import NumberWidget from '../widgets/number/widget';

ReactDOM.render(
  <Dashboard>
    <NumberWidget name="MyCatWidget" title="Catz" />
  </Dashboard>,
  document.getElementById('content'),
);
```

Now you can run:

``` javascript
npm run start
```

and browse to `http://localhost:3000/catz`

![](https://res.cloudinary.com/metricio/image/upload/v1508761820/catz_xanftt.png)

Et voila! You are now ready to make your first job and test the other widgets available.

Head over to [jobs](/jobs) to see how add a job for this example.
