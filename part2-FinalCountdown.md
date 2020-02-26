# Final Countdown

__< Previous section: [Prepare for launch](./part1-PrepareForLaunch.md)__

Now that you've tried out collections, auth, variables, and test snippets, let's explore how to run sets of requests and pass data between them.

## 1. Import some tests

* In the Postman app, click the **New+** button, tab over to **Templates**, and find "Intro to writing tests - with examples".
* Import the **Intro to writing tests** collection using the **Run in Postman** button.

> Open the collection [web documentation](https://documenter.getpostman.com/view/1559645/RzZFCGFR?version=latest) for future reference.

## 2. Use variables to pass data between requests

* In the collection `Integration tests` folder &gt; `Using variables` sub-folder, send the request `Bitcoin exchange rate` and inspect the response.
* Check out the JavaScript code under the request **Tests** tab—it demonstrates how to get and set variables from a script using the `.set` method.
* Open the request `Echo the exchange rate`. Notice that the URL references the `bitcoinRate` variable set in the previous request tests. Send the request to see the response.

## 3. Run a collection

You can run all of the requests in a collection or folder using the collection runner.

* Click __New__ and find "Postman Echo" in the Templates. Import it and open it in __Collections__.
* Click __Runner__ and select the Postman Echo collection (or a folder inside it). Click __Run Postman Echo__ to see the order the requests run in and the output of any tests. Close the collection runner.

## 4. Change the request execution

* In the Postman Echo collection, open the first request `Request Methods` &gt; `GET request`.
* __Send__ the request and check out the response data.
* Open the **Tests** tab and enter some JavaScript at the end of the existing code (the conditional test should return true):

```javascript
let jsonData = pm.response.json();
let responseField = jsonData.args.foo1;
//the "foo1" field in the response has the value "bar1"
if (responseField === 'bar1') {
  //note - setnextrequest only works when you use collection runner
  postman.setNextRequest("DELETE Request");
}
```

* Make sure you __Save__ the request so that your code will execute when you run the collection.
* Open the __Runner__ again and select the Postman Echo collection "Request Methods" folder only. Run the collection—it should run the GET request followed by the DELETE request, skipping the requests in-between.
* _Optional: try changing the conditional test to return false and running the collection again (e.g. change "bar1" to "bar")._
* Alter the code to pass `null` to the `setNextRequest` method:

```javascript
if (responseField === 'bar1') {
  postman.setNextRequest(null);
}
```

* Open the __Runner__ and select the Postman Echo collection "Request Methods" folder again. Start the run—it should stop after one request.

## 6. Share data between collections

You can pass data between requests even if they are not in the same collection. Environments allow you to define sets of key value pairs you can use in multiple requests / collections.

* Open the Intro to Writing Tests collection &gt; `Integration Tests` &gt; `Bitcoin exchange rate` request again. In the __Tests__ remember that it sets the `bitcoinRate` environment variable.
* Open the API Learner collection &gt; `POST data` request. Make sure the `workshop` environment is selected from the dropdown in the top right.
* In the __Body__ of the request, add a new field, referencing the environment variable so that the body data has the following structure:

```json
{
 "name": "sue",
 "rate": "{{bitcoinRate}}"
}
```

* Send the request—you will see the variable value set by the request in the other collection was sent to this request via the environment.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

## Recap

In this section we tried out:

* used the collection runner
* chained requests
* altered execution order
* passed data between requests
* set variables from scripts
* accessed variables in the request body

## Additional resources

Check out the docs:

* [Postman sandbox](https://learning.postman.com/docs/postman/scripts/postman-sandbox/)
* [Advanced scripts and tests](https://learning.postman.com/docs/postman/collection-runs/building-workflows/)
* [Running a collection](https://learning.postman.com/docs/postman/collection-runs/intro-to-collection-runs/)
* [More about variables](https://learning.postman.com/docs/postman/variables-and-environments/variables/)

And more templates you can try out in Postman:

* [Intro to writing tests - with examples](https://explore.postman.com/templates/198/intro-to-writing-tests---with-examples)
* [Extract data to chain requests](https://explore.postman.com/templates/1616/extract-data-to-chain-requests)
* [Working with data files: ramen](https://explore.postman.com/templates/1433/working-with-data-files-ramen)
* [Dynamic variables in mock servers](https://explore.postman.com/templates/3360/dynamic-variables-in-mock-servers)

## Next steps

Next up: __[Liftoff](./part3-Liftoff.md)__
