
---
title: "Queue"
block_external_search_index: true
---






## Create a Queue Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/alicloud/mns/#Queue">Queue</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/alicloud/mns/#QueueArgs">QueueArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Queue</span><span class="p">(resource_name, opts=None, </span>delay_seconds=None<span class="p">, </span>maximum_message_size=None<span class="p">, </span>message_retention_period=None<span class="p">, </span>name=None<span class="p">, </span>polling_wait_seconds=None<span class="p">, </span>visibility_timeout=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewQueue<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-alicloud/sdk/go/alicloud/mns?tab=doc#QueueArgs">QueueArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-alicloud/sdk/go/alicloud/mns?tab=doc#Queue">Queue</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Alicloud/Pulumi.Alicloud.Mns.Queue.html">Queue</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Alicloud/Pulumi.AliCloud.Mns.QueueArgs.html">QueueArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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

    <dt class="property-optional"
            title="Optional">
        <span>Delay<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Maximum<wbr>Message<wbr>Size</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Message<wbr>Retention<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Polling<wbr>Wait<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Visibility<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Delay<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Maximum<wbr>Message<wbr>Size</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Message<wbr>Retention<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Polling<wbr>Wait<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Visibility<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>delay<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>maximum<wbr>Message<wbr>Size</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>message<wbr>Retention<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>polling<wbr>Wait<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>visibility<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>delay_<wbr>seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>maximum_<wbr>message_<wbr>size</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>message_<wbr>retention_<wbr>period</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>polling_<wbr>wait_<wbr>seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>visibility_<wbr>timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}










## Look up an Existing Queue Resource

Get an existing Queue resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/alicloud/mns/#QueueState">QueueState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/alicloud/mns/#Queue">Queue</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>delay_seconds=None<span class="p">, </span>maximum_message_size=None<span class="p">, </span>message_retention_period=None<span class="p">, </span>name=None<span class="p">, </span>polling_wait_seconds=None<span class="p">, </span>visibility_timeout=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetQueue<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-alicloud/sdk/go/alicloud/mns?tab=doc#QueueState">QueueState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-alicloud/sdk/go/alicloud/mns?tab=doc#Queue">Queue</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Alicloud/Pulumi.Alicloud.Mns.Queue.html">Queue</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Alicloud/Pulumi.Alicloud.Mns.QueueState.html">QueueState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Delay<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Maximum<wbr>Message<wbr>Size</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Message<wbr>Retention<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Polling<wbr>Wait<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Visibility<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Delay<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Maximum<wbr>Message<wbr>Size</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Message<wbr>Retention<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Polling<wbr>Wait<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Visibility<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>delay<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>maximum<wbr>Message<wbr>Size</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>message<wbr>Retention<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>polling<wbr>Wait<wbr>Seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>visibility<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>delay_<wbr>seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}This attribute defines the length of time, in seconds, after which every message sent to the queue is dequeued. Valid value range: 0-604800 seconds, i.e., 0 to 7 days. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>maximum_<wbr>message_<wbr>size</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}This indicates the maximum length, in bytes, of any message body sent to the queue. Valid value range: 1024-65536, i.e., 1K to 64K. Default value to 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>message_<wbr>retention_<wbr>period</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Messages are deleted from the queue after a specified length of time, whether they have been activated or not. This attribute defines the viability period, in seconds, for every message in the queue. Valid value range: 60-604800 seconds, i.e., 1 minutes to 7 days. Default value to 345600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Two queues on a single account in the same region cannot have the same name. A queue name must start with an English letter or a digit, and can contain English letters, digits, and hyphens, with the length not exceeding 256 characters .
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>polling_<wbr>wait_<wbr>seconds</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Long polling is measured in seconds. When this attribute is set to 0, long polling is disabled. When it is not set to 0, long polling is enabled and message dequeue requests will be processed only when valid messages are received or when long polling times out. Valid value range: 0-30 seconds. Default value to 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>visibility_<wbr>timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The VisibilityTimeout attribute of the queue. A dequeued messages will change from active (visible) status to inactive (invisible) status, and this attribute defines the length of time, in seconds, that messages remain invisible. Messages return to active status after the set period. Valid value range: 1-43200 seconds, i.e., 1 seconds to 12 hours. Default value to 30.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}











<h3>Package Details</h3>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-alicloud">https://github.com/pulumi/pulumi-alicloud</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
    
</dl>
