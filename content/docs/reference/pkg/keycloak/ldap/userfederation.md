
---
title: "UserFederation"
block_external_search_index: true
---



## # keycloak.ldap.UserFederation

Allows for creating and managing LDAP user federation providers within Keycloak.

Keycloak can use an LDAP user federation provider to federate users to Keycloak
from a directory system such as LDAP or Active Directory. Federated users
will exist within the realm and will be able to log in to clients. Federated
users can have their attributes defined using mappers.

### Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as keycloak from "@pulumi/keycloak";

const realm = new keycloak.Realm("realm", {
    enabled: true,
    realm: "test",
});
const ldapUserFederation = new keycloak.ldap.UserFederation("ldap_user_federation", {
    bindCredential: "admin",
    bindDn: "cn=admin,dc=example,dc=org",
    connectionTimeout: "5s",
    connectionUrl: "ldap://openldap",
    enabled: true,
    rdnLdapAttribute: "cn",
    readTimeout: "10s",
    realmId: realm.id,
    userObjectClasses: [
        "simpleSecurityObject",
        "organizationalRole",
    ],
    usernameLdapAttribute: "cn",
    usersDn: "dc=example,dc=org",
    uuidLdapAttribute: "entryDN",
});
```

### Argument Reference

The following arguments are supported:

- `realm_id` - (Required) The realm that this provider will provide user federation for.
- `name` - (Required) Display name of the provider when displayed in the console.
- `enabled` - (Optional) When `false`, this provider will not be used when performing queries for users. Defaults to `true`.
- `priority` - (Optional) Priority of this provider when looking up users. Lower values are first. Defaults to `0`.
- `import_enabled` - (Optional) When `true`, LDAP users will be imported into the Keycloak database. Defaults to `true`.
- `edit_mode` - (Optional) Can be one of `READ_ONLY`, `WRITABLE`, or `UNSYNCED`. `UNSYNCED` allows user data to be imported but not synced back to LDAP. Defaults to `READ_ONLY`.
- `sync_registrations` - (Optional) When `true`, newly created users will be synced back to LDAP. Defaults to `false`.
- `vendor` - (Optional) Can be one of `OTHER`, `EDIRECTORY`, `AD`, `RHDS`, or `TIVOLI`. When this is selected in the GUI, it provides reasonable defaults for other fields. When used with the Keycloak API, this attribute does nothing, but is still required. Defaults to `OPTIONAL`.
- `username_ldap_attribute` - (Required) Name of the LDAP attribute to use as the Keycloak username.
- `rdn_ldap_attribute` - (Required) Name of the LDAP attribute to use as the relative distinguished name.
- `uuid_ldap_attribute` - (Required) Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
- `user_object_classes` - (Required) Array of all values of LDAP objectClass attribute for users in LDAP. Must contain at least one.
- `connection_url` - (Required) Connection URL to the LDAP server.
- `users_dn` - (Required) Full DN of LDAP tree where your users are.
- `bind_dn` - (Optional) DN of LDAP admin, which will be used by Keycloak to access LDAP server. This attribute must be set if `bind_credential` is set.
- `bind_credential` - (Optional) Password of LDAP admin. This attribute must be set if `bind_dn` is set.
- `custom_user_search_filter` - (Optional) Additional LDAP filter for filtering searched users. Must begin with `(` and end with `)`.
- `search_scope` - (Optional) Can be one of `ONE_LEVEL` or `SUBTREE`:
    - `ONE_LEVEL`: Only search for users in the DN specified by `user_dn`.
    - `SUBTREE`: Search entire LDAP subtree.
- `validate_password_policy` - (Optional) When `true`, Keycloak will validate passwords using the realm policy before updating it.
- `use_truststore_spi` - (Optional) Can be one of `ALWAYS`, `ONLY_FOR_LDAPS`, or `NEVER`:
    - `ALWAYS` - Always use the truststore SPI for LDAP connections.
    - `NEVER` - Never use the truststore SPI for LDAP connections.
    - `ONLY_FOR_LDAPS` - Only use the truststore SPI if your LDAP connection uses the ldaps protocol.
- `connection_timeout` - (Optional) LDAP connection timeout in the format of a [Go duration string](https://golang.org/pkg/time/#Duration.String).
- `read_timeout` - (Optional) LDAP read timeout in the format of a [Go duration string](https://golang.org/pkg/time/#Duration.String).
- `pagination` - (Optional) When true, Keycloak assumes the LDAP server supports pagination. Defaults to `true`.
- `batch_size_for_sync` - (Optional) The number of users to sync within a single transaction. Defaults to `1000`.
- `full_sync_period` - (Optional) How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
- `changed_sync_period` - (Optional) How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users sync.
- `cache_policy` - (Optional) Can be one of `DEFAULT`, `EVICT_DAILY`, `EVICT_WEEKLY`, `MAX_LIFESPAN`, or `NO_CACHE`. Defaults to `DEFAULT`.

> This content is derived from https://github.com/mrparkers/terraform-provider-keycloak/blob/master/website/docs/r/keycloak_ldap_user_federation.html.markdown.



## Create a UserFederation Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/keycloak/ldap/#UserFederation">UserFederation</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/keycloak/ldap/#UserFederationArgs">UserFederationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">UserFederation</span><span class="p">(resource_name, opts=None, </span>batch_size_for_sync=None<span class="p">, </span>bind_credential=None<span class="p">, </span>bind_dn=None<span class="p">, </span>cache_policy=None<span class="p">, </span>changed_sync_period=None<span class="p">, </span>connection_timeout=None<span class="p">, </span>connection_url=None<span class="p">, </span>custom_user_search_filter=None<span class="p">, </span>edit_mode=None<span class="p">, </span>enabled=None<span class="p">, </span>full_sync_period=None<span class="p">, </span>import_enabled=None<span class="p">, </span>name=None<span class="p">, </span>pagination=None<span class="p">, </span>priority=None<span class="p">, </span>rdn_ldap_attribute=None<span class="p">, </span>read_timeout=None<span class="p">, </span>realm_id=None<span class="p">, </span>search_scope=None<span class="p">, </span>sync_registrations=None<span class="p">, </span>use_truststore_spi=None<span class="p">, </span>user_object_classes=None<span class="p">, </span>username_ldap_attribute=None<span class="p">, </span>users_dn=None<span class="p">, </span>uuid_ldap_attribute=None<span class="p">, </span>validate_password_policy=None<span class="p">, </span>vendor=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewUserFederation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-keycloak/sdk/go/keycloak/ldap?tab=doc#UserFederationArgs">UserFederationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-keycloak/sdk/go/keycloak/ldap?tab=doc#UserFederation">UserFederation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Keycloak/Pulumi.Keycloak.Ldap.UserFederation.html">UserFederation</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Keycloak/Pulumi.Keycloak.Ldap.UserFederationArgs.html">UserFederationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Connection<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Rdn<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Realm<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>User<wbr>Object<wbr>Classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Username<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Users<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Uuid<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Batch<wbr>Size<wbr>For<wbr>Sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Changed<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>User<wbr>Search<wbr>Filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Edit<wbr>Mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Full<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Import<wbr>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Read<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Search<wbr>Scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Sync<wbr>Registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Use<wbr>Truststore<wbr>Spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Validate<wbr>Password<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Connection<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Rdn<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Realm<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>User<wbr>Object<wbr>Classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Username<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Users<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Uuid<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Batch<wbr>Size<wbr>For<wbr>Sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Changed<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>User<wbr>Search<wbr>Filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Edit<wbr>Mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Full<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Import<wbr>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Read<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Search<wbr>Scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Sync<wbr>Registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Use<wbr>Truststore<wbr>Spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Validate<wbr>Password<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>connection<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>rdn<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>realm<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>user<wbr>Object<wbr>Classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>username<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>users<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>uuid<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>batch<wbr>Size<wbr>For<wbr>Sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind<wbr>Credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>changed<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom<wbr>User<wbr>Search<wbr>Filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>edit<wbr>Mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>full<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>import<wbr>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>read<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>search<wbr>Scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>sync<wbr>Registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>use<wbr>Truststore<wbr>Spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>validate<wbr>Password<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>connection_<wbr>url</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>rdn_<wbr>ldap_<wbr>attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>realm_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>user_<wbr>object_<wbr>classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>username_<wbr>ldap_<wbr>attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>users_<wbr>dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>uuid_<wbr>ldap_<wbr>attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>batch_<wbr>size_<wbr>for_<wbr>sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind_<wbr>credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind_<wbr>dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache_<wbr>policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>changed_<wbr>sync_<wbr>period</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection_<wbr>timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom_<wbr>user_<wbr>search_<wbr>filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>edit_<wbr>mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>full_<wbr>sync_<wbr>period</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>import_<wbr>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>read_<wbr>timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>search_<wbr>scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>sync_<wbr>registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>use_<wbr>truststore_<wbr>spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>validate_<wbr>password_<wbr>policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}










## Look up an Existing UserFederation Resource

Get an existing UserFederation resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/keycloak/ldap/#UserFederationState">UserFederationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/keycloak/ldap/#UserFederation">UserFederation</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>batch_size_for_sync=None<span class="p">, </span>bind_credential=None<span class="p">, </span>bind_dn=None<span class="p">, </span>cache_policy=None<span class="p">, </span>changed_sync_period=None<span class="p">, </span>connection_timeout=None<span class="p">, </span>connection_url=None<span class="p">, </span>custom_user_search_filter=None<span class="p">, </span>edit_mode=None<span class="p">, </span>enabled=None<span class="p">, </span>full_sync_period=None<span class="p">, </span>import_enabled=None<span class="p">, </span>name=None<span class="p">, </span>pagination=None<span class="p">, </span>priority=None<span class="p">, </span>rdn_ldap_attribute=None<span class="p">, </span>read_timeout=None<span class="p">, </span>realm_id=None<span class="p">, </span>search_scope=None<span class="p">, </span>sync_registrations=None<span class="p">, </span>use_truststore_spi=None<span class="p">, </span>user_object_classes=None<span class="p">, </span>username_ldap_attribute=None<span class="p">, </span>users_dn=None<span class="p">, </span>uuid_ldap_attribute=None<span class="p">, </span>validate_password_policy=None<span class="p">, </span>vendor=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetUserFederation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-keycloak/sdk/go/keycloak/ldap?tab=doc#UserFederationState">UserFederationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-keycloak/sdk/go/keycloak/ldap?tab=doc#UserFederation">UserFederation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Keycloak/Pulumi.Keycloak.Ldap.UserFederation.html">UserFederation</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Keycloak/Pulumi.Keycloak.Ldap.UserFederationState.html">UserFederationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Batch<wbr>Size<wbr>For<wbr>Sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Changed<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>User<wbr>Search<wbr>Filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Edit<wbr>Mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Full<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Import<wbr>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Rdn<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Read<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Realm<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Search<wbr>Scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Sync<wbr>Registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Use<wbr>Truststore<wbr>Spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>User<wbr>Object<wbr>Classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Username<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Users<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Uuid<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Validate<wbr>Password<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Batch<wbr>Size<wbr>For<wbr>Sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Bind<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Changed<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Connection<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Custom<wbr>User<wbr>Search<wbr>Filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Edit<wbr>Mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Full<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Import<wbr>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Rdn<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Read<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Realm<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Search<wbr>Scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Sync<wbr>Registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Use<wbr>Truststore<wbr>Spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>User<wbr>Object<wbr>Classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Username<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Users<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Uuid<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Validate<wbr>Password<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>batch<wbr>Size<wbr>For<wbr>Sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind<wbr>Credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>changed<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom<wbr>User<wbr>Search<wbr>Filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>edit<wbr>Mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>full<wbr>Sync<wbr>Period</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>import<wbr>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>rdn<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>read<wbr>Timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>realm<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>search<wbr>Scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>sync<wbr>Registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>use<wbr>Truststore<wbr>Spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>user<wbr>Object<wbr>Classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>username<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>users<wbr>Dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>uuid<wbr>Ldap<wbr>Attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>validate<wbr>Password<wbr>Policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>batch_<wbr>size_<wbr>for_<wbr>sync</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of users to sync within a single transaction.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind_<wbr>credential</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password of LDAP admin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>bind_<wbr>dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}DN of LDAP admin, which will be used by Keycloak to access LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache_<wbr>policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>changed_<wbr>sync_<wbr>period</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync changed LDAP users, in seconds. Omit this property to disable periodic changed users
sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection_<wbr>timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}LDAP connection timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>connection_<wbr>url</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Connection URL to the LDAP server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>custom_<wbr>user_<wbr>search_<wbr>filter</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Additional LDAP filter for filtering searched users. Must begin with '(' and end with ')'.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>edit_<wbr>mode</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}READ_ONLY and WRITABLE are self-explanatory. UNSYNCED allows user data to be imported but not synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When false, this provider will not be used when performing queries for users.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>full_<wbr>sync_<wbr>period</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How frequently Keycloak should sync all LDAP users, in seconds. Omit this property to disable periodic full sync.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>import_<wbr>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, LDAP users will be imported into the Keycloak database.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Display name of the provider when displayed in the console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>pagination</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak assumes the LDAP server supports pagination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>priority</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Priority of this provider when looking up users. Lower values are first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>rdn_<wbr>ldap_<wbr>attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the relative distinguished name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>read_<wbr>timeout</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}LDAP read timeout (duration string)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>realm_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The realm this provider will provide user federation for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>search_<wbr>scope</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ONE_LEVEL: only search for users in the DN specified by user_dn. SUBTREE: search entire LDAP subtree.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>sync_<wbr>registrations</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, newly created users will be synced back to LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>use_<wbr>truststore_<wbr>spi</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>user_<wbr>object_<wbr>classes</span>
        <span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}All values of LDAP objectClass attribute for users in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>username_<wbr>ldap_<wbr>attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as the Keycloak username.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>users_<wbr>dn</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Full DN of LDAP tree where your users are.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>uuid_<wbr>ldap_<wbr>attribute</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the LDAP attribute to use as a unique object identifier for objects in LDAP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>validate_<wbr>password_<wbr>policy</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When true, Keycloak will validate passwords using the realm policy before updating it.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>vendor</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}LDAP vendor. I am almost certain this field does nothing, but the UI indicates that it is required.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}











<h3>Package Details</h3>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-keycloak">https://github.com/pulumi/pulumi-keycloak</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
    
</dl>
