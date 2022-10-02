name: Apaca HTML file

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]
    
jobs:
  build:
    runs-on: ubuntu-latest
    env:
      AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
      AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
      AWS_SESSION_TOKEN: ${{ secrets.AWS_SESSION_TOKEN }}
      AWS_REGION: eu-central-1

    steps:
      - uses: actions/checkout@v3
      - name: File uploading....
        run: aws s3 cp index.html s3://s3cpibucket.github --acl public-read