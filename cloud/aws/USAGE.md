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
