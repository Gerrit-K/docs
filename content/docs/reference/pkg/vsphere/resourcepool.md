
---
title: "ResourcePool"
block_external_search_index: true
---



The `vsphere..ResourcePool` resource can be used to create and manage
resource pools in standalone hosts or on compute clusters.

For more information on vSphere resource pools, see [this
page][ref-vsphere-resource_pools].

[ref-vsphere-resource_pools]: https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.resmgmt.doc/GUID-60077B40-66FF-4625-934A-641703ED7601.html

## Example Usage

The following example sets up a resource pool in a compute cluster which uses
the default settings for CPU and memory reservations, shares, and limits. The
compute cluster needs to already exist in vSphere.  

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as vsphere from "@pulumi/vsphere";

const config = new pulumi.Config();
const datacenter = config.get("datacenter") || "dc1";
const cluster = config.get("cluster") || "cluster1";

const dc = pulumi.output(vsphere.getDatacenter({
    name: datacenter,
}, { async: true }));
const computeCluster = dc.apply(dc => vsphere.getComputeCluster({
    datacenterId: dc.id,
    name: cluster,
}, { async: true }));
const resourcePool = new vsphere.ResourcePool("resource_pool", {
    parentResourcePoolId: computeCluster.resourcePoolId,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-vsphere/blob/master/website/docs/r/resource_pool.html.markdown.



## Create a ResourcePool Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/vsphere/#ResourcePool">ResourcePool</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/vsphere/#ResourcePoolArgs">ResourcePoolArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ResourcePool</span><span class="p">(resource_name, opts=None, </span>cpu_expandable=None<span class="p">, </span>cpu_limit=None<span class="p">, </span>cpu_reservation=None<span class="p">, </span>cpu_share_level=None<span class="p">, </span>cpu_shares=None<span class="p">, </span>custom_attributes=None<span class="p">, </span>memory_expandable=None<span class="p">, </span>memory_limit=None<span class="p">, </span>memory_reservation=None<span class="p">, </span>memory_share_level=None<span class="p">, </span>memory_shares=None<span class="p">, </span>name=None<span class="p">, </span>parent_resource_pool_id=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewResourcePool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-vsphere/sdk/go/vsphere/?tab=doc#ResourcePoolArgs">ResourcePoolArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-vsphere/sdk/go/vsphere/?tab=doc#ResourcePool">ResourcePool</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Vsphere/Pulumi.Vsphere.ResourcePool.html">ResourcePool</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Vsphere/Pulumi.VSphere.ResourcePoolArgs.html">ResourcePoolArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        <span>args</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        <span>args</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        <span>args</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

#### Resource Arguments




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Parent<wbr>Resource<wbr>Pool<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>Attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Parent<wbr>Resource<wbr>Pool<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>Attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>parent<wbr>Resource<wbr>Pool<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom<wbr>Attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>parent_<wbr>resource_<wbr>pool_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>share_<wbr>level</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom_<wbr>attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>share_<wbr>level</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}










## Look up an Existing ResourcePool Resource

Get an existing ResourcePool resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/vsphere/#ResourcePoolState">ResourcePoolState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/vsphere/#ResourcePool">ResourcePool</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>cpu_expandable=None<span class="p">, </span>cpu_limit=None<span class="p">, </span>cpu_reservation=None<span class="p">, </span>cpu_share_level=None<span class="p">, </span>cpu_shares=None<span class="p">, </span>custom_attributes=None<span class="p">, </span>memory_expandable=None<span class="p">, </span>memory_limit=None<span class="p">, </span>memory_reservation=None<span class="p">, </span>memory_share_level=None<span class="p">, </span>memory_shares=None<span class="p">, </span>name=None<span class="p">, </span>parent_resource_pool_id=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetResourcePool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-vsphere/sdk/go/vsphere/?tab=doc#ResourcePoolState">ResourcePoolState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-vsphere/sdk/go/vsphere/?tab=doc#ResourcePool">ResourcePool</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Vsphere/Pulumi.Vsphere.ResourcePool.html">ResourcePool</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Vsphere/Pulumi.Vsphere..ResourcePoolState.html">ResourcePoolState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Optional">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

The following state arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>Attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Parent<wbr>Resource<wbr>Pool<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cpu<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>Attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Memory<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Parent<wbr>Resource<wbr>Pool<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom<wbr>Attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Share<wbr>Level</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory<wbr>Shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>parent<wbr>Resource<wbr>Pool<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>share_<wbr>level</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `cpu_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cpu_<wbr>shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`cpu_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom_<wbr>attributes</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A list of custom attributes to set on this resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>expandable</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines if the reservation on a resource
pool can grow beyond the specified value if the parent resource pool has
unreserved resources. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The CPU utilization of a resource pool will not exceed
this limit, even if there are available resources. Set to `-1` for unlimited.
Default: `-1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>reservation</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of CPU (MHz) that is guaranteed
available to the resource pool. Default: `0`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>share_<wbr>level</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CPU allocation level. The level is a
simplified view of shares. Levels map to a pre-determined set of numeric
values for shares. Can be one of `low`, `normal`, `high`, or `custom`. When
`low`, `normal`, or `high` are specified values in `memory_shares` will be
ignored.  Default: `normal`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>memory_<wbr>shares</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of shares allocated for CPU. Used to
determine resource allocation in case of resource contention. If this is set,
`memory_share_level` must be `custom`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>parent_<wbr>resource_<wbr>pool_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [managed object ID][docs-about-morefs]
of the parent resource pool. This can be the root resource pool for a cluster
or standalone host, or a resource pool itself. When moving a resource pool
from one parent resource pool to another, both must share a common root
resource pool or the move will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tags</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The IDs of any tags to attach to this resource. See
[here][docs-applying-tags] for a reference on how to apply tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}











<h3>Package Details</h3>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-vsphere">https://github.com/pulumi/pulumi-vsphere</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
    
</dl>
