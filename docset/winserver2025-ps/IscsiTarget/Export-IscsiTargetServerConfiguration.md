---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/export-iscsitargetserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-IscsiTargetServerConfiguration
---

# Export-IscsiTargetServerConfiguration

## SYNOPSIS
Exports an iSCSI Target Server configuration.

## SYNTAX

```
Export-IscsiTargetServerConfiguration [-Filename] <String> [[-ComputerName] <String>] [[-Credential] <String>]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Export-IscsiTargetServerConfiguration** cmdlet exports a Microsoft iSCSI Target Server configuration.
Use this cmdlet to archive an iSCSI Target Server configuration, or to create a file to import by using the **Import-IscsiTargetServerConfiguration** cmdlet.

The configuration information includes the following:

- If the cmdlet exports the configuration from a clustered iSCSI Target Server instance, the resource group name.
- For an import of the configuration into an iSCSI Target Server clustered instance, the name of the resource group into which to import the configuration.
This resource group name is the same as the iSCSI virtual disk attribute named **MigrationResourceGroup**.
- The following attributes for each iSCSI target that iSCSI Target Server hosts: **Enabled** (target state), **HostName**, **TargetIQN**, **Description**, **ResourceGroup**, **MigrationResourceGroup**, **EnforceIdleTimeoutDetection**, **FirstBurstLength**, **MaxBurstLength**, **MaxRecvDataSegmentLength**, **NumRecvBuffers**, **EnableCHAP**, **CHAPUserName**, **EnableReverseCHAP**, **ReverseCHAPUserName**, **InitiatorIDs**, and **LunMappings**.
- The following attributes for each iSCSI virtual disk that iSCSI Target Server recognizes: **DiskId**, **Type**, **Enabled**, **DevicePath**, **ParentPath**, **Description**, **SnapshotStorageSize**, **MigrationDevicePath**, **MigrationParentPath**, and **MigrationResourceGroup**.

**MigrationParentPath** and **ParentPath** always have a value of null.

This cmdlet does not export Challenge Handshake Authentication Protocol (CHAP) secret keys, logical unit (LU) snapshot information, or transient state information such as current session information.

## EXAMPLES

### Example 1: Export configuration of a stand-alone server
```
PS C:\> Export-IscsiTargetServerConfiguration -Filename "D:\Server07Config.xml" -ComputerName "StandAloneIscsiServer07.Contoso.com" "
```

This command exports the iSCSI Target Server configuration of a stand-alone iSCSI Target Server to a specified file.

### Example 2: Export configuration of a clustered server
```
PS C:\> Export-IscsiTargetServerConfiguration -Filename "D:\Server07Config.xml" -ComputerName "ClusteredIscsiInstance07.Contoso.com" -Force
```

This command exports the iSCSI Target Server configuration of a clustered iSCSI Target Server to a specified file.
The command specifies the *Force* parameter.
Therefore, it overwrites an existing file without prompting you.

### Example 3: Export configuration of all clustered servers in a specified node
```
PS C:\> Export-IscsiTargetServerConfiguration -Filename "D:\Node22config.xml" -ComputerName "Node22-iSCSIServer.Contoso.com"
```

This command exports the iSCSI Target Server configuration of all clustered iSCSI Target Server instances hosted on the named cluster node to a specified file.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

The cmdlet exports the configuration for the iSCSI Target Server instance that runs on the computer or cluster that you specify.
If you do not specify a value for this parameter, the cmdlet uses the local computer.

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
The cmdlet exports the configuration to the file that you specify.
If a file already exists, the cmdlet overwrites the file after you confirm.
If you specify the *Force* parameter, the cmdlet overwrites the file without confirmation.

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
Indicates that the cmdlet overwrites an existing export file without confirmation.

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

[Import-IscsiTargetServerConfiguration](./Import-IscsiTargetServerConfiguration.md)

