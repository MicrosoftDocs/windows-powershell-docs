---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/new-rdvirtualdesktopcollection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-RDVirtualDesktopCollection
---

# New-RDVirtualDesktopCollection

## SYNOPSIS
Creates a virtual desktop collection.

## SYNTAX

### PooledMgd
```
New-RDVirtualDesktopCollection [-PooledManaged] [-CollectionName] <String> [-Description <String>]
 [-UserGroups <String[]>] [-ConnectionBroker <String>] -VirtualDesktopTemplateName <String>
 -VirtualDesktopTemplateHostServer <String> -VirtualDesktopAllocation <Hashtable>
 -StorageType <VirtualDesktopStorageType> [-CentralStoragePath <String>] [-LocalStoragePath <String>]
 [-VirtualDesktopTemplateStoragePath <String>] [-Domain <String>] [-OU <String>]
 [-CustomSysprepUnattendFilePath <String>] [-VirtualDesktopNamePrefix <String>]
 [-DisableVirtualDesktopRollback] [-VirtualDesktopPasswordAge <Int32>] [-UserProfileDiskPath <String>]
 [-MaxUserProfileDiskSizeGB <Int32>] [-Force] [<CommonParameters>]
```

### PersonalMgd
```
New-RDVirtualDesktopCollection [-PersonalManaged] [-CollectionName] <String> [-Description <String>]
 [-UserGroups <String[]>] [-ConnectionBroker <String>] -VirtualDesktopTemplateName <String>
 -VirtualDesktopTemplateHostServer <String> -VirtualDesktopAllocation <Hashtable>
 -StorageType <VirtualDesktopStorageType> [-CentralStoragePath <String>] [-LocalStoragePath <String>]
 [-Domain <String>] [-OU <String>] [-CustomSysprepUnattendFilePath <String>]
 [-VirtualDesktopNamePrefix <String>] [-AutoAssignPersonalVirtualDesktopToUser] [-GrantAdministrativePrivilege]
 [-Force] [<CommonParameters>]
```

### PooledUnmgd
```
New-RDVirtualDesktopCollection [-PooledUnmanaged] [-CollectionName] <String> [-Description <String>]
 [-UserGroups <String[]>] [-ConnectionBroker <String>] -VirtualDesktopName <String[]>
 [-UserProfileDiskPath <String>] [-MaxUserProfileDiskSizeGB <Int32>] [-Force] [<CommonParameters>]
```

### PersonalUnmgd
```
New-RDVirtualDesktopCollection [-PersonalUnmanaged] [-CollectionName] <String> [-Description <String>]
 [-UserGroups <String[]>] [-ConnectionBroker <String>] -VirtualDesktopName <String[]>
 [-AutoAssignPersonalVirtualDesktopToUser] [-GrantAdministrativePrivilege] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-RDVirtualDesktopCollection** cmdlet creates a virtual desktop collection.

## EXAMPLES

### Example 1: Create a managed pooled virtual desktop collection
```
PS C:\> New-RDVirtualDesktopCollection -CollectionName "Virtual Desktop Pool" -PooledManaged -VirtualDesktopTemplateName "RDS-Template" -VirtualDesktopTemplateHostServer "rdvh-1.contoso.com" -VirtualDesktopAllocation @{"RDS-WKS-A26.contoso.com"=1;" RDS-WKS-A27.contoso.com"=2} -StorageType LocalStorage -Description "PowerShell created Virtual Desktop Pool" -UserGroups "contoso\domain users" -ConnectionBroker "rdcb.contoso.com" -VirtualDesktopNamePrefix "RDS-WKS-A" -VirtualDesktopPasswordAge 31 -UserProfileDiskPath "\\RDS-WKS-A26.contoso.com\uvhd" -MaxUserProfileDiskSizeGB 10
```

This command creates a managed pooled virtual desktop collection and specifies configuration settings for the virtual desktop collection.
The command specifies the LocalStorage type for the collection, and specifies the virtual desktop template named RDS-Template for the collection.

## PARAMETERS

### -AutoAssignPersonalVirtualDesktopToUser
Indicates that the server automatically associates virtual desktops with user accounts when you create a new personal virtual desktop collection.

```yaml
Type: SwitchParameter
Parameter Sets: PersonalMgd, PersonalUnmgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CentralStoragePath
Specifies the path to a central storage location for virtual desktops in the collection.
Use the **StorageType** parameter to specify the type of storage (local or centralized) for the collection.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of a personal virtual desktop collection.

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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomSysprepUnattendFilePath
Provides the path to the .xml file that contains unattended installation settings for the remote desktop collection.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a descriptive name for the unattended installation file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableVirtualDesktopRollback
Indicates that the server prevents rollback of a virtual desktop deployment.

