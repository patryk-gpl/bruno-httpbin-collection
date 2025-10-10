- [Bruno httpbin collection](#bruno-httpbin-collection)
  - [Prerequisites](#prerequisites)
  - [Contents](#contents)
  - [Quick start](#quick-start)
  - [Run httpbin locally (Docker)](#run-httpbin-locally-docker)
  - [Configuration and environments](#configuration-and-environments)
- [License and attribution](#license-and-attribution)

# Bruno httpbin collection

This repository contains Bruno collection for exercising the public httpbin service and self-hosted httpbin instances.

This repository contains Bruno collection files (and environments) that make it easy to explore httpbin's endpoints, reproduce common HTTP behaviors, and use them in API testing.

## Prerequisites

- [Bruno](https://docs.usebruno.com/) installed.
- (Optional) [Docker](https://www.docker.com/get-started/) installed to run httpbin locally.

## Contents

- `httpbin.org/` — main Bruno collection folder (collections, environments and example requests).
- `httpbin.org/environments/` — sample environments (`local`).

## Quick start

1. Clone the repository and navigate into it:

```bash
git clone https://github.com/patryk-gpl/bruno-httpbin-collection.git
cd bruno-httpbin-collection
```

2. Open Bruno and import the collection folder:

- In Bruno: click the menu (three dots) → Open Collection → choose the `httpbin.org` folder from the cloned repository.

3. Select an environment (top-right environment selector in Bruno):

- Use the included `httpbin.org` environment to target the public service.
- Use the `localhost` environment to target a local httpbin instance.

Now you can run requests, inspect responses, and use the collection as test fixtures.

## Run httpbin locally (Docker)

If you want to run httpbin locally for development or testing, start the official image:

```bash
docker pull kennethreitz/httpbin
docker run --rm -p 80:80 kennethreitz/httpbin
```

This will expose httpbin at http://localhost. Point the Bruno `localhost` environment `url` variable to that address if needed.

Notes:
- Use `--rm` to automatically remove the container after you stop it.
- If port 80 is taken, map to a different host port (e.g., `-p 8080:80`) and update the `localhost` environment URL.

## Configuration and environments

- The collection uses an environment variable named `url` as the base URL. By default the included `httpbin.org` environment points to https://httpbin.org.
- To target a different instance, use  or edit an environment and set `url` to your instance (for example `http://localhost:8080`).

# License and attribution

This repository is provided under the terms of the repository LICENSE file. The httpbin project and its Docker image are maintained by the httpbin community (see https://github.com/httpbin/httpbin).
