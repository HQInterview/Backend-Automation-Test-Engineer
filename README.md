# Backend Automation Test Engineer
===========

This document contains description and requirements for Round #1 of interview for Backend Automation Test Engineer position.

## Goal

1. Verify applicant's ability to write test scenarios
2. Verify that applicant is able to write clean and readable code.
3. Check for best practices inside chosen test framework.

## Requirements

1. Cover a feature with automation tests. You can find the feature description below.
2. Create a public repository on Github and push the solution there. Send us the link to the repository.

The code needs to work after we pull it and try it (no bugs).

## Quality requirements

Similarly as during any other code review in our team, we'll be checking the following:

* code quality
* usage of the configuration files
* naming convention

## Feature

### Requirements

1) Create a payment gateway library, that can handle payments with:

* Paypal REST API
* Braintree payments


2) Create a simple form for making payment. Form should have this fields:

* In order section:
  * Price (amount)
  * Currency (USD, EUR, THB, HKD, SGD, AUD)
  * Customer Full name
* In payment section:
  * Credit card holder name
  * Credit card number
  * Credit card expiration
  * Credit card CCV
* Submit button

Show success or error message after payment. 

Use appropriate form validations.

3) Save order data + response from payment gateway to database table.

### Specification

* Implement only **single payment** with credit card. 
* After submitting the form, use a different gateway based on these rules:
  * if credit card type is AMEX, then use Paypal.
  * if currency is USD, EUR, or AUD, then use Paypal. Otherwise use Braintree.
  * if currency is **not** USD and credit card **is** AMEX, return error message, that AMEX is possible to use only for USD
  
