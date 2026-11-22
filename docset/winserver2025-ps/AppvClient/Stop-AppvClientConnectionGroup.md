---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/stop-appvclientconnectiongroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-AppvClientConnectionGroup
---

# Stop-AppvClientConnectionGroup

## SYNOPSIS
Shuts down the shared virtual environment of a connection group.

## SYNTAX

### ByGuid (Default)
```
Stop-AppvClientConnectionGroup [-Global] [-GroupId] <Guid> [-VersionId] <Guid> [<CommonParameters>]
```

### ByName
```
Stop-AppvClientConnectionGroup [-Global] [-Name] <String> [<CommonParameters>]
```

### ByConnectionGroup
```
Stop-AppvClientConnectionGroup [-Global] [-ConnectionGroup] <AppvClientConnectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AppvClientConnectionGroup** cmdlet shuts down the shared virtual environment of a connection group.
All running processes in the connection group virtual environment are shutdown.

## EXAMPLES

### Example 1: Stop a virtual environment for a named group
```
PS C:\> Stop-AppvClientConnectionGroup -Name "MyGroup"
```

This command stops the virtual environment of the enabled connection group that has the name MyGroup.

### Example 2: Stop a virtual environment for a group by using its ID
```
PS C:\> Stop-AppvClientConnectionGroup -GroupID 793afd37-bd68-4ea1-859a-669f6afd0aa8
```

This command stops the virtual environment of the enabled connection group that has the group ID 793afd37-bd68-4ea1-859a-669f6afd0aa8.

### Example 3: Stop virtual environment for groups with names that match a string
```
PS C:\> Get-AppvClientConnectionGroup -Name "MyGr*" | Stop-AppvClientConnectionGroup
```

This command gets all of the enabled connection groups that have the string MyGr in the name, and then stops each of their virtual environments.

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

### -Global
Indicates that the cmdlet shuts down virtual environments for the specified connection groups for all users on the computer.
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
Specifies the group ID of a specific connection group.

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
Specifies the name of the Microsoft Application Virtualization (App-V) connection group.

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
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns an error.
* If the enable operation fails, the cmdlet returns an error.
* If the cmdlet cannot find the connection group on the target computer, the cmdlet returns an error.

## RELATED LINKS

[Add-AppvClientConnectionGroup](./Add-AppvClientConnectionGroup.md)

[Disable-AppvClientConnectionGroup](./Disable-AppvClientConnectionGroup.md)

[Enable-AppvClientConnectionGroup](./Enable-AppvClientConnectionGroup.md)

[Get-AppvClientConnectionGroup](./Get-AppvClientConnectionGroup.md)

[Mount-AppvClientConnectionGroup](./Mount-AppvClientConnectionGroup.md)

[Remove-AppvClientConnectionGroup](./Remove-AppvClientConnectionGroup.md)

[Repair-AppvClientConnectionGroup](./Repair-AppvClientConnectionGroup.md)

