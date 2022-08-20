#hardhat-lambda-layer

Generator for public layer to provide hardhat support for webpacked lambdas. 

## Requirements
A lambda function using `14.x` or `16.x` node versions
## Usage
In your function deployment, specify the layer to mix in:

### us-east-1 (Virginia) region
```
arn:aws:lambda:us-east-1:210049126456:layer:hardhat-lambda-layer:3
```

### us-east-2 (Ohio) region
```
arn:aws:lambda:us-east-2:210049126456:layer:hardhat-lambda-layer:3
```

### Serverless framework example
To add this using serverless framework:
```yml
functions:
    expensiveLUFunction:
        handler: handlers.myFunc
        role: MainRole
        timeout: 30
        layers:
        - arn:aws:lambda:${opt:region,
            'us-east-1'}:210049126456:layer:hardhat-lambda-layer:1
        memorySize: 2048
```
