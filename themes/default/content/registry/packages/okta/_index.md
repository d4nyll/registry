---
title: Okta
meta_desc: This page provides an overview of the Okta Provider for Pulumi.
layout: overview
---

The Okta provider for Pulumi can be used to provision any of the resources available in [Okta](https://www.okta.com/).

## Example

{{< chooser language "javascript,typescript,python,go,csharp" >}}

{{% choosable language javascript %}}

```javascript
const okta = require("@pulumi/okta")

const user = new okta.user.User("example-user", {
    email: "test-user@mydomain.com",
    login: "test-user@mydomain.com",
    firstName: "random",
    lastName: "user",
})
```

{{% /choosable %}}
{{% choosable language typescript %}}

```typescript
import * as okta from "@pulumi/okta";

const user = new okta.user.User("example-user", {
    email: "test-user@mydomain.com",
    login: "test-user@mydomain.com",
    firstName: "random",
    lastName: "user",
});
```

{{% /choosable %}}
{{% choosable language python %}}

```python
import pulumi_okta as okta

user = okta.user.User("example-user",
email="test-user@mydomain.com",
login="test-user@mydomain.com",
first_name="random",
last_name="user",
)
```

{{% /choosable %}}
{{% choosable language go %}}

```go
import (
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	user "github.com/pulumi/pulumi-okta/sdk/v3/go/okta/user"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		user, err := user.User(ctx, "example-user", &user.UserArgs{
			FirstName: pulumi.String("random"),
			LastName:  pulumi.String("user"),
			Email:     pulumi.String("test-user@mydomain.com"),
			Login:     pulumi.String("test-user@mydomain.com"),
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
using Pulumi.Okta.User;

class Program
{
    static Task Main() =>
        Pulumi.Deployment.RunAsync(() =>
        {
            var user = new User("example-user", new UserArgs
            {
                FirstName = "random",
                LastName = "user",
                Login = "test-user@mydomain.com",
                Email = "test-user@mydomain.com",
            });
        });
}
```

{{% /choosable %}}

{{< /chooser >}}

## Libraries

The following packages are available in packager managers:

* JavaScript/TypeScript: [`@pulumi/okta`](https://www.npmjs.com/package/@pulumi/okta)
* Python: [`pulumi-okta`](https://pypi.org/project/pulumi-okta/)
* Go: [`github.com/pulumi/pulumi-okta/sdk/v3/go/okta`](https://github.com/pulumi/pulumi-okta)
* .NET: [`Pulumi.Okta`](https://www.nuget.org/packages/Pulumi.Okta)

The Okta provider is open source and available in the [pulumi/pulumi-okta](https://github.com/pulumi/pulumi-okta) repo.
