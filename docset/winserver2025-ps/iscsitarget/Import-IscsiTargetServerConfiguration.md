---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/import-iscsitargetserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IscsiTargetServerConfiguration
---

# Import-IscsiTargetServerConfiguration

## SYNOPSIS
Imports an iSCSI Target Server configuration.

## SYNTAX

```
Import-IscsiTargetServerConfiguration [-Filename] <String> [[-ComputerName] <String>] [[-Credential] <String>]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Import-IscsiTargetServerConfiguration** cmdlet imports a Microsoft iSCSI Target Server configuration.

The configuration information includes the following:

- If you exported the configuration from a clustered iSCSI Target Server instance, the resource group name.
- If the cmdlet imports the configuration into an iSCSI Target Server clustered instance, the name of the resource group into which to import the configuration.
This resource group name is the same as the iSCSI virtual disk attribute named **MigrationResourceGroup**.
- The following attributes for each iSCSI target that iSCSI Target Server hosts: **Enabled** (target state), **HostName**, **TargetIQN**, **Description**, **ResourceGroup**, **MigrationResourceGroup**, **EnforceIdleTimeoutDetection**, **FirstBurstLength**, **MaxBurstLength**, **MaxRecvDataSegmentLength**, **NumRecvBuffers**, **EnableCHAP**, **CHAPUserName**, **EnableReverseCHAP**, **ReverseCHAPUserName**, **InitiatorIDs**, and **LunMappings**.
- The following attributes for each iSCSI virtual disk that iSCSI Target Server recognizes: **DiskId**, **Type**, **Enabled**, **DevicePath**, **ParentPath**, **Description**, **SnapshotStorageSize**, **MigrationDevicePath**, **MigrationParentPath**, and **MigrationResourceGroup**.

**MigrationParentPath** and **ParentPath** always have a value of null.

Before you import a configuration, perform the following tasks:

- Move the files for all the virtual disks that are eligible for migration from the source server to the destination server.
If there are any file path changes, note the source to destination changes.
- In a cluster configuration, ensure that the destination path of the file copy is on a cluster disk and that the cluster disk has been assigned to the desired iSCSI Target Server resource group, which you created on the destination cluster.
Note the resource group that owns the path.
- If the file paths have changed between the source and the destination servers, open the exported configuration .xml file in a text editor, and identify the **MigrationDevicePath** tags to change to reflect the changes.
- In a cluster configuration, if the file path or the resource group name have changed between the source server and the destination server, open the exported configuration xml file in a text editor, and identify the **MigrationResourceGroup** tags to change to reflect the new resource group.

After you import a configuration, perform the following tasks:

- You must manually reconfigure the forward and reverse Challenge Handshake Authentication Protocol (CHAP) secret keys.
- Because importing does not include logical unit (LU) snapshot information, you must take necessary snapshots.
- Manually apply any iSNS settings that are relevant to the new configuration.
- Manually apply any iSCSI target portal settings that are relevant to the new configuration.

## EXAMPLES

### Example 1: Import configuration into the current computer or cluster
```
PS C:\> Import-IscsiTargetServerConfiguration -Filename "D:\ServerConfig78.xml"
```

This command imports the iSCSI Target Server configuration of a stand-alone iSCSI Target Server or clustered iSCSI Target Servers from a specified file.
The cmdlet imports into the current stand-alone computer or the current clustered node.

### Example 2: Import configuration into a specified computer or cluster
```
PS C:\> Import-IscsiTargetServerConfiguration -Filename "D:\ServerConfig78.xml" -ComputerName "TargetServer09.Contoso.com"
```

This command imports the iSCSI Target Server configuration of a stand-alone iSCSI Target Server or clustered iSCSI Target Servers from a specified file.
The command imports the servers into the specified remote stand-alone computer or remote clustered node.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

The cmdlet imports the iSCSI Target Server configuration to the computer or cluster that you specify.
If you do not specify this parameter, the cmdlet imports the configuration into the iSCSI Target Server that runs on the same computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials when connecting to a remote computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filename
Specifies a file name.
The cmdlet imports the configuration from the file that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet deletes an existing **iSCSITarget** or **iSCSIVirtualDisk** that has the same name or device path on the target node, and then imports the ones in the configuration file.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Export-IscsiTargetServerConfiguration](./Export-IscsiTargetServerConfiguration.md)

[Set-IscsiServerTarget](./Set-IscsiServerTarget.md)

