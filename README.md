#AWS Lambda Png/Jpg to webp convertor

Based on [Tutorial](https://docs.aws.amazon.com/lambda/latest/dg/with-s3-example.html)

Add [Sharp](https://sharp.pixelplumbing.com) `npm install --arch=x64 --platform=linux --target=12.13.0  sharp`

Build zip `zip -r function.zip .`

Create lambda function

~~~
aws lambda create-function --function-name WebpConverter \
--zip-file fileb://function.zip --handler index.handler --runtime nodejs12.x \
--timeout 10 --memory-size 1024 \
--role <lambda role> \
--profile <creadentials profile> \
--region eu-west-1
~~~

Update lambda function

~~~
aws lambda update-function-code \
--function-name WebpConverter \
--zip-file fileb://function.zip \
--profile donatix \
--region eu-west-1
~~~
