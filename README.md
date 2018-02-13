<img src="https://datera.io/cnt/uploads/2017/04/blue-285.png" alt="Drawing" width=200 height=50 />

<!--ts-->
   * [Datera Ecosystem Wiki](#datera-ecosystem-wiki)
      * [OpenStack](#openstack)
         * [Cinder Volume Driver](#cinder-volume-driver)
            * [Description](#description)
            * [Features Supported](#features-supported)
            * [Datera Specific Features](#datera-specific-features)
         * [Cinder Backup Driver](#cinder-backup-driver)
         * [Glance Image Backend Driver](#glance-image-backend-driver)
      * [Kubernetes](#kubernetes)
         * [CSI Driver](#csi-driver)
         * [Flex Volume Driver](#flex-volume-driver)
      * [Cloudstack](#cloudstack)
      * [Docker](#docker)
      * [DCOS](#dcos)
      * [VMWare](#vmware)
<!--te-->

# Datera Ecosystem Wiki

## OpenStack

### Cinder Volume Driver

[Location](http://www.github.com/Datera/cinder-driver)

#### Description
The Cinder Volume Driver (CVD) is used for provisioning persistent block
storage for a VM (or container) in an OpenStack cloud.  This differs from
“scratch” or “ephemeral” storage that a VM will be given automatically by Nova
during instantiation because the storage is persistent and will stick around
even when the original VM is destroyed (provided the Cinder volume was not also
destroyed, but this has to be done explicitly).  Many common volume-lifecycle
operations (listed below) are supported by the Datera CVD

#### Features Supported

    * Volume
        * Creation
        * Deletion
        * Extension
        * Clone
        * Initialize Connection
        * Attach
        * Detach
        * Manage
        * Unmanage
        * Manage-Get-Size
        * List-Manageable
        * Retype
    * Snapshot
        * Creation
        * Deletion
        * Clone
    * Image
        * Fast Clone

#### Datera Specific Features
These are all exposed to the client through Cinder config opts or Volume-Types

    * Tenancy (Config Opt)
    * No Tenant
    * Manual Tenant
    * Automatic Tenant (Disallows cloning between projects)
    * ACLs (automatic based on VM host, should never be turned off)
    * Storage-Placement (Volume Type)
        * hybrid
        * all-flash
        * single-flash
    * QoS (Volume Type)
        * read_iops_max
        * write_iops_max
        * total_iops_max
        * read_bw_max
        * write_bw_max
        * total_bw_max
    * Data path round-robin (Volume Type)
    * Replica Count (Volume Type)
    * IP Pools (Volume Type)
    * Datera Templates (Volume Type)
    * Multipath (configured outside the driver, but the driver supports it)
    * Request Profiling (Config Opt)


### Cinder Backup Driver

### Glance Image Backend Driver

## Kubernetes

### CSI Driver

### Flex Volume Driver

## Cloudstack

## Docker

## DCOS

## VMWare
