# Serverless RESTfull API
_____________
Simple CRUD that utilize AWS lambda to perform RESTfull CRUD API
Uses Serverless Offline plugin to ease local development


### Initial setup
Create all containers required
- Install npm packages
`npm install`
- Copy *.env.example* to the root directory and name it as *.env*

### How to run serverless in offline mode
- Run
`sls offline start --skipCacheInvalidation`
- Access your API endpoint in here
`http://localhost:3000`

### How to deploy your lambda function to AWS
- Configure your AWS credentails (Create access key in IAM)
`serverless config credentials --provider aws --key 1234 --secret 5678 --profile custom-profile`
- Deploy using your custom profile
`sls deploy --aws-profile custom-profile`

```
Serverless: Stack update finished...
Service Information
service: serverless-rest-api
stage: dev
region: ap-southeast-1
stack: serverless-rest-api-dev
resources: 34
api keys:
  None
endpoints:
  POST - https://xxxxxxx.execute-api.ap-southeast-1.amazonaws.com/dev/notes
  GET - https://xxxxxxx.execute-api.ap-southeast-1.amazonaws.com/dev/notes/{id}
  GET - https://xxxxxxx.execute-api.ap-southeast-1.amazonaws.com/dev/notes
  PUT - https://xxxxxxx.execute-api.ap-southeast-1.amazonaws.com/dev/notes/{id}
  DELETE - https://xxxxxxx.execute-api.ap-southeast-1.amazonaws.com/dev/notes/{id}
functions:
  create: serverless-rest-api-dev-create
  getOne: serverless-rest-api-dev-getOne
  getAll: serverless-rest-api-dev-getAll
  update: serverless-rest-api-dev-update
  delete: serverless-rest-api-dev-delete
layers:
  None
Serverless: Run the "serverless" command to setup monitoring, troubleshooting and testing.
```