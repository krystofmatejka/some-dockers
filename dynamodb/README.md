# AWS DynamoDB

This image is for local development only. Full documentation [here](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.html)

## Docker

### Build & run
```sh
docker-compose up
```

## AWS CLI

### Create table

this command will create a table named **default** with key **id**
```
aws dynamodb create-table --cli-input-json file://schema.json --endpoint-url http://localhost:8000
```

### List tables
```sh
aws dynamodb list-tables --endpoint-url http://localhost:8000
```

### Scan table
```sh
aws dynamodb scan --table-name default --endpoint-url http://localhost:8000
```

## AWS NODE.JS SDK

aws sdk needs to specify an url of local endpoint
```js
const aws = require('aws-sdk')
const dynamo = new aws.DynamoDB({endpoint: 'http://localhost:8000'})
```
