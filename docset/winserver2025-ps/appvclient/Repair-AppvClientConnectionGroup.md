---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/repair-appvclientconnectiongroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-AppvClientConnectionGroup
---

# Repair-AppvClientConnectionGroup

## SYNOPSIS
Resets the user package settings for the connection group.

## SYNTAX

### ByGuid (Default)
```
Repair-AppvClientConnectionGroup [-Global] [-UserState] [-Extensions] [-GroupId] <Guid> [-VersionId] <Guid>
 [<CommonParameters>]
```

### ByName
```
Repair-AppvClientConnectionGroup [-Global] [-UserState] [-Extensions] [-Name] <String> [<CommonParameters>]
```

### ByConnectionGroup
```
Repair-AppvClientConnectionGroup [-Global] [-UserState] [-Extensions]
 [-ConnectionGroup] <AppvClientConnectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Repair-AppvClientConnectionGroup** cmdlet resets the user settings of the connection group.
Resetting the settings causes permanent loss of any user-specific application settings in the package.
The settings are reset to their original state when the connection group was originally added to the system.

## EXAMPLES

### Example 1: Repair a named connection group
```
PS C:\> Repair-AppvClientConnectionGroup -Name "MyGroup"
```

This command repairs the connection group named MyGroup.

### Example 2: Repair a connection group by using its ID
```
PS C:\> Repair-AppvClientConnectionGroup -GroupID 793afd37-bd68-4ea1-859a-669f6afd0aa8
```

This command repairs the connection group that has the group ID 793afd37-bd68-4ea1-859a-669f6afd0aa8.

### Example 3: Repair all connection groups that have names that match a string
```
PS C:\> Get-AppvClientConnectionGroup -Name "MyGr*" | Repair-AppvClientConnectionGroup
```

This command finds all of the connection groups that have the string MyGr in the name, and then repairs them.

## PARAMETERS

### -ConnectionGroup
Specifies an App-V Connection Group object.

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

### -Extensions
Indicates that the cmdlet repairs the extension points of a connection group only, and does not delete the user state of the connection group.

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

### -Global
Indicates that this cmdlet resets user settings for the specified packages for all users on the computer.
Usage of the *Global* parameter requires administrative credentials.

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
Specifies the name of the Microsoft Application Virtualization (App-V) Connection Group.

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

### -UserState
Indicates that the cmdlet deletes the user state of the connection group only, and does not perform a repair on the extension points.

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

### -VersionId
Specifies a GUID that differentiates a connection group version from other versions, whether older, newer, or of a different lineage.
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

## RELATED LINKS

[Add-AppvClientConnectionGroup](./Add-AppvClientConnectionGroup.md)

[Disable-AppvClientConnectionGroup](./Disable-AppvClientConnectionGroup.md)

[Enable-AppvClientConnectionGroup](./Enable-AppvClientConnectionGroup.md)

[Get-AppvClientConnectionGroup](./Get-AppvClientConnectionGroup.md)

[Mount-AppvClientConnectionGroup](./Mount-AppvClientConnectionGroup.md)

[Remove-AppvClientConnectionGroup](./Remove-AppvClientConnectionGroup.md)

[Stop-AppvClientConnectionGroup](./Stop-AppvClientConnectionGroup.md)

