# SST Demo Notes App [![Seed Status](https://api.seed.run/serverless-stack/demo-notes-app/stages/prod/build_badge)](https://console.seed.run/serverless-stack/demo-notes-app)

The [SST Guide](https://sst.dev/guide) is a comprehensive open source tutorial for building and deploying full-stack apps using serverless and React on AWS.

We create a note taking app from scratch — [**demo.sst.dev**](https://demo.sst.dev)

![Demo App](screenshot.png)

We use React.js, AWS Lambda, API Gateway, DynamoDB, and Cognito. This repo is a full-stack serverless app built with [SST](https://github.com/sst/sst).

- The `infra/` directory defines our AWS infrastructure.
- The `packages/functions` directory contains the Lambda functions that power the CRUD API.
- The `packages/frontend` directory contains the React app.

It's a single-page React app powered by a serverless CRUD API. We also cover how add user authentication, handle file uploads, and process credit card payments with Stripe.

### Prerequisites

Before you get started:

1. [Configure your AWS credentials](https://docs.sst.dev/advanced/iam-credentials#loading-from-a-file)
2. [Install the SST CLI](https://ion.sst.dev/docs/reference/cli/)

### Usage

Clone this repo.

```bash
git clone -b ion https://github.com/sst/demo-notes-app.git
```

Install dependencies.

```bash
npm install
```

This project uses a secret that we are not checking in to the repo. Make sure to [create one before deploying](https://sst.dev/chapters/handling-secrets-in-sst.html).

```bash
sst secret set StripeSecretKey <YOUR STRIPE SECRET TEST KEY>
```

#### Developing Locally

Start the React local dev environment from the `packges/frontend/` dir.

```bash
cd pacakges/frontend/
npm run dev
```

#### Running Tests

From the project root.

```bash
npm test
```

#### Deploying to Prod

Run this in the project root to deploy it to prod.

```bash
sst deploy --stage production
```

Make sure to set your secret for prod as well.

```bash
sst secret set StripeSecretKey <YOUR STRIPE SECRET TEST KEY> --stage production
```

---

Join the SST community over on [Discord](https://discord.gg/sst) and follow us on [Twitter](https://twitter.com/SST_dev).
