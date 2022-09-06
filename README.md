How the Deno Fresh Framework Will Make Your App Fast
Pitch: Explain how the server-side rendering of JS with Fresh speeds up the loading of app and makes it faster to develop.

Audience: Back-end or full-stack dev

Client: Fusebit

Writer Deliverables: ~1500 word article,Stock Image,Code Samples

Content Type: Guide

What sets the company apart?: Developer-first 3rd party integration platform for SaaS products.

Competitors: Tray.io, Mulesoft

Technical Level: Expert/Highly technical

Tools to be used: Deno, JavaScript

Tools to be excluded: 

Mention of Product: Quick mention of our product in the conclusion of the article

Call to action: 

Outline: (this is just a starting point, feel free to modify it as you see fit)
- Introduction (1-3 paragraphs)
    - Introduce the reader to Deno Fresh Framework (briefly)
    - Introduce briefly the benefits of Fresh Framework in relation to app performance
    - What will the reader learn in this article?
- Expand on what Deno Fresh Framework is
- Explain the benefits of Deno Fresh Framework and how it can make your app fast
        - Zero build step
        - Typescript support
        - Zero run-time overhead
        - Just-in-time rendering on the edge.
- Explain how to get started with Deno Fresh Framework
- Create a simple app with the Deno Fresh Framework
- Conclusion (2-3 paragraphs)
    - Restate what the reader has learned
    - Introduce the reader to Fusebit, An API integration platform that saves you time when integrating popular APIs like Salesforce, Github, etc into your application by handling all the boilerplate needed to integrate with the APIs in a fast and secure manner

Reference(s):
https://fresh.deno.dev/
​​https://deno.com/blog/fresh-is-stable

Example Article(s):
NA

Target Keyword: Deno
Be sure to review our style guide before writing.

Writer Name: 

Writer Profile URL: (leave this blank)

----- Article

Write your article in Markdown and paste it below the rest of the content in this Google Doc.

Use the following link to let us know your article is ready for us to review:

https://portal.draft.dev/assignments/recA01Oo0vxvuQNVw


# How the Deno Fresh Framework Will Make Your App Fast

Deno Fresh framework is a full stack JavaScript web framework which you can use to build small and large scale web applications, it also support writting in TypeScript. Fresh framework does not provide a build step, the code that you write is the code that is run on the server providing instant deployments.

Web apps created with Fresh support server-side rendering (SSR), meaning all the HTML, CSS and JavaScript code is first generated on the server and delievered to the client as fully rendered HTML pages, this greatly reduce the time a page loads on the browser. It uses [Preact](https://preactjs.com) to render pages on both the server and client, depending on the specific component we need but most rendering is done on the server, the client renders small islands of interactivity for example click buttons. In the aricle you will learn how to create a simple blog using the Fresh Framework and how Fresh can help both your web app and development faster also note that you can create a large scale app like Github.

## Deno Fresh Framework features and benefits

Fresh make use of just-in-time (JIT) rendering on the, using a combination of a routing framework and templating engine for rendering pages on demand. Whenever a user make a request it takes less time for the browser to load content onto the screen.
