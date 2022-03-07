## ESXi Configuration/Fixes

### Fix multiple partitions on ESXi disk preventing Datastore creation

`Error message: HostDatastoreSystem.QueryVmfsDatastoreCreateOptions” for object “ha-datastoresystem” on ESXi failed`

#### Steps

- SSH into your host
- Navigate to /dev/disks directory
- List files (ls)
- Match the identifier with the datastore that you cant create in vSphere (Example: naa.6d4ae7608f873700762a910c5402c983)
- Type: partedUtil mklabel /dev/disks/naa.6d4ae7608f873700762a910c5402c983 msdos
- Exit SSH session

#### Example Identifier:

`t10.ATA_____WDC_WD20EFRX2D68EUZN0_________________________WD2DWCC4M0KNUN5D`
