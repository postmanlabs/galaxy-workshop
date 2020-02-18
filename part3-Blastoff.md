# Blastoff- part 3

## [DO] Run the collection with the collection runner

1. Import the **Postman Echo** template.
1. Run the collection with the collection runner, and observe the results.
1. Filter on failed tests, and drill down into the request and response details.

## [OBSERVE] Run the collection from CLI with Newman

1. In order to use **Newman**, you will need to install [Node.js](https://nodejs.org/en/download/), a package manager like [npm](https://www.npmjs.com/), and [Newman](https://github.com/postmanlabs/newman) using a command like `npm install -g newman`.
1. Begin by exporting the Postman Echo collection to a local directory, run `newman run collection.json`, and observe the CLI output.
1. Import **Postman** collection from the API Network.
1. Retrieve your [Postman API](https://learning.postman.com/docs/postman/postman-api/intro-api/) key, and store it as an environment variable called `postman-api-key`.
1. [`GET` all collections](https://docs.api.getpostman.com/?version=latest#3190c896-4216-a0a3-aa38-a041d0c2eb72), find the Postman Echo collection in the response body, and copy the collection `uid` to your clipboard.
1. [`GET` a single collection](https://docs.api.getpostman.com/?version=latest#647806d5-492a-eded-1df6-6529b5dc685c) using the `uid` from the previous step.
1. In order to use the URL with Newman, add a query string parameter `apikey` with the value of your Postman API Key.
1. Run the collection using Newman and this entire URL, and discuss how this can be used with your Continuous Integration / Continuous Delivery (CI/CD) pipeline.

```bash
newman run https://api.getpostman.com/collections/{{collection_uid}}?apikey={{postman_api_key}}
```

## [DO] Run the collection from Postman servers with Monitor

1. Schedule a monitor to run on the Postman servers, select the frequency, regions, and other configuration options.
1. In the web dashboard, review the monitor run results.

## [DO] Do documentation

1. Write a description in markdown for a collection, folder, request, and parameter.
1. Create a team workspace, and share an existing collection to the new workspace.
1. Publish the collection publicly, customize theme, and add as a template.

## [DO] Collaboration

1. Toggle over to the **Browse** view in Postman.
1. For Postman Team users, update the role of a user for a collection in a team workspace.
1. Fork and merge a collection
1. Add a new version to the API specification (or to the collection).
1. Review the changelog for the collection, workspace, team, or user.
1. Browse available integrations.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

### Summary

1. Running a collection with Newman for CI/CD, from CLI, or as a library
1. Running a collection with monitors from Postman servers
1. Writing and sharing private and public documentation
1. Using Postman for lots and lots of collaboration

### Concepts

1. Automation with [Newman](https://learning.postman.com/docs/postman/collection-runs/command-line-integration-with-newman/) and [Monitors](https://learning.postman.com/docs/postman/monitors/intro-monitors/)
1. [Documentation](https://learning.postman.com/docs/postman/api-documentation/documenting-your-api/)
1. [Collaboration](https://learning.postman.com/docs/postman/collaboration/collaboration-intro/)

### Additional resources

1. [Postman Echo](https://explore.postman.com/templates/1358/postman-echo) template
1. [Postman API](https://explore.postman.com/team/postman)
