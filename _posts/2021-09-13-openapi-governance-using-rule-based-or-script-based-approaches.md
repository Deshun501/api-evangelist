---
published: true
layout: post
title: 'OpenAPI Governance Using Rule-Based or Script-Based Approaches'
image: https://kinlane-productions2.s3.amazonaws.com/algorotoscope-master/uncle-sam-statue-supreme-court.jpg
tags:
    - Governance
    - OpenAPI
---

I have been spending more time investing in [my collection-based approach to applying governance to OpenAPI definitions](https://www.postman.com/postman/workspace/openapi-linting/overview). I have had several collections for using Postman’s testing capabilities to “test” the surface area of an OpenAPI for a variety of properties and patterns.. While I am continuing to invest in these collections, I wanted to lay a foundation of simpler, more consistent rules-based linting, tackling some of the most common and more simpler things you’d be looking for when applying design governance. As part of the latest work I’ve added two new collections to my toolbox for applying rules-based linting to OpenAPIs pulled from the Postman API, or via any URL--resulting in three distinct approaches to applying design governance to OpenAPIs.

- <ma href="https://www.postman.com/postman/workspace/openapi-linting/documentation/12959542-93cd90de-9f3c-4ed0-9c57-cc5a7712cf19">**OpenAPI Rules-Based Linting via API** - This collection lints an OpenAPI using a public API, passing an OpenAPI and a URL for a set of rules to be used when linting, returning the assertions using the test results for the response. The API doesn't require authentication, but does log all requests and should not be used to for production, but as a learning environment.</ma>
- [**OpenAPI Rules-Based Linting via Script**](https://www.postman.com/postman/workspace/openapi-linting/documentation/12959542-54a0882f-a8df-44ec-9861-40e409ca9876) - This collection has two requests, one that pulls an OpenAPI from the Postman API, and another that pulls the OpenAPI from URL, with both using scripts to lint the OpenAPI against a set of rules passed in via a parameter URL.
- [**OpenAPI Script-Based Testing**](https://www.postman.com/postman/workspace/openapi-linting/documentation/12959542-c2b7fca2-8ab1-4bd2-afcd-bb7662d46c1f) - This is a collection intended to demonstrate how you can lint an OpenAPI using the same scripting and testing infrastructure Postman uses to test individual instances of an API, but instead of scripting against the API, it is scripting against the OpenAPI for an API. There are two requests here, one pulls the OpenAPI from the Postman API, and the other from a URL.

The API supporting the first one is still in development, but provides a look at an API-first approach to API governance. The second one is interesting because it is completely self-contained, relying on libraries that are stored as global variables, and the third one will help tackle anything that you can’t easily do with rules. [I have setup a Github repository where I am managing all of the rules](https://rules.linting.org/) that you can apply with these collection, and working to organize them into meaningful rulesets. While design time governance within your editor or IDE is desirable, these collections are focused on develop and build time governance, leveraging the Postman platform to realize governance in these ways.

- **Runners** - Manually running against an OpenAPI stored in Postman, or via any other location with a rule, seeing the assertions via the Postman test results pane.
- **Monitors** - Automating governance by scheduling the governance of an OpenAPI stored in Postman, or via any other location with a rule, seeing the assertions via the Postman test results pane.
- **Pipelines** - Automating governance by baking into a CI/CD pipeline, applying the governance of an OpenAPI stored in Postman, or via any other location with a rule, seeing the assertions via the Postman test results pane.

Using a collection-based approach you can layer governance on top of existing contract, performance, security, and other testing using Postman. The rules-based and script-based approaches covers the full spectrum of needs. You can develop common sets of rules via rulesets and apply for the most common design patterns you want to enforce, but then cover the more advanced and custom end of the spectrum by writing scripts to test. Providing a very flexible and robust to how you realize governance across operations, allowing governance to be defined by modular collections, and applied manually by developers or baked directly into operations.

Next, I am going to keep adding to the rules catalog, and building some meaningful rulesets. Then I’ll make sure I craft sample OpenAPIs that help demonstrate common problems that will demonstrate the value of rules-based or script-based governance. Then I’ll organize the various rules into more complete API design guides, and I’ll even see if I can recreate some of the design guidelines of popular APIs who have made them available. I am keen to see how many of the guidelines set forth can be defined as rules, and how many will need a more script-based approach, or maybe are too difficult to automate at all. Then I’ll continue to push beyond just design governance and begin considering how I can apply across the entire API lifecycle, providing a more complete look at how API Operations can be governed.