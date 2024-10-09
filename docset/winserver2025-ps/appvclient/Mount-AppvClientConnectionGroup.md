---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/mount-appvclientconnectiongroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Mount-AppvClientConnectionGroup
---

# Mount-AppvClientConnectionGroup

## SYNOPSIS
Streams the contents of packages to the local disk.

## SYNTAX

### ByGuid (Default)
```
Mount-AppvClientConnectionGroup [-GroupId] <Guid> [-VersionId] <Guid> [<CommonParameters>]
```

### ByName
```
Mount-AppvClientConnectionGroup [-Name] <String> [<CommonParameters>]
```

### ByConnectionGroup
```
Mount-AppvClientConnectionGroup [-ConnectionGroup] <AppvClientConnectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Mount-AppvClientConnectionGroup** cmdlet streams the contents of all packages in a connection group to the local disk.

## EXAMPLES

### Example 1: Download packages for a named group
```
PS C:\> Mount-AppvClientConnectionGroup -Name "MyGroup"
```

This command downloads all packages that are part of the enabled connection group named MyGroup.

### Example 2: Download packages for a group by using group ID
```
PS C:\> Mount-AppvClientConnectionGroup -GroupID 793afd37-bd68-4ea1-859a-669f6afd0aa8
```

This cmdlet downloads all the packages that are part of the enabled connection group that has the group ID 793afd37-bd68-4ea1-859a-669f6afd0aa8.

### Example 3: Download packages for groups that match a string
```
PS C:\> Get-AppvClientConnectionGroup -Name "MyGr*" | Mount-AppvClientConnectionGroup
```

This command gets all enabled connection groups that have the string MyGr in the name, and then downloads all of the packages in those connection groups.

## PARAMETERS

### -ConnectionGroup
Specifies the Microsoft Application Virtualization (App-V) Connection Group object.

```yaml
Type: AppvClientConnectionGroup
Parameter Sets: ByConnectionGroup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GroupId
Specifies the group ID of specific connection group.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the App-V Connection Group.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Specifies the GUID that differentiates a Connection Group version from other versions.
If you do not specify this parameter, the cmdlet operates on all versions of the connection group.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvClientConnectionGroup

## OUTPUTS

## NOTES
* If a previous load has been canceled, the cmdlet resumes that load when it is run again. The package will be added to the system before loading. Otherwise the cmdlet fails. If you do not specify any parameters, the cmdlet loads all packages on the system.
* The cmdlet is synchronous. It returns when the load option has completed. To make the cmdlet asynchronous, use the **Start-Job** cmdlet.
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns an error.

## RELATED LINKS

[Add-AppvClientConnectionGroup](./Add-AppvClientConnectionGroup.md)

[Disable-AppvClientConnectionGroup](./Disable-AppvClientConnectionGroup.md)

[Enable-AppvClientConnectionGroup](./Enable-AppvClientConnectionGroup.md)

[Get-AppvClientConnectionGroup](./Get-AppvClientConnectionGroup.md)

[Remove-AppvClientConnectionGroup](./Remove-AppvClientConnectionGroup.md)

[Repair-AppvClientConnectionGroup](./Repair-AppvClientConnectionGroup.md)

[Stop-AppvClientConnectionGroup](./Stop-AppvClientConnectionGroup.md)

