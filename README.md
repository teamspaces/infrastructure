# Getting started
- Install `brew cask install google-cloud-sdk`
- `gcloud auth login`

# Secrets

## Encode
Use the included script with this repository to generate the base64 encoded version:

  `bin/base64 prepareforbeingsecretz`


# SSL
Generate or download keys into the `keys/` folder before running any of the commands below.

## Generate self-signed wildcard certificate

  ```
  openssl genrsa 2048 > host.key
  openssl req -new -x509 -nodes -sha1 -days 3650 -key host.key > host.cert
  #[enter *.domain.com for the Common Name]
  openssl x509 -noout -fingerprint -text < host.cert > host.info
  cat host.cert host.key > host.pem
  chmod 400 host.key host.pem
  ```

## Create certificate
`gcloud compute ssl-certificates create spaces-is --certificate=keys/spaces.is.crt --private-key=keys/spaces.is.key --project=spaces-prod`


# Cloud SQL
Follow the guide at https://cloud.google.com/sql/docs/postgres/connect-container-engine
