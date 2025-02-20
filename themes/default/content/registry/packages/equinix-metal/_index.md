---
title: Equinix Metal
meta_desc: This page provides an overview of the Equinix Metal provider for Pulumi.
layout: overview
---

The Equinix Metal provider for Pulumi can be used to provision any of the cloud resources available in [Equinix Metal](https://metal.equinix.com/).
The Equinix Metal provider must be configured with credentials to deploy and update resources in Equinix Metal.

## Example

{{< chooser language "javascript,typescript,python,go,csharp" >}}

{{% choosable language javascript %}}

```javascript
import * as metal from "@pulumi/equinix-metal";

const project = new metal.Project("my-project", {
  name: "DevelopmentEnvironment"
});
```

{{% /choosable %}}
{{% choosable language typescript %}}

```typescript
import * as metal from "@pulumi/equinix-metal";

const project = new metal.Project("my-project", {
  name: "DevelopmentEnvironment"
});
```

{{% /choosable %}}
{{% choosable language python %}}

```python
import pulumi_equinix_metal as metal
project = metal.Project("my-project",
  name='DevelopmentEnvironment'
)
```

{{% /choosable %}}
{{% choosable language go %}}

```go
import (
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	metal "github.com/pulumi/pulumi-equinix-metal/sdk/v2/go/equinix"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		project, err := metal.NewProject(ctx, "test", &metal.ProjectArgs{
			Name: pulumi.String("DevelopmentEnvironment"),
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
using Pulumi.EquinixMetal;

class Program
{
    static Task Main() =>
        Deployment.Run(() => {
            var project = new EquinixMetal.Project("my-project", new EquinixMetal.ProjectArgs
            {
                Name = "DevelopmentEnvironment"
            });
        });
}
```

{{% /choosable %}}

{{< /chooser >}}

## Libraries

The following packages are available in packager managers:

* JavaScript/TypeScript: [`@pulumi/equinix-metal`](https://www.npmjs.com/package/@pulumi/equinix-metal)
* Python: [`pulumi-equinix-metal`](https://pypi.org/project/pulumi-equinix-metal/)
* Go: [`github.com/pulumi/pulumi-equinix-metal/sdk/v2/go/equinix`](https://github.com/pulumi/pulumi-equinix-metal)
* .NET: [`Pulumi.EquinixMetal`](https://www.nuget.org/packages/Pulumi.EquinixMetal)

The Equinix Metal provider is open source and available in the [pulumi/pulumi-equinix-metal](https://github.com/pulumi/pulumi-equinix-metal) repo.
