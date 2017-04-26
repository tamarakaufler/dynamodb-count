# dynamodb-count
Several implementations for quick retrieval of dynamoDB record count.

# REQUIREMENTS

* Painless retrieval of the number of records in a dynamoDB table for given search criteria. (Finding the count on the AWS DynamoDB dashboard is time consuming if there are many found records, because AWS shows batches of results and the count is found only on the last results page.)
* The tool needs to be easy to use on different platforms without the need for a long setup. (The app implemented on a Linux machine but my colleague, who was to use the app, uses a Windows machine and is not a developer.)

# BACKGROUND

The search needs to be done on non-primary fields, therefore dynamoDB scan is used.

DynamoDB scan retrieves all table records and filters them according to search criteria. It outputs batches of records limited by 1Mb restriction.  

# IMPLEMENTATION

The plan was to provide an implementation in the form of one file, that could be downloaded and, after setting up the AWS credentials, could be used as is.

Originally I was going to use Go and build the relevant binary for my colleague's OS. However Go was not a supported programming language in our company, so I opted for Javascript, with the plan to add a Go implementation after I provide my colleague with the tool he needed.

## Javascript

* AWS javascript aws-sdk library provided the javascript client to connect and do the search of the table

### Initial implementation - under directory 1

* No form for providing the search criteria. These need to be updated in the file, and file then saved and reloaded in the browser.
    
### Implementation providing a search form - under directory 2

* Angularjs was used to create a SPA (Single Page Application). Being a single HTML file, it can be locally accessed through the browser, without a need to do any more setup that to add the AWS access key and the AWS secret in the file.

In our case, the order/member tables have a composite primary key (orderId/memberId and namespace). The search filters must be provided for the namespace, and start and end dates.

## Go

Implementation in repo https://github.com/tamarakaufler/go_dynamodb_search
