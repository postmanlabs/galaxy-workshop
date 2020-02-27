# Liftoff

So far we have tried running collections, shared data between requests, and used some basic test scripting. In this section we will look at Postman on the command line, the Postman API, generating documentation, and collaborating in Postman.

## 1. Generate documentation

You can generate user documentation directly from your Postman collections. Documentation can include instructional text, request details, example request and response code, and code snippets in different languages.

* Open any of the collections you have in your Postman app. Click the description text—make an edit. Request details can also be set when you open a request—set the name and description for the request and parameters.
* With the collection details open, click __View in web__. By default the private view of your docs will open—you can also edit in the browser.
* By publishing your docs you can make them available at a shareable URL and promote them in the API Network along with a team listing.
* Docs can be versioned and include an environment—you can use environment variables to populate doc content (but be careful in case you expose sensitive data).

## 2. Run a collection from CLI with Newman

You can run collections from the Postman CLI Newman—which in turns facilitates integrating collection runs with your CI/CD pipeline—for example if tests fail you could set an exit flag to prevent deployment.

> In order to use **Newman**, you will need to install [Node.js](https://nodejs.org/en/download/), a package manager like [npm](https://www.npmjs.com/), and [Newman](https://github.com/postmanlabs/newman) using a command like `npm install -g newman`. _If you don't already have node and npm on your computer you might want to watch this part and get setup to try it yourself later._

* Export a collection to a local directory.
* Run `newman run collection.json`, and observe the CLI output.

We can also run a collection in Newman from a Postman account—in order to do that we need the collection ID, which we can get using the Postman API.

## 3. Use Postman API

Let's use Postman to call the Postman API so that we can get a collection ID to run via Newman.

* Import the "Postman" collection into the Postman app from the API Network.
* Retrieve your Postman API key. Toggle to __Browse__ mode using the switch at the bottom of the Postman app. Select __Integrations__ and navigate to the web dashboard.
* Browse integrations, find __Postman API__ and follow the instructions to generate your key.
* Back in the app, the Postman API collection has a variable called `postman_api_key`. Paste your key in there.
* In the Postman API collection, run the request `GET All Collections`. Choose a collection in the response body and copy its `uid` value.
* Insert the collection `uid` value and add a query string parameter `apikey` with the value of your Postman API Key to run the collection using Newman:

```bash
newman run https://api.getpostman.com/collections/{{collection_uid}}?apikey={{postman_api_key}}
```

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

## Recap

In this section we covered:

* Generating documentation
* Using Newman
* Using Postman API

## Additional resources

Check out the Postman docs:

* [Publishing documentation](https://learning.postman.com/docs/postman/api-documentation/documenting-your-api/)
* Automation with [Newman](https://learning.postman.com/docs/postman/collection-runs/command-line-integration-with-newman/)
* [Postman API](https://learning.postman.com/docs/postman/postman-api/intro-api/)

## Next steps

Next up let's overview some topics for further learning: __[Activate thrusters](./part4-ActivateThrusters.md)__.
