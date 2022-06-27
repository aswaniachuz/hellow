# hellow
name: Go test

on:
  push:
    branches:
      - master
  pull_request:
    branches:
      - master

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - name: Set up Go
        uses: actions/setup-go@v2
        with:
          go-version: 1.17.8

      - name: Build
        run: GOBUILD_TAGS= make

      - name: Test
        run: GOBUILD_TAGS= make test
