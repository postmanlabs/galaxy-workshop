# Activate Thrusters

![Activate](./Activate.jpg)

In the last part of the session, we're going to briefly look at a few areas in more detail, including Q&A. After the session you'll still have opportunities to chat to the team about specific topics.

## 1. Visualize data

You can create test scripts that visualize response data when your requests run. Visualizations can include graphs, charts, and interactive elements using JavaScript libraries.

* Import the `Visualizer Examples` or `Visualizer Feature Templates` collections.
* Pick any request and __Send__. When the response comes back, select __Visualize__. To see the code building the visualizations, select the __Tests__ tab. You can use JavaScript visualization libraries such as D3.

**Check out the [Visualizer docs](https://learning.postman.com/docs/postman/sending-api-requests/visualizer/)**

## 2. Newman

We saw the basics of how to use Newman to access Postman on the command line earlier. Let's take a deeper dive into Newman.

* Run `newman run -h` in your terminal to see the available options. You can specify folder, environments, data files, number of iterations, request delays and timeouts, and a variety of other configurations.
* You can create and use custom reporters to suit your use case.

__Check out the [Newman docs](https://learning.postman.com/docs/postman/collection-runs/command-line-integration-with-newman/).__

## 3. API Builder

You can define and model your API using a specification inside Postman. Postman API Builder can act as the single source of truth through multiple phases of your development and testing process.

* In Postman, open __APIs__ on the left.
* You can import or write a spec, for example OpenAPI (formerly Swagger).
* You can generate collections from a spec.
* You can validate against a spec.
* You can connect various other elements to your schema, e.g. mocks, monitors, tests.

**Check out the [API Builder docs](https://learning.postman.com/docs/postman/design-and-develop-apis/the-api-workflow/)**

## Questions?

Shout out any remaining questions you have. We'll also have time for questions on an individual basis after the session.

![Postman Platform](./platform.png)

## Other topics

Follow-up topics for further learning:

* __Collaboration__
  * We saw earlier that you can create workspaces in Postman. There are various other features designed to support collaboration. You can invite people to workspaces. With paid accounts you can specify role based access control. As we saw earlier, you can use version control on APIs and collections. you can also view changelogs for collections, teams, workspaces, as well as comment and discuss. Check out the [Collaboration docs](https://learning.postman.com/docs/postman/collaboration/collaboration-intro/).
* __Mock data__
  * You can use Postman to mock data during API design or development. Mocks use examples you specify in Postman to provide test data. Open a collection and select the __Mocks__ tab. Create a new mock, giving it a name. Add examples. Use the mock server URL in your requests to return example data instead of hitting the actual API. _If you set your URL as a variable you can swap the mock URL in there while designing and developing your API._ Check out the [Mock Server docs](https://learning.postman.com/docs/postman/mock-servers/intro-to-mock-servers/).
* __Monitors__
  * We saw earlier how you can run the requests in a collection using the collection runner. You can schedule these to run and analyze performance using monitors. Open a collection and choose the __Monitors__ tab. Create a monitor and setup details including run frequency. View monitor results in the web dashboard. Check out the [Monitoring docs](https://learning.postman.com/docs/postman/monitors/intro-monitors/) for more detail.
* __GraphQL__
  * You can write GraphQL queries and specs in Postman. Import the template `Working with GraphQL` and check it out.
* __Interceptor__
  * Postman Interceptor allows you to sync cookie data for specified domains. Check out [the docs](https://learning.postman.com/docs/postman/sending-api-requests/interceptor/).
* __Codegen__
  * If you use code generation in Postman, you can customize how your code is generated using the __Settings__ &gt; __New Code Generation Mode__ option then clicking __Code__ in a request and opening the settings to configure the detail for specific languages.
* __Console__
  * The Postman Console provides debugging info you can use when troubleshooting your requests—and has recently had an upgrade. Try using `console.warn`, `console.info`, and `console.error` in your scripts.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

## Additional resources

* [Get support on the Postman community forum](https://community.getpostman.com/)
* [Check out the docs](https://learning.postman.com/docs/)
* [Explore the API Network](https://explore.postman.com/)
* [Create or comment on issues in the GitHub support repo](https://github.com/postmanlabs/postman-app-support/issues)
* [See what's coming in the public roadmap](https://trello.com/b/4N7PnHAz/postman-roadmap-for-developers)
* [Newman HTMLExtra Reporter](https://www.npmjs.com/package/newman-reporter-htmlextra)
* [Newman Reporters](https://www.npmjs.com/search?q=newman-reporter)
* [Postman CLI](https://github.com/matt-ball/postman-cli)

## Survey

Please take a few minutes to fill out the survey so that we can make future workshops as useful as possible.

__[bit.ly/postman-berlin-survey](http://bit.ly/postman-berlin-survey)__

![Survey QRCode](./QR_code_Berlin.png)

## Kahoot

__Go to [kahoot.it](https://kahoot.it/) and enter the pin show on the screen—answer the questions as quick as you can to win an Amazon gift card!__
