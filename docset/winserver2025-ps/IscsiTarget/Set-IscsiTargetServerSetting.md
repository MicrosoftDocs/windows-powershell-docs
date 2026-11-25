---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/set-iscsitargetserversetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IscsiTargetServerSetting
---

# Set-IscsiTargetServerSetting

## SYNOPSIS
Sets the global settings or common configurations for an iSCSI target virtual disk.

## SYNTAX

### IpScoped (Default)
```
Set-IscsiTargetServerSetting [-IP] <String> [-Port <Int32>] [-Enable <Boolean>] [-PassThru]
 [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ServerGlobal
```
Set-IscsiTargetServerSetting -DisableRemoteManagement <Boolean> [-PassThru] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IscsiTargetServerSetting** cmdlet sets the global settings or common configurations for an iSCSI target.

## EXAMPLES

### Example 1: Set target portal port number
```
PS C:\> Set-IscsiTargetServerSetting -IP 10.1.1.1 -Port 3200
```

This example sets the target portal with the IP address 10.1.1.1 to use port number 3200.
The default is port number 3260.

### Example 2: Disable target portal
```
PS C:\> Set-IscsiTargetServerSetting -IP 10.1.1.1 -Enable $False
```

This example disables the target portal with the IP address 10.1.1.1.

### Example 3: Enable target portal
```
PS C:\> Set-IscsiTargetServerSetting -IP 10.1.1.1 -Port 3200 -Enable $True
```

This example enables the target portal with the IP address 10.1.1.1 and changes the port number to 3200.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials when connecting to a remote computer.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableRemoteManagement
Indicates whether the computer that runs Microsoft iSCSI Target Server accepts any network-based management requests.
If you specify a value of $True, iSCSI Target Server does not accept requests issued by thread tokens that contain a SECURITY_NETWORK_RID.

You can specify this parameter only as a local user on the computer that runs iSCSI Target Server or on the cluster node that owns the iSCSI Target Server clustered role.

```yaml
Type: Boolean
Parameter Sets: ServerGlobal
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Specifies the portal state as set by the user.

```yaml
Type: Boolean
Parameter Sets: IpScoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies an IP address.

```yaml
Type: String
Parameter Sets: IpScoped
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Port
Specifies the port number to which the iSCSI target should listen.

```yaml
Type: Int32
Parameter Sets: IpScoped
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

### None.

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiTargetServerSetting

## NOTES

## RELATED LINKS

[Set-IscsiTargetServerSetting](./Set-IscsiTargetServerSetting.md)

