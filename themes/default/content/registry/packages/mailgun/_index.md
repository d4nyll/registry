---
title: Mailgun
meta_desc: This page provides an overview of the Mailgun Provider for Pulumi.
layout: overview
---

The Mailgun provider for Pulumi can be used to provision any of the cloud resources available in [Mailgun](https://www.mailgun.com/).
The Mailgun provider must be configured with credentials to deploy and update resources in Mailgun.

## Example

{{< chooser language "javascript,typescript,python,go,csharp" >}}

{{% choosable language javascript %}}

```javascript
const mailgun = require("@pulumi/mailgun")

const route = new mailgun.Route("test-route", {
    priority: 0,
    description: "Inbound route",
    expression: "match_recipient('.*@example.com')",
    actions: [
        "forward('http://example.com/api/v1/foos/')",
        "stop()"
    ]
});
```

{{% /choosable %}}
{{% choosable language typescript %}}

```typescript
import * as mailgun from "@pulumi/mailgun";

const route = new mailgun.Route("test-route", {
    priority: 0,
    description: "Inbound route",
    expression: "match_recipient('.*@example.com')",
    actions: [
        "forward('http://example.com/api/v1/foos/')",
        "stop()"
    ]
});
```

{{% /choosable %}}
{{% choosable language python %}}

```python
import pulumi_mailgun as mailgun

route = mailgun.Route("test-route",
  priority=0,
  description="Inbound route",
  expression="match_recipient('.*@example.com')",
  actions=[
    "forward('http://example.com/api/v1/foos/')",
    "stop()"
])
```

{{% /choosable %}}
{{% choosable language go %}}

```go
import (
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	mailgun "github.com/pulumi/pulumi-mailgun/sdk/v3/go/mailgun"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		route, err := mailgun.NewRoute(ctx, "test-route", &mailgun.RouteArgs{
			Priority:    pulumi.Int(0),
			Description: pulumi.String("Inbound route"),
			Expression:  pulumi.String("match_recipient('.*@example.com')"),
			Actions: []string{
				pulumi.String("forward('http://example.com/api/v1/foos/')"),
				pulumi.String("stop()"),
			},
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
using Pulumi.Mailgun;

class Program
{
    static Task Main() =>
        Deployment.Run(() => {
            var route = new Route("test-route", new RouteArgs
            {
                Priority = 0,
                Description = "Inbound route",
                Expression = "match_recipient('.*@example.com')",
                Actions = [
                    "forward('http://example.com/api/v1/foos/')",
                    "stop()"
                ],
            });
        });
}
```

{{% /choosable %}}

{{< /chooser >}}

## Libraries

The following packages are available in packager managers:

* JavaScript/TypeScript: [`@pulumi/mailgun`](https://www.npmjs.com/package/@pulumi/mailgun)
* Python: [`pulumi-mailgun`](https://pypi.org/project/pulumi-mailgun/)
* Go: [`github.com/pulumi/pulumi-mailgun/sdk/v3/go/mailgun`](https://github.com/pulumi/pulumi-mailgun)
* .NET: [`Pulumi.Mailgun`](https://www.nuget.org/packages/Pulumi.Mailgun)

The Mailgun provider is open source and available in the [pulumi/pulumi-mailgun](https://github.com/pulumi/pulumi-mailgun) repo.
