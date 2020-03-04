# Liftoff

![Liftoff](./Liftoff.jpg)

So far we have tried running collections, shared data between requests, and used some basic test scripting. In this section we will look at generating documentation, using Postman on the command line, and the Postman API.

## 1. Generate documentation

You can generate user documentation for an API directly from your Postman collections. Documentation can include instructional text and images, request details, example request and response code, and code snippets in different languages.

> To see a great demo of how you can use Postman for developer onboarding, check out the [ShipEngine Walkthrough](https://documenter.getpostman.com/view/305204/SW7XbA6V?version=latest) collection.
> * Create a free ShipEngine account and get a sandbox API key by visiting [shipengine.com/postman](https://shipengine.com/postman) (_make sure you use this link as they've kindly raised rate limits for us_).
> * Select “United States” as your country when signing up for this free account to enable the sandbox environment.
> * Add your ShipEngine key value in the collection variables as the `API_KEY` and try out the first request.

* Open the VIP Customers collection detail view and check out the description. Click to edit it—you can use markdown. You can add a description when you first create a collection.
* Open one of the collection requests and check out the name and description by expanding it—this all appears in the documentation. Make an edit to the description.
* Open the parameters and headers—these descriptions are also in the docs.
* Open the request __Examples__—this content will also auto-populate in the docs. Remember from earlier that you can save responses as examples when you send your request.
* Save any requests you changed, open the collection, and click __View in web__. Your edits should appear—you can also edit directly in the browser.
* By default your docs will open in a private view which is accessible to anyone with access to the collection. Check out the docs structure—requests are listed on the left and are clickable, your collection description appears at the top, request detail includes parameters, auth, etc, and on the right you can access code snippets in different languages.
  * You can also publish your docs, then share them by URL. Published docs can be linked to specific versions of your collection and can include environments. If you include an environment, any variables you reference in the requests will populate in the docs from the relevant variable value (collection or environment).
* While publishing you can share your collection in the Templates or API Network, which makes them available from the __New__ button in the Postman app just like the collections we've been using today.
* Your docs will include the Run in Postman button which allows people to import the collection in a single click (optionally including an environment). You can alternatively generate a Run in Postman button from the Postman app. Open the collection options menu and choose __Share__ then __Embed__. You can generate HTML or Markdown to include in any web page and let people import your collection. _Note that your collection will only auto-update with changes if you publish it / add it to Templates or API Network, if you only use the Run in Postman button you will need to generate the embed code again when you make changes._

## 2. Version control

You can version your collections and manage changes via forks and pull requests.

* Create a fork of a collection—use the collection menu. Choose a name and workspace.
* Make a change in a request on your fork.
* _If you have edit access to the parent collection you can merge your changes at any time using the edit menu—or you can create a pull request._
* Open a pull request using the edit menu. Clicking __Create pull request__ will display the diff in the web dashboard. Enter the details and select reviewers.
* You an pull changes from the parent collection if it has updated since your fork was created.
* You can comment on pull requests to discuss them, and can resolve conflicts.

## 3. Run a collection from CLI with Newman

You can run collections from the Postman CLI Newman—which in turn facilitates integrating collection runs with your CI/CD pipeline—for example if tests fail you could set an exit flag to prevent deployment.

> In order to use **Newman**, you will need to install [Node.js](https://nodejs.org/en/download/), a package manager like [npm](https://www.npmjs.com/), and [Newman](https://github.com/postmanlabs/newman) using a command like `npm install -g newman`. _If you don't already have node and npm on your computer you might want to watch this part and get setup to try it yourself later._

* Export a collection to a local directory.
* Run `newman run collection.json`, and observe the CLI output.

We can also run a collection in Newman from a Postman account—in order to do that we need the collection ID, which we can get using the Postman API.

## 4. Use Postman API

Let's use Postman to call the Postman API so that we can get a collection ID to run via Newman. The Postman API provides access to your Postman account data, including collections. You can access it like any other API—it also has a Postman collection to make calling it inside Postman straightforward.

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

## Questions?

Shout out any questions you have on documentation, Newman, or Postman API.

## Kahoot

Go to [kahoot.it](https://kahoot.it/) and enter the pin show on the screen—answer the questions as quick as you can to win an Amazon gift card!

## Additional resources

Check out the Postman docs:

* [Publishing documentation](https://learning.postman.com/docs/postman/api-documentation/documenting-your-api/)
* Automation with [Newman](https://learning.postman.com/docs/postman/collection-runs/command-line-integration-with-newman/)
* [Postman API](https://learning.postman.com/docs/postman/postman-api/intro-api/)

## Next steps

Next up let's overview some topics for further learning: __[Activate thrusters](./part4-ActivateThrusters.md)__.
