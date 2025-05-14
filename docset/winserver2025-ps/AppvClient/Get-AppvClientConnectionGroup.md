---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/get-appvclientconnectiongroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppvClientConnectionGroup
---

# Get-AppvClientConnectionGroup

## SYNOPSIS
Returns an App-V connection group object.

## SYNTAX

### ByName (Default)
```
Get-AppvClientConnectionGroup [[-Name] <String>] [-All] [<CommonParameters>]
```

### ByGuid
```
Get-AppvClientConnectionGroup [-GroupId] <Guid> [[-VersionId] <Guid>] [-All] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvClientConnectionGroup** cmdlet returns a specific Microsoft Application Virtualization (App-V) connection group object.

## EXAMPLES

### Example 1: Get all versions of a group by name
```
PS C:\> Get-AppvClientConnectionGroup -Name "MyConnectionGroup"
```

This command gets all versions of the enabled connection groups named MyConnectionGroup.

### Example 2: Get a connection group by using its ID
```
PS C:\> Get-AppvClientConnectionGroup -GroupID 793afd37-bd68-4ea1-859a-669f6afd0aa8
```

This command gets the enabled connection group that has the group ID of 793afd37-bd68-4ea1-859a-669f6afd0aa8.

### Example 3: Get all connection groups
```
PS C:\> Get-AppvClientConnectionGroup -All
```

This command gets all of the connection groups on the computer.

## PARAMETERS

### -All
Indicates that the cmdlet returns all connection groups that have been added to the computer, not just those that are enabled to the current user.

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

### -GroupId
Specifies the GUID of specific connection group.

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

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a different lineage.
If you do not specify this parameter, the cmdlet operates on all versions of the package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvClientConnectionGroup

## NOTES
* The cmdlet returns an error if the name of the specified App-V connection group cannot be found on the target computer.

## RELATED LINKS

[Add-AppvClientConnectionGroup](./Add-AppvClientConnectionGroup.md)

[Disable-AppvClientConnectionGroup](./Disable-AppvClientConnectionGroup.md)

[Enable-AppvClientConnectionGroup](./Enable-AppvClientConnectionGroup.md)

[Mount-AppvClientConnectionGroup](./Mount-AppvClientConnectionGroup.md)

[Remove-AppvClientConnectionGroup](./Remove-AppvClientConnectionGroup.md)

[Repair-AppvClientConnectionGroup](./Repair-AppvClientConnectionGroup.md)

[Stop-AppvClientConnectionGroup](./Stop-AppvClientConnectionGroup.md)

