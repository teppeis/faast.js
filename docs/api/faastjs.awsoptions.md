---
id: faastjs.awsoptions
title: AwsOptions interface
hide_title: true
---
[faastjs](./faastjs.md) &gt; [AwsOptions](./faastjs.awsoptions.md)

## AwsOptions interface

AWS-specific options. Extends [CommonOptions](./faastjs.commonoptions.md)<!-- -->. These options should be used with [faastAws()](./faastjs.faastaws.md)<!-- -->.

<b>Signature:</b>

```typescript
export interface AwsOptions extends CommonOptions 
```

## Properties

|  Property | Type | Description |
|  --- | --- | --- |
|  [awsLambdaOptions](./faastjs.awsoptions.awslambdaoptions.md) | <code>Partial&lt;aws.Lambda.CreateFunctionRequest&gt;</code> | Additional options to pass to AWS Lambda creation. See [CreateFunction](https://docs.aws.amazon.com/lambda/latest/dg/API_CreateFunction.html)<!-- -->. |
|  [region](./faastjs.awsoptions.region.md) | <code>AwsRegion</code> | The region to create resources in. Garbage collection is also limited to this region. Default: <code>&quot;us-west-2&quot;</code>. |
|  [RoleName](./faastjs.awsoptions.rolename.md) | <code>string</code> | The role that the lambda function will assume when executing user code. Default: <code>&quot;faast-cached-lambda-role&quot;</code>. Rarely used. |