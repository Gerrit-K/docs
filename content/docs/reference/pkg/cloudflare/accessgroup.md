
---
title: "AccessGroup"
block_external_search_index: true
---



Provides a Cloudflare Access Group resource. Access Groups are used
in conjunction with Access Policies to restrict access to a
particular resource based on group membership.

## Conditions

`require`, `exclude` and `include` arguments share the available
conditions which can be applied. The conditions are:

* `ip` - (Optional) A list of IP addresses or ranges. Example:
  `ip = ["1.2.3.4", "10.0.0.0/2"]`
* `email` - (Optional) A list of email addresses. Example:
  `email = ["test@example.com"]`
* `email_domain` - (Optional) A list of email domains. Example:
  `email_domain = ["example.com"]`
* `service_token` - (Optional) A list of service token ids. Example:
  `service_token = cloudflare_access_service_token.demo.id`
* `any_valid_service_token` - (Optional) Boolean indicating if allow
  all tokens to be granted. Example: `any_valid_service_token = true`
* `group` - (Optional) A list of access group ids. Example:
  `group = [cloudflare_access_group.demo.id]`
* `everyone` - (Optional) Boolean indicating permitting access for all
  requests. Example: `everyone = true`
* `certificate` - (Optional) Whether to use mTLS certificate authentication.
* `common_name` - (Optional) Use a certificate common name to authenticate with.
* `gsuite` - (Optional) Use GSuite as the authentication mechanism. Example:

  ```hcl
  # ... other configuration
  include {
    gsuite {
      email = "admins@example.com"
      identity_provider_id = "ca298b82-93b5-41bf-bc2d-10493f09b761"
    }
  }
  ```
* `github` - (Optional) Use a GitHub team as the `include` condition. Example:

  ```hcl
  # ... other configuration
  include {
    github {
      name = "my-github-team-name"
      identity_provider_id = "ca298b82-93b5-41bf-bc2d-10493f09b761"
    }
  }
  ```
* `azure` - (Optional) Use Azure AD as the `include` condition. Example:

  ```hcl
  # ... other configuration
  include {
    azure {
      id = "86773093-5feb-48dd-814b-7ccd3676ff50e"
      identity_provider_id = "ca298b82-93b5-41bf-bc2d-10493f09b761"
    }
  }
  ```
* `okta` - (Optional) Use Okta as the `include` condition. Example:

  ```hcl
  # ... other configuration
  include {
    okta {
      name = "admins"
      identity_provider_id = "ca298b82-93b5-41bf-bc2d-10493f09b761"
    }
  }
  ```
* `saml` - (Optional) Use an external SAML setup as the `include` condition.
  Example:

  ```hcl
  # ... other configuration
  include {
    saml {
      attribute_name = "group"
      attribute_value = "admins"
      identity_provider_id = "ca298b82-93b5-41bf-bc2d-10493f09b761"
    }
  }
  ```

> This content is derived from https://github.com/terraform-providers/terraform-provider-cloudflare/blob/master/website/docs/r/access_group.html.markdown.



## Create a AccessGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/#AccessGroup">AccessGroup</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/#AccessGroupArgs">AccessGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AccessGroup</span><span class="p">(resource_name, opts=None, </span>account_id=None<span class="p">, </span>excludes=None<span class="p">, </span>includes=None<span class="p">, </span>name=None<span class="p">, </span>requires=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAccessGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupArgs">AccessGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroup">AccessGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Cloudflare/Pulumi.Cloudflare.AccessGroup.html">AccessGroup</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Cloudflare/Pulumi.Cloudflare.AccessGroupArgs.html">AccessGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">List&lt;Access<wbr>Group<wbr>Include<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">List&lt;Access<wbr>Group<wbr>Exclude<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">List&lt;Access<wbr>Group<wbr>Require<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">[]Access<wbr>Group<wbr>Include</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">[]Access<wbr>Group<wbr>Exclude</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">[]Access<wbr>Group<wbr>Require</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">Access<wbr>Group<wbr>Include[]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">Access<wbr>Group<wbr>Exclude[]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">Access<wbr>Group<wbr>Require[]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>account_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">List[Access<wbr>Group<wbr>Include]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">List[Access<wbr>Group<wbr>Exclude]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">List[Access<wbr>Group<wbr>Require]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}










## Look up an Existing AccessGroup Resource

Get an existing AccessGroup resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/#AccessGroupState">AccessGroupState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/#AccessGroup">AccessGroup</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>account_id=None<span class="p">, </span>excludes=None<span class="p">, </span>includes=None<span class="p">, </span>name=None<span class="p">, </span>requires=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAccessGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupState">AccessGroupState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroup">AccessGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Cloudflare/Pulumi.Cloudflare.AccessGroup.html">AccessGroup</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Cloudflare/Pulumi.Cloudflare..AccessGroupState.html">AccessGroupState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">List&lt;Access<wbr>Group<wbr>Exclude<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">List&lt;Access<wbr>Group<wbr>Include<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">List&lt;Access<wbr>Group<wbr>Require<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">[]Access<wbr>Group<wbr>Exclude</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">[]Access<wbr>Group<wbr>Include</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">[]Access<wbr>Group<wbr>Require</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">Access<wbr>Group<wbr>Exclude[]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">Access<wbr>Group<wbr>Include[]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">Access<wbr>Group<wbr>Require[]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>account_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the account the group is
associated with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>excludes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupexclude">List[Access<wbr>Group<wbr>Exclude]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>includes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgroupinclude">List[Access<wbr>Group<wbr>Include]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Friendly name of the Access Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>requires</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#accessgrouprequire">List[Access<wbr>Group<wbr>Require]</a></span>
    </dt>
    <dd>{{% md %}}A series of access conditions, see below for
full list.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}










## Supporting Types

<h4>Access<wbr>Group<wbr>Exclude</h4>
{{% choosable language nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/types/input/#AccessGroupExclude">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/types/output/#AccessGroupExclude">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupExcludeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupExcludeOutput">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Access<wbr>Group<wbr>Include</h4>
{{% choosable language nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/types/input/#AccessGroupInclude">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/types/output/#AccessGroupInclude">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupIncludeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupIncludeOutput">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Access<wbr>Group<wbr>Require</h4>
{{% choosable language nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/types/input/#AccessGroupRequire">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/cloudflare/types/output/#AccessGroupRequire">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupRequireArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-cloudflare/sdk/go/cloudflare/?tab=doc#AccessGroupRequireOutput">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>email<wbr>Domains</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>emails</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>everyone</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>groups</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>ips</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}









<h3>Package Details</h3>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-cloudflare">https://github.com/pulumi/pulumi-cloudflare</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
    
</dl>
