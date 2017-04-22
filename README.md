# dynamodb-count
Several implementations for quick retrieval of dynamoDB record count.

## REQUIREMENT

Painless retrieval of the number of records in a dynamoDB table for given search criteria

The tool should be easy to use on different platforms without the need for long setup

## SYNOPSIS

The search needs to be done on non-primary fields, therefore dynamoDB scan is used.

DynamoDB scan rretrieves all table records and filters them according to search criteria. Ir outputs batches of records limited by 1Mb restriction.  

## IMPLEMENTATION

AWS javscript aws-sdk library provided the javascript client to connect and do the search of the table.
