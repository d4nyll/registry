---
title: AWS QuickStart Aurora Postgres
meta_desc: Use Pulumi's Component for creating an AWS QuickStart Aurora Postgres Cluster using infrastructure as code.
layout: overview
---

Easily create AWS Aurora Postgres Cluster based on the AWS QuickStart Aurora Postgres guide as a package available in all Pulumi languages.

Example:

{{< chooser language "typescript" >}}

{{% choosable language typescript %}}

```typescript
const myDb = new aurora.Cluster("demo-cluster", {
    vpcID: myVpc.vpcID,
    dbName: "myDemoDatabase",
    dbEngineVersion: "9.6.16",
    dbInstanceClass: "db.r4.large",
    availabilityZoneNames: ["us-west-2a", "us-west-2b"],
    dbNumDbClusterInstances: 3,
    dbMasterUsername: "rootUser",
    enableEventSubscription: false,
    dbMasterPassword: pulumi.secret("TestPassword1234!"),
    dbParameterGroupFamily: "aurora-postgresql9.6",
    privateSubnetID1: "private Subnet ID 1",
    privateSubnetID2: "private Subnet ID 2",
});
```

{{% /choosable %}}

{{< /chooser >}}

## SDK packages

The AWS API Gateway provider is available as a package in all Pulumi languages:

* JavaScript/TypeScript: [`@pulumi/aws-quickstart-aurora-postgres`](https://www.npmjs.com/package/@pulumi/aws-quickstart-aurora-postgres)
* Python: [`pulumi-aws-quickstart-aurora-postgres`](https://pypi.org/project/pulumi-aws-quickstart-aurora-postgres/)
* Go: [`github.com/pulumi/pulumi-aws-quickstart-aurora-postgres/sdk/go/aws`](https://github.com/pulumi/pulumi-aws-quickstart-aurora-postgres)
* .NET: [`Pulumi.AwsQuickStartAuroraPostgres`](https://www.nuget.org/packages/Pulumi.AwsQuickStartAuroraPostgres)
