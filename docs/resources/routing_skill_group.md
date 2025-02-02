---
page_title: "genesyscloud_routing_skill_group Resource - terraform-provider-genesyscloud"
subcategory: ""
description: |-
  Genesys Cloud Skill Group
---
# genesyscloud_routing_skill_group (Resource)

Genesys Cloud Skill Group

## API Usage
The following Genesys Cloud APIs are used by this resource. Ensure your OAuth Client has been granted the necessary scopes and permissions to perform these operations:

[GET /api/v2/routing/skillgroups](https://developer.genesys.cloud/platform/preview-apis#get-api-v2-routing-skillgroups)
[POST /api/v2/routing/skillgroups](https://developer.genesys.cloud/platform/preview-apis#post-api-v2-routing-skillgroups)
[PATCH /api/v2/routing/skillgroups/{skillGroupId}](https://developer.genesys.cloud/platform/preview-apis#patch-api-v2-routing-skillgroups--skillGroupId-)
[DELETE /api/v2/routing/skillgroups/{skillGroupId}](https://developer.genesys.cloud/platform/preview-apis#delete-api-v2-routing-skillgroups--skillGroupId-)

## Example Usage

```terraform
resource "genesyscloud_routing_skill_group" "skillgroup" {
  name        = "Series6"
  description = "Agents with exposure to Series 6 license"
  skill_conditions = jsonencode(
    [
      {
        "routingSkillConditions" : [
          {
            "routingSkill" : "Series 6",
            "comparator" : "GreaterThan",
            "proficiency" : 2,
            "childConditions" : [{
              "routingSkillConditions" : [],
              "languageSkillConditions" : [],
              "operation" : "And"
            }]
          }
        ],
        "languageSkillConditions" : [],
        "operation" : "And"
    }]
  )
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) The group name

### Optional

- `description` (String) Description of the skill group
- `division_id` (String) The division to which this entity belongs
- `skill_conditions` (String) JSON encoded array of rules that will be used to determine group membership.

### Read-Only

- `id` (String) The ID of this resource.

