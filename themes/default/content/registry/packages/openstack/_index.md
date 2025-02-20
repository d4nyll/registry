---
title: OpenStack
meta_desc: The OpenStack provider for Pulumi can be used to provision any of the cloud resources available in OpenStack.
layout: overview
---

The OpenStack provider for Pulumi can be used to provision any of the private and public cloud resources available in [OpenStack](https://www.openstack.org/).  The OpenStack provider must be configured with credentials to deploy and update resources in an OpenStack cloud.

## Example

{{< chooser language "javascript,typescript,python,go,csharp" >}}

{{% choosable language javascript %}}

```javascript
const os = require("@pulumi/openstack")

const instance = new os.compute.Instance("test", {
	flavorName: "s1-2",
	imageName: "Ubuntu 16.04",
});
```

{{% /choosable %}}
{{% choosable language typescript %}}

```typescript
import * as os from "@pulumi/openstack";

const instance = new os.compute.Instance("test", {
	flavorName: "s1-2",
	imageName: "Ubuntu 16.04",
});
```

{{% /choosable %}}
{{% choosable language python %}}

```python
from pulumi_openstack import compute

instance = compute.Instance("test",
  flavor_name='s1-2',
  image_name='Ubuntu 16.04'
)
```

{{% /choosable %}}
{{% choosable language go %}}

```go
import (
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	compute "github.com/pulumi/pulumi-openstack/sdk/v3/go/openstack/compute"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		instance, err := compute.NewInstance(ctx, "test", &compute.InstanceArgs{
			FlavorName: pulumi.String("s1-2"),
			ImageName:  pulumi.String("Ubuntu 16.04"),
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
using System.Threading.Tasks;
using Pulumi;
using Pulumi.OpenStack;

class Program
{
    static Task Main() =>
        Deployment.Run(() => {
            var instance = new OpenStack.Compute.Instance("test", new OpenStack.Compute.InstanceArgs
            {
                FlavorName = "s1-2",
                ImageName = "Ubuntu 16.04",
            });
        });
}
```

{{% /choosable %}}

{{< /chooser >}}

## Libraries

The following packages are available in package managers:

* JavaScript/TypeScript: [`@pulumi/openstack`](https://www.npmjs.com/package/@pulumi/openstack)
* Python: [`pulumi-openstack`](https://pypi.org/project/pulumi-openstack/)
* Go: [`github.com/pulumi/pulumi-openstack/sdk/v3/go/openstack`](https://github.com/pulumi/pulumi-openstack)
* .NET: [`Pulumi.Openstack`](https://www.nuget.org/packages/Pulumi.Openstack)

As with all Pulumi software solutions, the OpenStack provider is open source and available in the [pulumi/pulumi-openstack](https://github.com/pulumi/pulumi-openstack) repo.
