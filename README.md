# DORA Network SRE coding challenge

## Pre-requisites

You will need to have the following installed on your machine:

- Docker
- Your choice of development environment (IDE) or text editor
- Use the language of your choice

### Steps

1. Pull the docker image containing the trades database `ghcr.io/dora-network/dora-sre-test:latest`
2. Start the postgres database container, it needs a little time to start up and import the data as there's a lot of it

## Task

The Postgres database contains a table called `trades`, a zipped CSV file (`trades.zip`) received from a broker contains trades data, however there are discrepancies between the two datasets. Your task is to write a script that will reconcile the two datasets and output the differences to a file called `differences.csv`.

The script must be runnable on a machine with limited memory, so the entire trades data set cannot be loaded into memory at once. You will need to use a streaming approach to read the data in chunks and process it in a memory efficient way.

The script should be able to handle the following scenarios:

- Price differences found
- Quantity differences found
- Missing trades in the data set

The script should be time efficient and should be able to process the data in a reasonable amount of time.

