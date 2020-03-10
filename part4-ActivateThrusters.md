# Activate Thrusters - part 4

**Choose your own adventure**: part 4 of this workshop is tailored to the interests and makeup of the attendees. In the **Side Missions Q&A Networking** immediately following, attendees can talk through specific features and workflows in a smaller group.

## [OBSERVE] Maintain your **API specifications**

1. Import the **Cosmos** template.
1. Review the web documentation to access [an example specification file](https://github.com/postmanlabs/spectral-postman/blob/master/cosmos.yaml), and copy this specification to your clipboard.
1. In the Postman app under the **APIs** tab, create a new API by pasting the specification and selecting `OpenAPI 3.0` and `YAML` format.
1. Save the specification details, and generate a collection.

## [OBSERVE] An easier way to **GraphQL**

1. Import the **Working with GraphQL** template.
1. Under the last request `Built-in support for GraphQL`, read the request description and copy the sample GraphQL schema to your clipboard.
1. Under the **APIs** tab, paste the GraphQL as a new schema (as described in the previous section), select the `GraphQL` schema type, and hit **Save**.
1. Back under the **Collections** tab, return to the `Built-in support for GraphQL` request under the **Body** tab, select your recently added schema, and hit refresh.
1. Observe the syntax highlighting, autocompletion from schema, and usage of GraphQL and other variables.

## [OBSERVE] **Intercept** your cookies

1. The first time using the **Interceptor**, you will need [to install the Postman interceptor and bridge](https://learning.postman.com/docs/postman/sending-api-requests/interceptor/#installing-interceptor).
1. Send a request to a site like `medium.com`, and inspect the response.
1. Under the **Interceptor** icon to "Capture requests and cookies with Postman", tab over to **Cookies** and toggle on **Capture Cookies**. Enter a domain like `medium.com`, and add the domain.
1. Return to the original request to `medium.com`, and re-inspect the response. Observe the difference in response when you're logged in to your Medium account (in the Chrome browser) and when you're not. Observe the difference when you've added the domain to sync your cookies or removed the domain.

## [DO] Finer control for **generating code**

1. Under the wrench icon's **General Settings**, toggle on the `New Code Generation Mode`.
1. On a tab with a request working as you'd like it, click the **Code** link.
1. Select a language or framework, and observe the generated code snippets.
1. Under the gear icon, customize your preferences for each language's code generation.

## [DO] Powerful debugging with the **console**

1. Import the **How to use the Postman console** template.
1. Open the Postman console, and run the request `message types`.
1. Observe how the log statements written under the script areas correspond to the logs in the Postman console, information about network requests, and other metadata and features within the console display.

![[winter solstice art](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)](https://apod.nasa.gov/apod/image/1712/WinterSolsticeMW_Seip.jpg)

### New features and improvements

1. API specifications
1. GraphQL support
1. Interceptor support
1. Code generation improvements
1. Console improvements

### Additional resources

1. [Cosmos](https://explore.postman.com/templates/4341/cosmos) template
1. [Working with GraphQL](https://explore.postman.com/templates/1692/working-with-graphql) template
1. [How to use the Postman Console](https://explore.postman.com/templates/4573/how-to-use-the-postman-console) template

## Mission Complete 🚀

### Even More Resources

- Launchpad in-app tutorials
- Community-contributed [templates](https://learning.getpostman.com/docs/postman_for_publishers/postman_templates/add_templates)
- [Community forum](https://community.getpostman.com/)
- [Product Roadmap](https://trello.com/b/4N7PnHAz/postman-roadmap-for-developers)
- [Better Practices](https://medium.com/better-practices) technical blog
