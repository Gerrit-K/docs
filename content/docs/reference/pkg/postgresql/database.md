
---
title: "Database"
block_external_search_index: true
---



The ``postgresql..Database`` resource creates and manages [database
objects](https://www.postgresql.org/docs/current/static/managing-databases.html)
within a PostgreSQL server instance.


## Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as postgresql from "@pulumi/postgresql";

const myDb = new postgresql.Database("my_db", {
    allowConnections: true,
    connectionLimit: -1,
    lcCollate: "C",
    owner: "my_role",
    template: "template0",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-postgresql/blob/master/website/docs/r/postgresql_database.html.markdown.



## Create a Database Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/postgresql/#Database">Database</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/postgresql/#DatabaseArgs">DatabaseArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Database</span><span class="p">(resource_name, opts=None, </span>allow_connections=None<span class="p">, </span>connection_limit=None<span class="p">, </span>encoding=None<span class="p">, </span>is_template=None<span class="p">, </span>lc_collate=None<span class="p">, </span>lc_ctype=None<span class="p">, </span>name=None<span class="p">, </span>owner=None<span class="p">, </span>tablespace_name=None<span class="p">, </span>template=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDatabase<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-postgresql/sdk/go/postgresql/?tab=doc#DatabaseArgs">DatabaseArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-postgresql/sdk/go/postgresql/?tab=doc#Database">Database</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Postgresql/Pulumi.Postgresql.Database.html">Database</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Postgresql/Pulumi.PostgreSql.DatabaseArgs.html">DatabaseArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Allow<wbr>Connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Is<wbr>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tablespace<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Allow<wbr>Connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Is<wbr>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tablespace<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>allow<wbr>Connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>is<wbr>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc<wbr>Collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc<wbr>Ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tablespace<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>template</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>allow_<wbr>connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection_<wbr>limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>is_<wbr>template</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc_<wbr>collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc_<wbr>ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tablespace_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>template</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}










## Look up an Existing Database Resource

Get an existing Database resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/postgresql/#DatabaseState">DatabaseState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/postgresql/#Database">Database</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allow_connections=None<span class="p">, </span>connection_limit=None<span class="p">, </span>encoding=None<span class="p">, </span>is_template=None<span class="p">, </span>lc_collate=None<span class="p">, </span>lc_ctype=None<span class="p">, </span>name=None<span class="p">, </span>owner=None<span class="p">, </span>tablespace_name=None<span class="p">, </span>template=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDatabase<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-postgresql/sdk/go/postgresql/?tab=doc#DatabaseState">DatabaseState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-postgresql/sdk/go/postgresql/?tab=doc#Database">Database</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Postgresql/Pulumi.Postgresql.Database.html">Database</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Postgresql/Pulumi.Postgresql..DatabaseState.html">DatabaseState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Allow<wbr>Connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Is<wbr>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tablespace<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Allow<wbr>Connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Is<wbr>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Lc<wbr>Ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Tablespace<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>allow<wbr>Connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection<wbr>Limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>is<wbr>Template</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc<wbr>Collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc<wbr>Ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tablespace<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>template</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>allow_<wbr>connections</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `false` then no one can connect to this
database. The default is `true`, allowing connections (except as restricted by
other mechanisms, such as `GRANT` or `REVOKE CONNECT`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection_<wbr>limit</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How many concurrent connections can be
established to this database. `-1` (the default) means no limit.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Character set encoding to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>is_<wbr>template</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, then this database can be cloned by any
user with `CREATEDB` privileges; if `false` (the default), then only
superusers or the owner of the database can clone it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc_<wbr>collate</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Collation order (LC_COLLATE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>lc_<wbr>ctype</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Character classification (LC_CTYPE) to use in the new database
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database. Must be unique on the PostgreSQL
server instance where it is configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>owner</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The role name of the user who will own the database, or
`DEFAULT` to use the default (namely, the user executing the command). To
create a database owned by another role or to change the owner of an existing
database, you must be a direct or indirect member of the specified role, or
the username in the provider is a superuser.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>tablespace_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the tablespace that will be
associated with the database, or `DEFAULT` to use the template database's
tablespace.  This tablespace will be the default tablespace used for objects
created in this database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>template</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the template from which to create the new database
{{% /md %}}</dd>

</dl>
{{% /choosable %}}











<h3>Package Details</h3>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-postgresql">https://github.com/pulumi/pulumi-postgresql</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
    
</dl>
