# GOV.UK Replatforming test app

This is a very simple test app to help GOV.UK developers familiarise themselves with the new Kubernetes-based hosting.

## How to use this app

Navigate to the test app url on your browser and set the status parameter as the status response you want (e.g. `<test app url>?status=200`)

## Build workflows

This app is used by [govuk-ruby-images](https://github.com/alphagov/govuk-ruby-images/blob/main/.github/workflows/build-govuk-replatform-test-app.yaml) as part of a workflow to test the base and builder Ruby images. It is currently pinned to `Ruby 3.4` and `Bundler 2.3.22` to ensure that Ruby 3.x builds are tested. Ensure that this is always at the penultimate Ruby version.

## Run the app locally

The app is intended to run on the GOV.UK Kubernetes clusters, but it is also possible to run it locally.

```sh
docker build -t govuk-replatform-test-app .
```

```sh
docker run --rm -p3000:3000 -p9394:9394 govuk-replatform-test-app
```

You should then be able to browse the web app on http://localhost:3000/ and the Prometheus metrics on http://localhost:9394/metrics.
