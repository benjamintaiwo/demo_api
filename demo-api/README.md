# Bitstack Coding Challenge

The goal of this coding challenge is to create a simple bitcoin price calculating service
on the BTC/EUR trading pair.

You can name the service however you like. However, it is your responsibility to write tests
for it on top of the ones provided to you.

Inputs:
- BTC ask

Output:
- Total price of BTC ask

Here is a quick resource on [how orderbooks work](https://blog.cryptology.com/how-does-the-order-book-work/).

## Setup

This repository depends on [Poetry](https://python-poetry.org) as a package manager.

Run:
- `poetry install` to install all dependencies
- `poetry add package-name` to install any additional dependency (you can use any dependency you like)
- `poetry run pytest tests` to run all tests

Running a development server:
- You can use `make run` to automatically run your development server

## Testing

You can use the following commands for testing:
- `poetry run pytest tests/test_demo_api.py`
- `poetry run python -m unittest tests/test_btc_eur_calculator_service.py`

I have added them both in the `makefile` and they can be run by `make test`.

## Code formatting

Mypy and Black are used for code formatting. All code formatting rules have already been specified.

You can use the Makefile to automatically format your code. (`make format`)

## Fetching Data
 
All data will be fetched from the [Bitstamp Orderbook](https://www.bitstamp.net/api/#order-book).

The orderbook returns all bids and asks on the EURBTC trading pair.

Each Ask is composed of (at minimum):
- Bitcoin on sale
- Price asked

## Calculating Price

It is upto you to gather how you would go about calculating BTC price for large orders (> 2 BTC).

## Testing

A simple fuzz-based test has already been created.

It is upto you to add test cases to help testing your bitcoin price calculator.

Your API must pass all fuzz tests as well as your own tests.
