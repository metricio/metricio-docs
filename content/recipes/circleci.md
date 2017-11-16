+++
title = "CircleCI"
+++

Below is a basic example of a job to get your build status from CircleCI and then how to integrate the [build status](/widgets/build-status/) widget into your dashboard using the result from the job.

### Job

``` javascript
import request from 'request-promise-native';

// Helper method to fetch a status for a branch
function getBranch(repo, branch, limit = 10) {
  const githubUser = 'GITHUB_ORG_OR_USER';
  const endpoint = 'https://circleci.com/api/v1.1/project/github';
  const options = {
    uri: `${endpoint}/${githubUser}/${repo}/tree/${branch}`,
    qs: {
      'circle-token': 'SECRET_CIRCLE_CI_TOKEN',
      offset: 0,
      limit,
    },
    headers: {
      'User-Agent': 'Metricio - CircleCI',
    },
    json: true,
  };
  return request(options);
}

// Define our interval e.g. https://crontab.guru
export const interval = '*/2 * * * *';

// Define our jobs function
export const perform = async () => {

  // Resolve promise for develop
  const develop = await getBranch('YOUR_REPO`', 'develop');

  // Resolve promise for master
  const master = await getBranch('YOUR_REPO', 'master');

  return [
    {
      target: 'BuildDevelop',
      data: {
        outcome: develop[0].outcome === null ? 'pending' : develop[0].outcome,
      },
    },
    {
      target: 'BuildMaster',
      data: {
        outcome: master[0].outcome === null ? 'pending' : master[0].outcome,
      },
    },
  ];
};
```

### Dashboard

```javascript
  import BuildStatusWidget from '../widgets/build-status/widget';
```

``` html
<BuildStatusWidget
  name="BuildDevelop"
  title="Build - Develop"
  size="medium"
/>

<BuildStatusWidget
  name="BuildMaster"
  title="Build - Master"
  size="medium"
/>
```

Now everytime the above job completes successfully, widgets **BuildMaster** and **BuildDevelop** will get updated with the latest build outcome.
