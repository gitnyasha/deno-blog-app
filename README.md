# How the Deno Fresh Framework Will Make Your App Fast

Deno Fresh framework is a full stack JavaScript web framework which you can use to build small and large scale web applications, it also support writting in TypeScript. Fresh framework does not provide a build step, the code that you write is the code that is run on the server providing instant deployments.

Web apps created with Fresh support server-side rendering (SSR), meaning all the HTML, CSS and JavaScript code is first generated on the server and delievered to the client as fully rendered HTML pages, this greatly reduce the time a page loads on the browser. It uses [Preact](https://preactjs.com) to render pages on both the server and client, depending on the specific component we need but most rendering is done on the server, the client renders small islands of interactivity for example click buttons. In the aricle you will learn how to create a simple blog using the Fresh Framework and how Fresh can help both your web app and development faster also note that you can create a large scale app like Github.

## Deno Fresh Framework features and benefits

Fresh makes use of just-in-time (JIT) rendering on the server meaning the code is compiled when needed not before runtime, using a combination of a routing framework and templating engine for rendering pages on demand. Whenever a user make a request it takes less time for the browser to load content onto the screen. Now remember when I said that Fresh does not provide a build step, any TypeScript or JSX to plain JavaScript code is done when it is needed giving very fast iteration loops and deployments, you can use any platform that supports Deno to deploy your Fresh web app but the recommended platform is [Deno deploy](https://deno.com/deploy), visit the site on how to deploy your site it is very easy and is not time consuming. TypeScript comes out of the box with Fresh no separated configurations.

Deno Fresh framework also has a zero config necessary, there are no configurations that need to be done to run your first Fresh web app as you will see below when I am going to create a sample site. You could opt to have client side hydration of individual components meaning the client will download some JavaScript files embedded in HTML processing them, and attaching event listeners to the components or JavaScript files, these components will be inside the islands folder. Other features of Fresh are it makes use of native browser features, it has a file-system routing like Next.js.

## How to get started with Deno Fresh Framework

To get started with Deno Fresh Framework you need to have Deno on your machine if you do not already have it follow the instructions [here to install Deno](https://deno.land/manual/getting_started/installation). I will guide you in creating a simple blog app, where we can create, and get posts. To create a project use the following command below and I have named my project blog.

```
deno run -A -r https://fresh.deno.dev blog
```
It will scaffold out a new project with some example files, to understand how fresh runs read the [https://fresh.deno.dev/docs/getting-started/create-a-project](docs).

![Fresh project folder structure](https://imgur.com/ovECi9p.png)

Using your terminal switch into the newly created project and run `deno task start`, open your browser and navigate to `http://localhost:8000` you will see a page with a text "Welcome to fresh".

## Creating a the blog app

I will start by creating a route, they handle requests to the path in your project and are defined as files inside the routes folder. All posts will be shown on the home page so navigate inside the `routes/index.tsx` and update it to match the following code

```
import data from "../data/data.json" assert { type: "json" };

export default function Home() {
  return (
    <div class="p-4 mx-auto max-w-screen-md">
      <div class="flex flex-col gap-2 w-full">
        <h1 class="text-3xl font-bold">All Posts</h1>
        <ul class="flex flex-col gap-2 w-full">
          {data.map((post) => (
            <li class="flex flex-col gap-2 w-full" key={post.id}>
              <h2 class="text-xl font-bold">
                <a href={`/posts/${post.id}`}>{post.title}</a>
              </h2>
              <p class="flex-grow-1">{post.body}</p>
            </li>
          ))}
        </ul>
      </div>
    </div>
  );
}

```

Notice that I am importing data from a json file which we have not yet created in this tutorial I will not use a database but instead a json file to store our data, so go into the root folder and create a folder called `data`, inside the folder create a file `data.json` and add the following code.

```
[
  {
    "id": 1,
    "title": "This is my first post",
    "body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation",
    "created_at": "2019-01-01 00:00:00"
  },
  {
    "id": 2,
    "title": "This is my second post",
    "body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation",
    "created_at": "2019-01-02 00:00:00"
  },
  {
    "id": 3,
    "title": "This is my third post",
    "body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation",
    "created_at": "2019-01-03 00:00:00"
  }
]
```
![Imgur](https://i.imgur.com/aJDM8GP.png)

Now open your browser on `http://localhost:8000` if your server is not running run `deno task start` in the terminal from your app root folder and in the browser it should display all the posts in your json file.

Next I will add a posts folder inside routes folder and in the posts folder create a dynamic route `posts/[id].tsx`, everything is passed right after the path part of the URL becomes the parameter so that when you click on a post you will be directed to that post page.
