# Prepare for Launch

__Before you get started make sure you have carried out the following setup steps:__

* Download [Postman](https://www.postman.com/downloads/) for Mac / Windows / Linux.
* Create a [Postman account](https://learning.postman.com/docs/postman/launching-postman/postman-account/#signing-up-for-a-postman-account), and then sign in to the Postman app.
* Create a free ShipEngine account and get a sandbox API key by visiting [shipengine.com/postman](https://shipengine.com/postman) (_make sure you use this link as they've kindly raised rate limits for this workshop_). Select “United States” as your country when signing up for this free account to enable the sandbox environment.

We'll import a few collections along the way. Having these in your Postman app will give you loads more requests to play around with after the session.

In this section we're going to create a workspace, import a collection, authorize our requests, and add a test.

## 1. Create a workspace

In the Postman app, create a personal or team workspace to organize your workshop output.

* Open the dropdown at the top of the app and select __Create New__ &gt; enter a name and __Create Workspace__.

## 2. Import a collection

Postman collections let you organize groups of requests together with associated elements such as tests and documentation. You can create your own and import others.

> We're going to use a real-world API from ShipEngine, a shipping company who use Postman for developer onboarding and who created an exemplary demo of what you can do with Postman API docs.

* Click **New+**, tab over to **API Network**, and find the "ShipEngine" listing.
* Import the **ShipEngine Walkthrough** collection using the **Run in Postman** button.

_The ShipEngine collection has [published documentation](https://documenter.getpostman.com/view/305204/SW7XbA6V?version=latest) you can access by opening it in __Collections__ and clicking __View in web__._

## 3. Authorize your requests

You can specify auth details in Postman at the collection level using variables. Find the ShipEngine API key you obtained after signing up.

* Open the menu for the collection and select __Edit__. Select the __Variables__ tab.
* Add your ShipEngine key value as the __Initial Value__ field for the `API_KEY` variable (and the __Current Value__ field).
* Open the __Authorization__ tab so see how the collection requests are setup to authenticate. Click __Update__ to save your config.
* Send the first request in the collection `List your carriers`—this will initialize some additional collection variables you'll need later.

## 4. Test a request

* Send the second request in the collection `Get a specific carrier` and explore the response.
* Under the **Tests** tab, insert a test snippet from the right sidebar at the top of the script. Choose "Status code: Code is 200" from the list.
* Send the request again, and observe the test results in the response viewer.
* Update the test to fail, e.g. by testing for a 400 response code instead of 200. Send the request again, and observe the test results.

_Postman tests can use [Chai.js](https://www.chaijs.com/) assertions._

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

## Recap

In this section we tried out:

* creating a workspace
* importing a collection
* authorizing requests
* using variables
* test scripts

## Additional resources

Check out the Postman docs for more on these topics:

* [Workspaces](https://learning.postman.com/docs/postman/workspaces/intro-to-workspaces)
* [Requests](https://learning.postman.com/docs/postman/sending-api-requests/requests/)
* [Collections](https://learning.postman.com/docs/postman/collections/intro-to-collections/)
* [Variables](https://learning.postman.com/docs/postman/variables-and-environments/variables/)
* [Tests](https://learning.postman.com/docs/postman/scripts/test-scripts/)

See also:

* [Postman API Network](https://explore.postman.com/)
* [Chai.js](https://www.chaijs.com/) test assertion library

## Next steps

Next up: __[Final Countdown](./part2-FinalCountdown.md)__
