---
page_title: "genesyscloud_outbound_contact_list Resource - terraform-provider-genesyscloud"
subcategory: ""
description: |-
  Genesys Cloud Outbound Contact List
---
# genesyscloud_outbound_contact_list (Resource)

Genesys Cloud Outbound Contact List

## API Usage
The following Genesys Cloud APIs are used by this resource. Ensure your OAuth Client has been granted the necessary scopes and permissions to perform these operations:

- [GET /api/v2/outbound/contactlists](https://developer.genesys.cloud/devapps/api-explorer#get-api-v2-outbound-contactlists)
- [POST /api/v2/outbound/contactlists](https://developer.genesys.cloud/devapps/api-explorer#post-api-v2-outbound-contactlists)
- [GET /api/v2/outbound/contactlists/{contactListId}](https://developer.genesys.cloud/devapps/api-explorer#get-api-v2-outbound-contactlists--contactListId-)
- [PUT /api/v2/outbound/contactlists/{contactListId}](https://developer.genesys.cloud/devapps/api-explorer#put-api-v2-outbound-contactlists--contactListId-)
- [DELETE /api/v2/outbound/contactlists/{contactListId}](https://developer.genesys.cloud/devapps/api-explorer#delete-api-v2-outbound-contactlists--contactListId-)

## Example Usage

```terraform
resource "genesyscloud_outbound_contact_list" "contact-list" {
  name             = "Example Contact List"
  column_names     = ["First Name", "Last Name", "Cell", "Home"]
  attempt_limit_id = genesyscloud_outbound_attempt_limit.attempt-limit.id
  phone_columns {
    column_name = "Cell"
    type        = "cell"
  }
  phone_columns {
    column_name = "Home"
    type        = "home"
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `column_names` (List of String) The names of the contact data columns.

### Optional

- `attempt_limit_id` (String) Attempt Limit for this ContactList.
- `automatic_time_zone_mapping` (Boolean) Indicates if automatic time zone mapping is to be used for this ContactList.
- `division_id` (String) The division this entity belongs to.
- `name` (String) The name for the contact list.
- `phone_columns` (Block Set) Indicates which columns are phone numbers. (see [below for nested schema](#nestedblock--phone_columns))
- `preview_mode_accepted_values` (List of String) The values in the previewModeColumnName column that indicate a contact should always be dialed in preview mode.
- `preview_mode_column_name` (String) A column to check if a contact should always be dialed in preview mode.
- `zip_code_column_name` (String) The name of contact list column containing the zip code for use with automatic time zone mapping. Only allowed if 'automaticTimeZoneMapping' is set to true.

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--phone_columns"></a>
### Nested Schema for `phone_columns`

Required:

- `column_name` (String) The name of the phone column.
- `type` (String) Indicates the type of the phone column. For example, 'cell' or 'home'.

Optional:

- `callable_time_column` (String) A column that indicates the timezone to use for a given contact when checking callable times. Not allowed if 'automaticTimeZoneMapping' is set to true.
