# Final Countdown

__< Previous section: [Prepare for launch](./part1-PrepareForLaunch.md)__

Now that we've tried out collection runs, variables, and test snippets, let's explore how to pass data between requests and change the order of execution.

## 1. Import some tests

* In the Postman app, click **New+**, open the **Templates**, and find "Intro to writing tests - with examples".
* Import the **Intro to writing tests** collection using the **Run in Postman** button.
* This collection has a variety of test types organized into folders. It's a great place to explore for future learning around tests.

> Open the collection [web documentation](https://documenter.getpostman.com/view/1559645/RzZFCGFR?version=latest) for future reference.

## 2. Use variables to pass data between requests

Test scripts let you pass data around in Postman, so you can chain tests together with shared data.

* Create an environment to use for your tests. In the top right click the eye button—the environment quick look. In the __Environments__ section, click __Add__. Give your environment the name `workshop`, click __Add__, and close the __Manage Environments__ modal.
* Use the dropdown at the top right to select the `workshop` environment you just created. With this selected, any requests we run will reference variables in this environment.
* In the collection `Integration tests` folder &gt; `Using variables` sub-folder, send the request `Bitcoin exchange rate` and inspect the response.
* Check out the JavaScript code under the request **Tests** tab—it demonstrates how to get and set variables from a script using the `.set` method. It's saving a var to the environment. Open the environment quick look—it should be in there now because we ran the request.
* Open the request `Echo the exchange rate`. Notice that the URL references the `bitcoinRate` variable set in the previous request tests. Send the request to see the response. The request used the value returned from the previous one.

## 3. Change the request execution

Your scripts can alter the flow of request execution when you use the collection runner.

* Import another collection from __API Network__, search "learn" again and select the learning profile from before, this time importing "API Learner".
* Open the __Runner__ and select the `API Learner` collection. Run the collection and notice the flow of execution. All four requests should run.
* Open the first request `GET data` and __Send__ it. The response includes a field `message` and a text string value.
* Select the __Tests__ tab. Enter some JavaScript to test the length of the `message` (the conditional test should return true):

```javascript
let jsonData = pm.response.json();
let responseField = jsonData.message;
//check the length of the text
if (responseField.length < 10) {
  //note - setnextrequest only works when you use collection runner
  postman.setNextRequest(null);
}
```

* Make sure you __Save__ the request so that your code will execute when you run the collection.
* Open the __Runner__ again and select the API Learner collection. Run the collection—it should run the GET request followed by the PUT request, skipping the requests in-between.
* Alter the code to stop execution after the first request by passing `null` to the `setNextRequest` method:

```javascript
if (responseField.length > 10) {
  postman.setNextRequest(null);
}
```

* __Save__ the request. Open the __Runner__ and select the API Learner collection again. Start the run—it should stop after one request.
* _Optional: try changing the conditional test to return false and running the collection again (e.g. change &gt; to &lt;)—all requests should run._

## 4. Share data between collections

You can pass data between requests even if they are not in the same collection. Let's try that using environments.

* Open the Intro to Writing Tests collection &gt; `Integration Tests` &gt; `Bitcoin exchange rate` request again. In the __Tests__ remember that it sets the `bitcoinRate` environment variable. Make sure the `workshop` environment is selected.
* Open the API Learner collection &gt; `POST data` request.
* In the __Body__ of the request, add a new field, with the value referencing the environment variable:

{% highlight javascript%}
{% raw %}
{
	"name": "sue",
	"value": "{{bitcoinRate}}"
}
{% endraw %}
{% endhighlight %}

* Send the request—you will see the variable value set by the request in the other collection was sent to this request via the environment.

> [Variable scopes](https://learning.postman.com/docs/postman/variables-and-environments/variables/) determine where variable values are available within Postman, as well as which one takes precedence if you different vars with the same name.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

## Recap

In this section we tried out:

* used the collection runner
* chained requests
* altered execution order
* passed data between requests
* set variables from scripts
* accessed variables in the request body

## Kahoot

Go to [kahoot.it](https://kahoot.it/) and enter the pin shown on the screen—answer the questions as quick as you can to win an Amazon gift card!

## Additional resources

Check out the docs:

* [Variables](https://learning.postman.com/docs/postman/variables-and-environments/variables/)
* [Building Workflows](https://learning.postman.com/docs/postman/collection-runs/building-workflows/)
* [Branching and Looping](https://learning.postman.com/docs/postman/scripts/branching-and-looping/)
* [Postman sandbox](https://learning.postman.com/docs/postman/scripts/postman-sandbox/)
* [Advanced scripts and tests](https://learning.postman.com/docs/postman/collection-runs/building-workflows/)

And more templates you can try out in Postman:

* [Extract data to chain requests](https://explore.postman.com/templates/1616/extract-data-to-chain-requests)
* [Working with data files: ramen](https://explore.postman.com/templates/1433/working-with-data-files-ramen)
* [Dynamic variables in mock servers](https://explore.postman.com/templates/3360/dynamic-variables-in-mock-servers)

## Next steps

Next up: __[Liftoff](./part3-Liftoff.md)__
