# Prepare for Launch

In this section we're going to create a workspace, import a collection, authorize our requests, and add a test.

## 1. Create a workspace

In the Postman app, create a personal or team workspace to organize your workshop output.

* Open the dropdown at the top of the app and select __Create New__ &gt; enter a name and __Create Workspace__.

## 2. Import a collection

Postman collections let you organize groups of requests together with associated elements such as tests and documentation. You can create your own and import others.

We'll import a few collections as we work through the topics. Having these in your Postman app will give you loads more requests to play around with after the session.

* Click **New+**, tab over to **API Network**, and search for "Learning". Select Sue's __API Learning Resources__ listing.
* Import the __VIP Customers__ collection using the **Run in Postman** button.
* Open the VIP Customers collection and click the second request `Get customer` to open it. Take a minute to look at the parts of the request with data entered (highlighted in green). Check out the collection variables to see where the URL components are coming from (open the collection menu and select __Edit__ &gt; __Variables__).
* __Send__ the request and look at the response data. The API sends back JSON—see the status code, and hover over the response time and size breakdowns. You can also save the response as an Example you can use in documentation and mock servers.
* Open the `PATCH` `Add customer` request and check out the data it's sending in the __Params__, __Authorization__, and __Body__. Remember the collection variables included the `token` value. __Send__ the request.

## 3. Test a request

Let's add some test JavaScript code to the request.

* In the **Tests** tab, insert a test snippet from the right sidebar at the top of the script. Remember that the status code was 200 OK. Choose `Status code: Code is 200` from the list.
* Notice that the test includes a message you'll see alongside it in test result output, and uses [Chai.js](https://www.chaijs.com/) syntax to create the assertion.
* __Save__ the request and __Send__ it again, and check out the __Test Results__.
* Open the `Get customers` request (first in the folder) and in the __Tests__ tab, add the same status code 200 test, but this time edit the test to fail, e.g. by testing for a 400 response code instead of 200. __Save__ and __Send__ the request again, and observe the test results, noticing the difference in the failed message.

## 4. Run a collection

You can run all of the requests in a collection or folder using the collection runner.

* Click __Runner__ and select the __VIP Customers__ collection.
* Click __Run VIP Customers__ to see the requests run. By default they'll run in the order they're listed in the collection folder, but you can change that as we'll see soon.

> Your request tests need to be saved to appear in the collection runner so remember to hit __Save__ in the requests._

* Import another collection to see more tests run. Click __New__ &gt; __Templates__ and search for "echo". Import the `Postman Echo` collection.
* Open the collection runner again, choose the Postman Echo collection, and run it.
* Check out the __Run Summary__ and notice you can filter on passed or failed tests. You can also access past test runs when you open the runner or by navigating back after a run.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

## Recap

In this section we tried out:

* creating a workspace
* importing a collection
* using variables
* authorizing requests
* test scripts
* running collections

## Kahoot

Go to [kahoot.it](https://kahoot.it/) and enter the pin shown on the screen—answer the questions as quick as you can to win an Amazon gift card!

## Additional resources

Check out the Postman docs for more on these topics:

* [Workspaces](https://learning.postman.com/docs/postman/workspaces/intro-to-workspaces)
* [Requests](https://learning.postman.com/docs/postman/sending-api-requests/requests/)
* [Collections](https://learning.postman.com/docs/postman/collections/intro-to-collections/)
* [Variables](https://learning.postman.com/docs/postman/variables-and-environments/variables/)
* [Tests](https://learning.postman.com/docs/postman/scripts/test-scripts/)
* [Running a collection](https://learning.postman.com/docs/postman/collection-runs/intro-to-collection-runs/)

See also:

* [Postman API Network](https://explore.postman.com/)
* [Chai.js](https://www.chaijs.com/) test assertion library

## Next steps

Next up: __[Final Countdown](./part2-FinalCountdown.md)__
