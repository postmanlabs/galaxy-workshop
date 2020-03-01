# Liftoff

![Liftoff](./Liftoff.jpg)

So far we have tried running collections, shared data between requests, and used some basic test scripting. In this section we will look at generating documentation, using Postman on the command line, and the Postman API.

## 1. Generate documentation

You can generate user documentation for an API directly from your Postman collections. Documentation can include instructional text and images, request details, example request and response code, and code snippets in different languages.

* Open any of the collections you have in your Postman app. Click the description text—make an edit. Request details can also be set when you open a request—set the name and description for the request and parameters.
* With the collection details open, click __View in web__. By default the private view of your docs will open—you can also edit in the browser. When you publish your docs you can share them via url and people can import the collection using the embedded Run in Postman button.
  * If you just want to use the Run in Postman on a website you can generate HTML or Markdown __Embed__ from the collection in Postman by choosing __Share__.
* Open the VIP Customers collection in the Postman app and open a GET request. Click __Examples__ and select the `Get` example. Select the collection again, open its details and choose View in Web—you'll see the examples are populated in the docs.

You can promote your docs and collections within the Postman community by listing them in the Templates and API Network when you publish. Docs can be versioned and can include an environment—_you can use variables to populate doc content (but be careful in case you expose sensitive data)_.

> To see a great demo of how you can use Postman for developer onboarding, check out the [ShipEngine Walkthrough](https://documenter.getpostman.com/view/305204/SW7XbA6V?version=latest) collection.
> * Create a free ShipEngine account and get a sandbox API key by visiting [shipengine.com/postman](https://shipengine.com/postman) (_make sure you use this link as they've kindly raised rate limits for us_).
> * Select “United States” as your country when signing up for this free account to enable the sandbox environment.
> * Add your ShipEngine key value in the collection variables as the `API_KEY` and try out the first request.

## 2. Run a collection from CLI with Newman

You can run collections from the Postman CLI Newman—which in turn facilitates integrating collection runs with your CI/CD pipeline—for example if tests fail you could set an exit flag to prevent deployment.

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
* In the Postman API collection, open the request `GET All Collections`. Open the __Authorization__ tab to see the auth scheme and that it pulls the key value from the collection variables. __Send__ the request. Choose a collection in the response body and copy its `uid` value.
* Insert the collection `uid` value and add a query string parameter `apikey` with the value of your Postman API Key to run the collection using Newman:

```bash
newman run https://api.getpostman.com/collections/collection_uid?apikey=postman_api_key
```

> The key you see on screen will be revoked immediately after the workshop—note that if you accidentally commit a Postman API key to a public repo on GitHub you will receive a notification alerting you to the leaked key.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

## Recap

In this section we covered:

* Generating documentation
* Using Newman
* Using Postman API

## Kahoot

Go to [kahoot.it](https://kahoot.it/) and enter the pin show on the screen—answer the questions as quick as you can to win an Amazon gift card!

## Additional resources

Check out the Postman docs:

* [Publishing documentation](https://learning.postman.com/docs/postman/api-documentation/documenting-your-api/)
* Automation with [Newman](https://learning.postman.com/docs/postman/collection-runs/command-line-integration-with-newman/)
* [Postman API](https://learning.postman.com/docs/postman/postman-api/intro-api/)

## Next steps

Next up let's overview some topics for further learning: __[Activate thrusters](./part4-ActivateThrusters.md)__.
