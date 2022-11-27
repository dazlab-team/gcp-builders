# Dazlab's custom Google Cloud Build images

This repository contains source code for [Dazlab's](http://dazlab.global)
custom Docker images used in [Google Cloud Build](https://cloud.google.com/cloud-build/docs/).

## Prerequisites

- Google Cloud project created with Billing enabled
- Cloud Build API enabled
- [gcloud CLI](https://cloud.google.com/sdk/docs/) installed

## Installation

To use these build images in your Google Cloud Project, do the following

1. Clone this source repo.
2. Go to the selected image, and schedule a build from the command line.

Example commands for [heroku](./heroku/README.md) image:

```bash
git clone https://github.com/dazlab-team/gcp-builders.git
cd gcp-builders/heroku
gcloud --project=<your GCP project ID> builds submit .
```

## Using the image

Based on the the example above, here's how to use the installed `heroku` image:

```bash
steps:
- name: gcr.io/$PROJECT_ID/heroku
  args: ['login']
  env: ["HEROKU_API_KEY=XXXXXXXXXXXXX"]
```

## License

This source code is licensed under Apache 2.0. Full license text is available in [LICENSE](LICENSE).

## Links

- http://dazlab.global
- https://cloud.google.com/sdk/docs/
- https://cloud.google.com/cloud-build/docs/
