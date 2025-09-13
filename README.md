# cloud-native-applications
this is related to cloud native applications 
my-cloud-native-app/
├── handler.js
├── serverless.yml
├── package.json
└── README.md

handler.js
exports.hello = async (event) => {
  return {
    statusCode: 200,
    body: JSON.stringify({ message: "Hello from Lambda!" }),
  };
};


serverless.yml
service: hello-world

provider:
  name: aws
  runtime: nodejs18.x
  region: us-east-1

functions:
  hello:
    handler: handler.hello
    events:
      - http:
          path: hello
          method: get


package.json 
{
  "name": "my-cloud-native-app",
  "version": "1.0.0",
  "description": "A simple serverless app",
  "main": "handler.js",
  "dependencies": {},
  "devDependencies": {},
  "scripts": {
    "deploy": "serverless deploy"
  }
}