```yaml
Type: SwitchParameter
Parameter Sets: PooledMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies the fully qualified domain name (FQDN) of the Active Directory domain to which you add the virtual desktops.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -GrantAdministrativePrivilege
Indicates that the server grants administrative privileges to the user account that the server assigns to a given personal virtual desktop.
This parameter applies only to personal virtual desktop collections.

```yaml
Type: SwitchParameter
Parameter Sets: PersonalMgd, PersonalUnmgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalStoragePath
Specifies the path to a local storage location for virtual desktops.
Use the **StorageType** parameter to specify the type of storage for this collection.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxUserProfileDiskSizeGB
Specifies the maximum size (in gigabytes) for the user profile disk.

```yaml
Type: Int32
Parameter Sets: PooledMgd, PooledUnmgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OU
Specifies the name of the Active Directory Domain Services (AD DS) organizational unit (OU) for the virtual desktop collection.
OU names must be unique within a forest.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersonalManaged
Indicates that the server creates a new managed personal virtual desktop collection.
New virtual desktops that you add to this collection are based on the template that you specify in the **VirtualDesktopTemplateName** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: PersonalMgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersonalUnmanaged
Indicates that the server creates a new unmanaged personal virtual desktop collection.
New virtual desktops that you add to this collection are based on the template that you specify in the **VirtualDesktopTemplateName** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: PersonalUnmgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PooledManaged
Indicates that the server creates a new managed pooled virtual desktop collection.
New virtual desktops that you add to this collection are based on the template that you specify in the **VirtualDesktopTemplateName** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: PooledMgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PooledUnmanaged
Indicates that the server creates a new unmanaged pooled virtual desktop collection.
New virtual desktops that you add to this collection are based on the template that you specify in the **VirtualDesktopTemplateName** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: PooledUnmgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageType
Specifies the storage type for the collection.
The acceptable values for this parameter are:

- LocalStorage
- CentralSmbShareStorage
- CentralSanStorage

If you specify LocalStorage, specify a value for the **LocalStoragePath** parameter.
If you specify CentralSMBSharedStorage or CentralSanStorage, specify a value for the **CentralStorage** parameter.

```yaml
Type: VirtualDesktopStorageType
Parameter Sets: PooledMgd, PersonalMgd
Aliases:
Accepted values: LocalStorage, CentralSmbShareStorage, CentralSanStorage

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserGroups
Specifies an array of user groups that are authorized to connect to the collection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserProfileDiskPath
Specifies the path to the user profile disk for the collection.

```yaml
Type: String
Parameter Sets: PooledMgd, PooledUnmgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopAllocation
Specifies a collection of values (key/value pair) that allocate virtual desktops to Remote Desktop Virtualization (RD Virtualization Host) servers.

```yaml
Type: Hashtable
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of a virtual desktop to add to an unmanaged collection.

```yaml
Type: String[]
Parameter Sets: PooledUnmgd, PersonalUnmgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopNamePrefix
Specifies a prefix for virtual desktop names that Remote Desktop Services automatically creates in a managed virtual desktop collection.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopPasswordAge
Specifies the number of days after which the server enforces a password update.

```yaml
Type: Int32
Parameter Sets: PooledMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopTemplateHostServer
Specifies the fully qualified domain name (FQDN) of the server where the virtual desktop template associated with the collection is stored.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopTemplateName
Specifies a descriptive name for the virtual desktop template.

```yaml
Type: String
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopTemplateStoragePath
Specifies the path where the parent disk for virtual machines in the collection is stored.

```yaml
Type: String
Parameter Sets: PooledMgd
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

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)

[Update-RDVirtualDesktopCollection](./Update-RDVirtualDesktopCollection.md)

[Remove-RDVirtualDesktopCollection](./Remove-RDVirtualDesktopCollection.md)

