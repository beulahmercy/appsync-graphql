# test-graphql-query
## SAM commands

**Validate**
```
sam validate
```

**Prerequisties**
Make sure s3 bucket is created prehand before running deploy commands

**Deploy**
```
sam deploy --profile <profilename> --stack-name <stackname> --s3-bucket <bucketname>
```

## Testing

```
curl --location --request POST 'https://XXXXXXXX.appsync-api.us-west-2.amazonaws.com/graphql' \
--header 'x-api-key: <api_key>' \
--header 'Content-Type: application/json' \
--data-raw '{"query":"query MyQuery {\r\n  getEmployee(employeeId: \"employee#8c08d1d9-0be6-43b9-9f09-aa926d4d7f0d\") {\r\n    department {\r\n      id\r\n      key\r\n      name\r\n    }\r\n    id\r\n    key\r\n    name\r\n    dob\r\n  }\r\n}","variables":{}}'
```

**Generate x-api-key** 

Go to, AWS AppSync>AWSAppSync Dynamo Testing Sample>Settings>Default authorization mode>ApiKeys




