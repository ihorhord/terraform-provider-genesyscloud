---
page_title: "genesyscloud_routing_email_domain Resource - terraform-provider-genesyscloud"
subcategory: ""
description: |-
  Genesys Cloud Routing Email Domain
---
# genesyscloud_routing_email_domain (Resource)

Genesys Cloud Routing Email Domain

## API Usage
The following Genesys Cloud APIs are used by this resource. Ensure your OAuth Client has been granted the necessary scopes and permissions to perform these operations:

* [GET /api/v2/routing/email/domains](https://developer.mypurecloud.com/api/rest/v2/routing/#get-api-v2-routing-email-domains)
* [POST /api/v2/routing/email/domains](https://developer.mypurecloud.com/api/rest/v2/routing/#post-api-v2-routing-email-domains)
* [GET /api/v2/routing/email/domains/{domainId}](https://developer.mypurecloud.com/api/rest/v2/routing/#get-api-v2-routing-email-domains--domainId-)
* [DELETE /api/v2/routing/email/domains/{domainId}](https://developer.mypurecloud.com/api/rest/v2/routing/#delete-api-v2-routing-email-domains--domainId-)
* [PATCH /api/v2/routing/email/domains/{domainId}](https://developer.mypurecloud.com/api/rest/v2/routing/#patch-api-v2-routing-email-domains--domainId-)

## Example Usage

```terraform
resource "genesyscloud_routing_email_domain" "example-domain-com" {
  domain_id             = "example.domain.com"
  subdomain             = false
  mail_from_domain      = "example.com"
  custom_smtp_server_id = "99490182-2695-47db-a17d-0bf2ef230827"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `domain_id` (String) Unique Id of the domain such as: 'example.com'. If subdomain is true, the Genesys Cloud regional domain is appended.

### Optional

- `custom_smtp_server_id` (String) The ID of the custom SMTP server integration to use when sending outbound emails from this domain.
- `mail_from_domain` (String) The custom MAIL FROM domain. This must be a subdomain of your email domain
- `subdomain` (Boolean) Indicates if this a Genesys Cloud sub-domain. If true, then the appropriate DNS records are created for sending/receiving email. Defaults to `false`.

### Read-Only

- `id` (String) The ID of this resource.

