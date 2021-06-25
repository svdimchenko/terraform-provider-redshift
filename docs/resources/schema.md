---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "redshift_schema Resource - terraform-provider-redshift"
subcategory: ""
description: |-
  A database contains one or more named schemas. Each schema in a database contains tables and other kinds of named objects. By default, a database has a single schema, which is named PUBLIC. You can use schemas to group database objects under a common name. Schemas are similar to file system directories, except that schemas cannot be nested.
---

# redshift_schema (Resource)

A database contains one or more named schemas. Each schema in a database contains tables and other kinds of named objects. By default, a database has a single schema, which is named PUBLIC. You can use schemas to group database objects under a common name. Schemas are similar to file system directories, except that schemas cannot be nested.

## Example Usage

```terraform
resource "redshift_user" "owner" {
  name = "owner"
}

resource "redshift_schema" "schema" {
  name  = "my_schema"
  owner = redshift_user.owner.name
  quota = 150
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **name** (String) Name of the schema. The schema name can't be `PUBLIC`.

### Optional

- **cascade_on_delete** (Boolean) Indicates to automatically drop all objects in the schema. The default action is TO NOT drop a schema if it contains any objects.
- **id** (String) The ID of this resource.
- **owner** (String) Name of the schema owner.
- **quota** (Number) The maximum amount of disk space that the specified schema can use. GB is the default unit of measurement.

