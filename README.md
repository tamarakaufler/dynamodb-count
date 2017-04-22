# dynamodb-count
Several implementations for quick retrieval of dynamoDB record count.

## REQUIREMENT

* Painless retrieval of the number of records in a dynamoDB table for given search criteria.
* The tool should be easy to use on different platforms without the need for long setup.

## BACKGROUND

The search needs to be done on non-primary fields, therefore dynamoDB scan is used.

DynamoDB scan retrieves all table records and filters them according to search criteria. It outputs batches of records limited by 1Mb restriction.  

## IMPLEMENTATION

### Javascript

* AWS javascript aws-sdk library provided the javascript client to connect and do the search of the table

#### Initial implementation - under directory 1

* No form for providing the search criteria. These need to be updated in the file, and file then saved and reloaded in the browser.
    
#### Implementation providing a search form - under directory 2

* Angularjs was used to create a SPA (Single Page Application). Being a single HTML file, it can be locally accessed through the browser, without a need to do any more setup that to add the AWS access key and the AWS secret in the file.

In our case, the order/member tables have a composite primary key (orderId/memberId and namespace). The search filters must be provided for the namespace, and start and end dates.
