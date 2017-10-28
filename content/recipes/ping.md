+++
title = "Ping"
+++

Below is a basic example of a job that gets a ping response time from a URL or endpoint and also how to integrate the [ping](/widgets/ping/) widget into your dashboard using the result from the job.

### Job

``` javascript
import request from 'request-promise-native';

const options = {
  resolveWithFullResponse: true,
  time: true,
  timeout: 5000,
  headers: {
    'User-Agent': 'Metricio - Ping Example',
  },
};

export const interval = '* * * * *';
export const perform = async () => {
  const google = await request(Object.assign(options, { uri: 'https://www.google.com' }));
  const reddit = await request(Object.assign(options, { uri: 'https://www.reddit.com/' }));

  return [
    {
      target: 'GooglePing',
      data: {
        status: google.statusCode,
        time: google.elapsedTime,
      },
    },
    {
      target: 'RedditPing',
      data: {
        status: reddit.statusCode,
        time: reddit.elapsedTime,
      },
    },
  ];
};

```

### Dashboard

```javascript
  import PingWidget from '../widgets/ping/widget';
```

``` html
<Ping socket={socket} name="GooglePing" title="Google" />
<Ping socket={socket} name="RedditPing" title="Reddit" />
```

Now everytime the above job completes successfully, widgets **GooglePing** and **RedditPing** will get updated with the ping response times.
