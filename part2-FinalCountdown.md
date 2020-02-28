# Final Countdown - part 2

## [DO] Import the template

1. In the Postman app, click the **New+** button, tab over to **Templates**, and find "Intro to writing tests - with examples".
1. Import the **Intro to writing tests** collection using the **Run in Postman** button.
1. Observe various aspects of the collection, including [the web documentation](https://documenter.getpostman.com/view/1559645/RzZFCGFR?version=latest).

## [DO] Learn how to use variables to pass data between requests

1. Create a new environment (to store our data), and then use the dropdown to select this new environment.
1. Under the **Integration tests** folder and **Using variables** sub-folder, send the request `Bitcoin exchange rate` and inspect the response.
1. Review the JavaScript code under the **Tests** tab, and observe how to get and set variables in script areas.
1. Send the request `Echo the exchange rate`, and observe how to get variables in text areas.

## [DO] Run a folder

1. Run the folder **Using variables** in the collection runner, and observe the execution order.
1. Write JavaScript code under the **Tests** tab to establish conditional logic to terminate a collection run.
1. Run the folder again, and observe the execution order.

```javascript
let jsonData = pm.response.json();
let bitcoinRate = jsonData.bpi.USD.rate_float;

if (bitcoinRate < 8000) {
  // proceed to the next request
} else {
  // stop right there
  postman.setNextRequest(null);
}
```

## [DO] Write code to chain a request

1. In the **ShipEngine Walkthrough** collection, plan what data to extract from the response body (to pass to a subsequent request).
1. Create an environment, and select it as your active environment.
1. Under the **Tests** tab of your request, write the code to parse the response body and set an environment variable.

```javascript
let jsonData = pm.response.json();
pm.environment.set("nameOfVariable", valueOfVariable);
```

## [DO] Format a different request to use this passed data

1. Duplicate the request `Echo the exchange rate` from the **Intro to writing tests** collection, rename the request, and drag the request into the **ShipEngine Walkthrough** collection.
1. Update the data to be sent in the request `Echo`, and review the syntax of getting and setting variables in text vs. script areas.
1. Using the collection runner, run the **ShipEngine Walkthrough** collection with your newly added request.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

### Summary

1. Writing advanced scripts and tests
1. Running a collection with the collection runner
1. Using lots and lots of variables

### Concepts

1. [Advanced scripts and tests](https://learning.postman.com/docs/postman/collection-runs/building-workflows/)
1. [Running a collection](https://learning.postman.com/docs/postman/collection-runs/intro-to-collection-runs/)
1. [More about variables](https://learning.postman.com/docs/postman/variables-and-environments/variables/)

### Additional resources

1. [Intro to writing tests - with examples](https://explore.postman.com/templates/198/intro-to-writing-tests---with-examples) template
1. [Extract data to chain requests](https://explore.postman.com/templates/1616/extract-data-to-chain-requests) template
1. [Postman sandbox docs](https://learning.postman.com/docs/postman/scripts/postman-sandbox/)
1. [Working with data files: ramen](https://explore.postman.com/templates/1433/working-with-data-files-ramen) template
1. [Dynamic variables in mock servers](https://explore.postman.com/templates/3360/dynamic-variables-in-mock-servers) template
