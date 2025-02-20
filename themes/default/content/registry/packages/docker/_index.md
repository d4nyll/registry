---
title: Docker
meta_desc: This page provides an overview of the Docker Provider for Pulumi.
layout: overview
---

The Docker provider for Pulumi can be used to provision any of the resources available in [Docker](https://www.docker.com/).

## Example

{{< chooser language "javascript,typescript,python,go,csharp" >}}

{{% choosable language javascript %}}

```javascript
const docker = require("@pulumi/docker")

const image = new docker.RemoteImage("ubuntu", {
  name: "ubuntu:precise"
});

const container = new docker.Container("ubuntu", {
  image: image.latest,
});
```

{{% /choosable %}}
{{% choosable language typescript %}}

```typescript
import * as docker from "@pulumi/docker";

const image = new docker.RemoteImage("ubuntu", {
  name: "ubuntu:precise"
});

const container = new docker.Container("ubuntu", {
  image: image.latest,
});
```

{{% /choosable %}}
{{% choosable language python %}}

```python
import pulumi_docker as docker

image = docker.RemoteImage("ubuntu",
  name='ubuntu:precise'
)

container = docker.Container("ubuntu",
  image=image.latest
)
```

{{% /choosable %}}
{{% choosable language go %}}

```go
import (
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	do "github.com/pulumi/pulumi-docker/sdk/v3/go/docker"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		image, err := docker.NewRemoteImage(ctx, "ubuntu", &docker.RemoteImageArgs{
			Name: pulumi.String("ubuntu:precise"),
		})
		if err != nil {
			return err
		}

		container, err := docker.NewContainer(ctx, "ubuntu", &docker.ContainerArgs{
			Image: image.Latest(),
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
using Pulumi.Docker;

class Program
{
    static Task Main() =>
        Deployment.Run(() => {
            var image = new Docker.RemoteImage("ubuntu", new Docker.RemoteImageArgs
            {
                Name = "ubuntu:precise",
            });

            var container = new Docker.Container("ubuntu", new Docker.ContainerArgs
            {
                Image = image.Latest,
            });
        });
}
```

{{% /choosable %}}

{{< /chooser >}}

## Libraries

The following packages are available in packager managers:

* JavaScript/TypeScript: [`@pulumi/docker`](https://www.npmjs.com/package/@pulumi/docker)
* Python: [`pulumi-docker`](https://pypi.org/project/pulumi-docker/)
* Go: [`github.com/pulumi/pulumi-docker/sdk/v3/go/docker`](https://github.com/pulumi/pulumi-docker)
* .NET: [`Pulumi.Docker`](https://www.nuget.org/packages/Pulumi.Docker)

The Docker provider is open source and available in the [pulumi/pulumi-docker](https://github.com/pulumi/pulumi-docker) repo.
