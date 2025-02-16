---
layout: "netapp_gcp"
page_title: "NetApp_GCP: netapp_gcp_kms_config"
sidebar_current: "docs-netapp-gcp-resource-kms-config"
description: |-
  Provides a NetApp_GCP kms configuration resource. This can be used to create a new kms config on the GCP-CVS.
---

# netapp_gcp\_kms

Provides a NetApp_GCP kms configuration resource. This can be used to create a new kms on the GCP-CVS.

## Example Usages

**Create NetApp_GCP kms config:**

```
resource "netapp-gcp_kms_config" "kms-example" {
    provider = netapp-gcp
	key_ring_location = "us-east4"
    key_ring_name = "test-kms"
    key_name = "test-kms-key-"
    network = "projects/{projectID}/global/networks/{network}"
}
```

## Argument Reference

The following arguments are supported:

* `key_name` - (Required, modifiable) Name of the key to be used for encryption, This key should be in the keyRing mentioned in keyRing field.
* `key_project_id` - (Optional,modifiable) Project ID of project where the key to be used for encryption is residing.
* `key_ring_location` - (Required) Location of the keyRing.
* `key_ring_name` - (Required, modifiable) Key ring containing the keys to be used for volume encryption.
* `network` - (Required) The path of the network, for example: "projects/123456789/global/networks/network-to-netapp".

  
## Attributes Reference

The following attributes are exported in addition to the arguments listed above:

* `id` - The unique identifier for the kms.