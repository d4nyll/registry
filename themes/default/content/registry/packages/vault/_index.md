---
title: HashiCorp Vault
meta_desc: This page provides an overview of the HashiCorp Vault Provider for Pulumi.
layout: overview
---

The HashiCorp Vault provider for Pulumi can be used to provision any of the resources available in [Vault](https://www.vaultproject.io/).

## Example

{{< chooser language "javascript,typescript,python,go,csharp" >}}

{{% choosable language javascript %}}

```javascript
const vault = require("@pulumi/vault")

const be = new vault.AuthBackend("example", {
  type: "github"
});
```

{{% /choosable %}}
{{% choosable language typescript %}}

```typescript
import * as vault from "@pulumi/vault";

const be = new vault.AuthBackend("example", {
  type: "github"
});
```

{{% /choosable %}}
{{% choosable language python %}}

```python
import pulumi_vault as vault

be = vault.AuthBackend("example",
  type='github'
)
```

{{% /choosable %}}
{{% choosable language go %}}

```go
import (
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	vault "github.com/pulumi/pulumi-vault/sdk/v4/go/vault"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		be, err := vault.NewAuthBackend(ctx, "example", &vault.AuthBackendArgs{
			Type: pulumi.String("github"),
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
using Pulumi.Vault;

class Program
{
    static Task Main() =>
        Deployment.Run(() => {
            var be = new Vault.AuthBackend("example", new Vault.AuthBackendArgs
            {
                Type = "github",
            });
        });
}
```

{{% /choosable %}}

{{< /chooser >}}

## Libraries

The following packages are available in packager managers:

* JavaScript/TypeScript: [`@pulumi/vault`](https://www.npmjs.com/package/@pulumi/vault)
* Python: [`pulumi-vault`](https://pypi.org/project/pulumi-vault/)
* Go: [`github.com/pulumi/pulumi-vault/sdk/v4/go/vault`](https://github.com/pulumi/pulumi-vault)
* .NET: [`Pulumi.Vault`](https://www.nuget.org/packages/Pulumi.Vault)

The HashiCorp Vault provider is open source and available in the [pulumi/pulumi-vault](https://github.com/pulumi/pulumi-vault) repo.
