# EBS

Amazon EBS (Elastic Block Store) is a scalable, high-performance block-storage service designed for Amazon EC2.

* It can be used to create storage volumes and attach them to EC2 instances. 
* All EBS volume types offer durable snapshot capabilities and are designed for 99.999% availability.

EBS' elastic volumes feature allows you to increase volume size while the volume is still in use, making the resizing process easier and faster. It also provides the option to completely change the volume type and adjust its performance - also without downtime.


# Show EBS Volume
In an Amazon-Linux system, you can read some information on the EBS volume with the following command:<br>
`sudo gdisk -l /dev/xvda`

![show-ebs-volume](./assets/EBS-screenshots/show-ebs-volume.png)

In Linux systems, you can use the following command to display disk usage on the file system:<br>
`df -h`

![show-storage-drives](./assets/EBS-screenshots/show-storage-drives.png)


# Create volume snapshot
It's recommended that you create a snapshot back-up before modifying the volume, in case you need to roll back changes.

From the EC2 left-hand pane:<br>
Snapshots  ->  Create snapshot

![create-snapshot](./assets/EBS-screenshots/create-snapshot.png)


Resource type:  `Volume`<br>
Volume ID:  `<id-of-EC2-volume>`<br>
Description:  `ex: Wazuh-Manager Snapshot`

Click `Create snapshot`.

![snapshot-created](./assets/EBS-screenshots/snapshot-created.png)

It will take some minutes for the volume to be created.<br> 
You can check progress in the `Snapshot status` column.


# Resize EBS volume with Elastic Volumes


## Modify volume
From the EC2 left-hand pane, click on `Volumes`.<br>
Check the box for the volume you'd like to modify.

![select-volume](./assets/EBS-screenshots/select-volume.png)

Select any changes you'd like to apply to the EBS volume.

![modify-volume](./assets/EBS-screenshots/modify-volume.png)

Click on `Modify`, then click on `Modify` again to confirm.

![confirm-modify](./assets/EBS-screenshots/confirm-modify.png)


## Extend file system
In order to finish increasing the size of the volume, you'll need to extend the file system after modifying the volume. The volume will first need to enter the optimizing state. In the EC2 volume's page, the `Volume state` should read `In-use` before proceeding.

Connect to your instance, and use the following command:<br>
`sudo lsblk`

![lsblk](./assets/EBS-screenshots/lsblk.png)

If you look in the output's `TYPE` column, you'll see the size of the full `disk`, and the size of the `part`ition. The partition has the old size before you modified the volume for more space. So now you'll extend the partition to allow access to the full disk space that you're paying AWS for!<br>
`sudo growpart /dev/xvda 1`

![growpart](./assets/EBS-screenshots/growpart.png)

Check that the partition was extended:<br>
`lsblk`

![lsblk-after-extending](./assets/EBS-screenshots/lsblk-after-extending.png)

View the file system data with this Linux command:<br>
`df -hT`

![df-hT](./assets/EBS-screenshots/df-hT.png)

The output should display the `Filesystem`, `Type`, `Size`, `Used`, `Avail`, `Use%`, `Mounted on`.<br>
The most relevant of these is the Filesystem, Type, and Mount point. In this example, the `xvda1` filesystem's Type is `xfs`, which allows me to use the `xfs_growfs` command on the `/` Mount point.

Use the `xfs_growfs` command to specify the mount point of your desired filesystem, aka `xvda1`:<br>
`sudo xfs_growfs -d /`

![xfs-growfs](./assets/EBS-screenshots/xfs-growfs.png)

For an `ext4` filesystem, use the `resize2fs` command instead. For example, if the filesystem is named `/dev/nvme0n1p1`, you can use this command:<br>
`sudo resize2fs /dev/nvme0n1p1`

Check that the size of the filesystem has been extended:<br>
`df -hT`

As you can see, the previous 8gb size is now 16gb.

![finished-extending](./assets/EBS-screenshots/finished-extending.png)

Congrats! You've just increased the amount of hard disk availability!