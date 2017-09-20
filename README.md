# Infrastructure

## Getting started
- Install `brew cask install google-cloud-sdk`
- `gcloud auth login`

# SSL
Generate or download keys into the `keys/` folder before running any of the commands below.

## Create certificate
`gcloud compute ssl-certificates create spaces-is --certificate=keys/spaces.is.crt --private-key=keys/spaces.is.key --project=spaces-prod`
