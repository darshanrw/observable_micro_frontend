# INFO8985-observable-microfrontend
make a microfrontend that consumes a microservice that connects to a postgres database observable

TLDR;

You will need to run this in desktop vscode as umlet doesn't work on the web. The included deployment.uxf is a starter to write up the following case. Explain the diagram you produce and [include a .png file](https://www.umletino.com/umletino.html) in a .pdf file that you submit to the assignment folder as a group.

## The case:

I failed to get [the microfrontend](https://github.com/salesucation/hono-jsx-dom-with-vite) to interface with OTEL. The particular problem that I had was with `@hono/vite-cloudflare-pages` having a require statement and otel using imports. I needed vite-cloudflare-pages because I wanted to deploy the whole microfrontend there. Cloudflare pages uses a javascript container which is a little different than node. I like it because they have a generous free tier for developers and even the microservice is really fast. They have [python in the javascript](https://blog.cloudflare.com/ru-ru/python-workers/) container with pyodide. I have some experience with trying to use javascript containers with node and php with students. That hasn't been a particularly good experience and I have had a very good experience with docker based devcontainers.

Today's case is for an open source project I am planning during the holidays. Rather than cloudflare pages, [knative-pages](https://github.com/salesucation/knative-pages). Knative exposes a standard docker container in a way that scales to 0 when it is not being requested. Pages exposes a static front end from an industry standard s3 compatible bucket in the way that we did in [this lab 1st term](https://github.com/localstack/localstack-workshop).

Cloudflare and Turso have a libsqlite database that can work with pages. Libsqlite works with all of the major frameworks like sqlite. During the last CAPSTONE session some students implemented with Supabase. Supabase is a lot like my project in that it is a compilation of open source standards like postgresql. I decided to include supabase as my persistence layer in my holiday project.

The 3 pieces that I am joining are [knative](https://knative.dev/docs/), a [s3 web server](https://github.com/e2fyi/minio-web) and [supabase](https://supabase.com/). The case is to look at my backlog for this project. Make a recommendation for deployment in the format of a uml deployment diagram. Explain your recommendations in the context of what you have learned about devops and open telemetry. 

## Marking scheme:

|Item|Out of|
|--|--:|
|Deployment Diagram Completeness|5|
|Explanation|10|
|Conclusion and Applications|10|
|||
|Total|25|


