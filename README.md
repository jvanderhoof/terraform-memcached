# Terraform Memcached Module

## Overview:
This Terraform module launches and configures a Memcached cluster.

---

#### Required Inputs:
  * cluster_name - name of cluster.  Should contain only lower case letters and '-'
  * security_group_ids - comma seperated list of security group ids which are allowed to * access this Memcached cluster
  * subnet_ids - comma seperated list of subnet ids available to this Memcached cluster
  * vpc_id - VPC id for this Memcached cluster

#### Optional Inputs:
  * node_type - type of node to use. defaults to cache.m1.small
  * port - port to run on.  defaults to 11211
  * count - number of nodes in the cluster.  defaults to 1

---

#### Module Outputs:
  * url - url for the Memcached cluster
  * port - port the Memcached cluster is configured on
  * security_group_id - security group assigned to the cluster


## Examples:

```bash
module "memcached" {
  source = "github.com/mondorobot/terraform-memcached"

  cluster_name = "memcached-cluster-name"
  security_group_ids = "security_group_id_with_memcached_access"
  subnet_ids = "subnet_id"
  vpc_id = "vpc_id"
}
```
