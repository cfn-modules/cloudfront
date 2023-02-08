# cfn-modules: Amazon CloudFront

Amazon CloudFront to deliver content from S3 bucket


## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/cloudfront
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Bucket:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        OriginBucketModule: !GetAtt 'Bucket.Outputs.StackName'
        LogsBucketModule: '' # optional
      TemplateURL: './node_modules/@cfn-modules/cloudfront/module.yml'
```


## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>OriginBucketModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/s3-bucket">s3-bucket module</a> (only works in combination with Access := [CloudFrontRead])</td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>LogsBucketModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/s3-bucket">s3-bucket module</a> (only works in combination with Access := [CloudFrontAccessLogWrite])</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
  </tbody>
</table>
