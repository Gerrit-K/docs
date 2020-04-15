
---
title: "BucketObject"
block_external_search_index: true
---



Creates a new object inside an existing bucket in Google cloud storage service (GCS). 
[ACLs](https://cloud.google.com/storage/docs/access-control/lists) can be applied using the `gcp.storage.ObjectACL` resource.
 For more information see 
[the official documentation](https://cloud.google.com/storage/docs/key-terms#objects) 
and 
[API](https://cloud.google.com/storage/docs/json_api/v1/objects).


## Example Usage

Example creating a public object in an existing `image-store` bucket.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const picture = new gcp.storage.BucketObject("picture", {
    bucket: "image-store",
    source: new pulumi.asset.FileAsset("/images/nature/garden-tiger-moth.jpg"),
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/storage_bucket_object.html.markdown.



## Create a BucketObject Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObject">BucketObject</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObjectArgs">BucketObjectArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BucketObject</span><span class="p">(resource_name, opts=None, </span>bucket=None<span class="p">, </span>cache_control=None<span class="p">, </span>content=None<span class="p">, </span>content_disposition=None<span class="p">, </span>content_encoding=None<span class="p">, </span>content_language=None<span class="p">, </span>content_type=None<span class="p">, </span>detect_md5hash=None<span class="p">, </span>metadata=None<span class="p">, </span>name=None<span class="p">, </span>source=None<span class="p">, </span>storage_class=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBucketObject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObjectArgs">BucketObjectArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObject">BucketObject</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObject.html">BucketObject</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObjectArgs.html">BucketObjectArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Source</span>
        <span class="property-indicator"></span>
        <span class="property-type">AssetOrArchive?</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Source</span>
        <span class="property-indicator"></span>
        <span class="property-type">pulumi.AssetOrArchive</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>source</span>
        <span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Asset | pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache_<wbr>control</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>language</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>type</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>detect_<wbr>md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>source</span>
        <span class="property-indicator"></span>
        <span class="property-type">Union[pulumi.Asset, pulumi.Archive]</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>storage_<wbr>class</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## BucketObject Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>Bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Output<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Self<wbr>Link</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Source</span>
        <span class="property-indicator"></span>
        <span class="property-type">AssetOrArchive?</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>Bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Output<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Self<wbr>Link</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Source</span>
        <span class="property-indicator"></span>
        <span class="property-type">pulumi.AssetOrArchive</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>output<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>self<wbr>Link</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>source</span>
        <span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Asset | pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>cache_<wbr>control</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content_<wbr>disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content_<wbr>encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content_<wbr>language</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>content_<wbr>type</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>detect_<wbr>md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>output_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>self_<wbr>link</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>source</span>
        <span class="property-indicator"></span>
        <span class="property-type">Union[pulumi.Asset, pulumi.Archive]</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>storage_<wbr>class</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Look up an Existing BucketObject Resource

Get an existing BucketObject resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObjectState">BucketObjectState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObject">BucketObject</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket=None<span class="p">, </span>cache_control=None<span class="p">, </span>content=None<span class="p">, </span>content_disposition=None<span class="p">, </span>content_encoding=None<span class="p">, </span>content_language=None<span class="p">, </span>content_type=None<span class="p">, </span>crc32c=None<span class="p">, </span>detect_md5hash=None<span class="p">, </span>md5hash=None<span class="p">, </span>metadata=None<span class="p">, </span>name=None<span class="p">, </span>output_name=None<span class="p">, </span>self_link=None<span class="p">, </span>source=None<span class="p">, </span>storage_class=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBucketObject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObjectState">BucketObjectState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObject">BucketObject</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObject.html">BucketObject</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObjectState.html">BucketObjectState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span>Bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Output<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Self<wbr>Link</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Source</span>
        <span class="property-indicator"></span>
        <span class="property-type">AssetOrArchive?</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Output<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Self<wbr>Link</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Source</span>
        <span class="property-indicator"></span>
        <span class="property-type">pulumi.AssetOrArchive</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache<wbr>Control</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Language</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content<wbr>Type</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>detect<wbr>Md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>output<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>self<wbr>Link</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>source</span>
        <span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Asset | pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>storage<wbr>Class</span>
        <span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>bucket</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the containing bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>cache_<wbr>control</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>disposition</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>encoding</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>language</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>content_<wbr>type</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to "application/octet-stream" or "text/plain; charset=utf-8".
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>crc32c</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 CRC32 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>detect_<wbr>md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>md5hash</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) Base 64 MD5 hash of the uploaded data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>metadata</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}User-provided metadata, in key/value pairs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the object. If you're interpolating the name of this object, see `output_name` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>output_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>self_<wbr>link</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) A url reference to this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>source</span>
        <span class="property-indicator"></span>
        <span class="property-type">Union[pulumi.Asset, pulumi.Archive]</span>
    </dt>
    <dd>{{% md %}}A path to the data you want to upload. Must be defined
if `content` is not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>storage_<wbr>class</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket's default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}











<h3>Package Details</h3>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-gcp">https://github.com/pulumi/pulumi-gcp</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
    
</dl>
