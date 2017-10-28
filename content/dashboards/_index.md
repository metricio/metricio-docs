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
// You will almost alsmost need these imports
import React from 'react';
import ReactDOM from 'react-dom';
import socketIOClient from 'socket.io-client';

// This is the default stylesheet feel free to add your own
import '../styles/default.scss';

// Import the widget(s) you want to use
import NumberWidget from '../widgets/number/widget';

// Make sure each client gets a socket connection. This will allow your
// widget(s) to subscribe to data events from processed jobs
const socket = socketIOClient(`http://${window.location.host}`);

ReactDOM.render(
  <div className="dashboard">
      // Add your widgets and define your props. See widget docs for more info.
    <NumberWidget socket={socket} name="MyCatWidget" title="Catz" />
  </div>,
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
