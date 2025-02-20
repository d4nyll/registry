---
title: CloudAMQP
meta_desc: This page provides an overview of the CloudAMQP Provider for Pulumi.
layout: overview
---

The CloudAMQP provider for Pulumi can be used to provision any of the cloud resources available in [CloudAMQP](https://www.cloudamqp.com/).
The CloudAMQP provider must be configured with credentials to deploy and update resources in CloudAMQP.

## Example

{{< chooser language "javascript,typescript,python,go,csharp" >}}

{{% choosable language javascript %}}

```javascript
const cloudamqp = require("@pulumi/cloudamqp")

const instance = new cloudamqp.Instance("demo-instance", {
    plan: "lemur",
    region: "amazon-web-services::us-west-2"
});
```

{{% /choosable %}}
{{% choosable language typescript %}}

```typescript
import * as cloudamqp from "@pulumi/cloudamqp";

const instance = new cloudamqp.Instance("demo-instance", {
    plan: "lemur",
    region: "amazon-web-services::us-west-2"
});
```

{{% /choosable %}}
{{% choosable language python %}}

```python
import pulumi_cloudamqp as cloudamqp

instance = cloudamqp.Instance("demo-instance",
    plan="lemur",
    region="amazon-web-services::us-west-2"
)
```

{{% /choosable %}}
{{% choosable language go %}}

```go
import (
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	cloudamqp "github.com/pulumi/pulumi-cloudamqp/sdk/v3/go/cloudamqp"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		instance, err := cloudamqp.NewInstance(ctx, "demo-instance", &cloudamqp.InstanceArgs{
			Plan:   pulumi.String("lemur"),
			Region: pulumi.String("amazon-web-services::us-west-2"),
		})
		if err != nil {
			return err
		}

		return nil
	})
}

```

{{% /choosable %}}
{{% choosable language csharp %}}

```csharp
using System.Collections.Generic;
using System.Threading.Tasks;
using Pulumi;
using Pulumi.Cloudamqp;

class Program
{
    static Task Main() =>
        Deployment.Run(() => {
            var instance = new Instance("demo-instance", new InstanceArgs
            {
                Plan = "lemur",
                Region = "amazon-web-services::us-west-2",
            });
        });
}
```

{{% /choosable %}}

{{< /chooser >}}

## Libraries

The following packages are available in packager managers:

* JavaScript/TypeScript: [`@pulumi/cloudamqp`](https://www.npmjs.com/package/@pulumi/cloudamqp)
* Python: [`pulumi-cloudamqp`](https://pypi.org/project/pulumi-cloudamqp/)
* Go: [`github.com/pulumi/pulumi-cloudamqp/sdk/v3/go/cloudamqp`](https://github.com/pulumi/pulumi-cloudamqp)
* .NET: [`Pulumi.Cloudamqp`](https://www.nuget.org/packages/Pulumi.Cloudamqp)

The CloudAMQP provider is open source and available in the [pulumi/pulumi-cloudamqp](https://github.com/pulumi/pulumi-cloudamqp) repo.
