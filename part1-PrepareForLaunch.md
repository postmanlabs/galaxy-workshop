# Prepare for Launch - part 1

## Verify pre-requisites

1. Download [Postman](https://www.postman.com/downloads/) for Mac / Windows / Linux
1. Create a [Postman account](https://learning.postman.com/docs/postman/launching-postman/postman-account/#signing-up-for-a-postman-account), and then sign in to the Postman app
1. Create a free ShipEngine account and get a sandbox API key using [this link](https://shipengine.com/postman), and select “United States” as your country when signing up for this free account to enable the sandbox environment

## [DO] Import the collection

1. In the Postman app, create a personal or team workspace to organize our workshop output.
1. Click the **New+** button, tab over to **API Network**, and find "ShipEngine".
1. Import the **ShipEngine Walkthrough** collection using the **Run in Postman** button.
1. Observe various aspects of the collection, including [the web documentation](https://documenter.getpostman.com/view/305204/SW7XbA6V?version=latest) that reviews how to get started with the ShipEngine API.

## [DO] Authorize your requests

1. Add your ShipEngine sandbox API key by [updating the collection variable](https://learning.postman.com/docs/postman/variables-and-environments/variables/#defining-collection-variables) called `API_KEY`.
1. Send the first request in the collection `List your carriers` to initialize some additional collection variables.

## [DO] Explore the ShipEngine API

1. Send the second request in the collection `Get a specific carrier` and observe various aspects of the request and response.
1. Review request builder and response viewer elements.

## [DO] Write a test

1. Under the **Tests** tab, insert a test snippet from the right sidebar.
1. Send the request again, and observe the test results in the response viewer.
1. Update the test to fail, send the request again, and observe the test results.
1. Review the syntax of Postman tests and [Chai.js](https://www.chaijs.com/) assertions.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

### Summary

1. Orientation within the app
1. Sending an HTTP request
1. Writing a test
1. Creating a collection

### Concepts

1. [Workspaces](https://learning.postman.com/docs/postman/workspaces/intro-to-workspaces)
1. [Requests](https://learning.postman.com/docs/postman/sending-api-requests/requests/)
1. [Collections](https://learning.postman.com/docs/postman/collections/intro-to-collections/)
1. [Variables](https://learning.postman.com/docs/postman/variables-and-environments/variables/)
1. [Tests](https://learning.postman.com/docs/postman/scripts/test-scripts/)

### Additional resources

1. [Postman API Network](https://explore.postman.com/)
1. [Chai.js](https://www.chaijs.com/) test assertion library
