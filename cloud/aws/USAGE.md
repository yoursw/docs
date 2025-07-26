# AWS Cloud Usage

## Instance Creation

...

## Instance Templates

When creating new templates for instances - please keep in mind the following:

1. Snapshots cost money - when creating AMI's, be mindful that they are associated with underlying EBS snapshots.
    a. 

TODO:

* Test replacement of root volumes for (automated?) migration ARM <-> x86-64 architectures.
  * This [Option in AWS Console](./img/root-img-replacement.png) can be found under the `Storage` tab of the instance.

## Instance Volume Attachment

Process:

0. (If necessary) - create a new volume from snapshot
1. Attach volume to instance
1. Wait for it to [initialize](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-initialize-monitor.html)
  a. TODO: See if there is a way to handle this automatically (i.e. with IaC)
1. Depending on the guest OS, the device name could be remapped
  a. In the case of Debian, it remaps NVME devices to `xvd*` as per these docs
    i.  There may be docs that specify this
    ii. NOTE: this is notated in AWS EBS Volume usage docs; however, the current documentation implicitly assumes that the reader will make the distinction of OS device mappings.
1. Mount block device as-per [normal procedure as documented by Amazon](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-using-volumes.html)
