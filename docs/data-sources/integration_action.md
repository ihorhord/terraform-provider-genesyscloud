---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "genesyscloud_integration_action Data Source - terraform-provider-genesyscloud"
subcategory: ""
description: |-
Data source for Genesys Cloud integration action. Select an integration action by name
---

# genesyscloud_integration_action (Data Source)

Data source for Genesys Cloud integration action. Select an integration action by name

## Example Usage

```terraform
data "genesyscloud_integration_action" "integrationAction" {
  name = "test integration action name"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **name** (String) Integration action name.

### Optional

- **id** (String) The ID of this resource.

