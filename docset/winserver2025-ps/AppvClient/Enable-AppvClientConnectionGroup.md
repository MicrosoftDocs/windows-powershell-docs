---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/enable-appvclientconnectiongroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AppvClientConnectionGroup
---

# Enable-AppvClientConnectionGroup

## SYNOPSIS
Enables a running connection group on the computer running the App-V client.

## SYNTAX

### ByGuid (Default)
```
Enable-AppvClientConnectionGroup [-Global] [-UserSID <String>] [-GroupId] <Guid> [-VersionId] <Guid>
 [<CommonParameters>]
```

### ByName
```
Enable-AppvClientConnectionGroup [-Global] [-UserSID <String>] [-Name] <String> [<CommonParameters>]
```

### ByConnectionGroup
```
Enable-AppvClientConnectionGroup [-Global] [-UserSID <String>] [-ConnectionGroup] <AppvClientConnectionGroup>
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AppvClientConnectionGroup** cmdlet enables a connection group to the computer that runs the Microsoft Application Virtualization (App-V) client.

## EXAMPLES

### Example 1: Enable a connection group by using its name
```
PS C:\> Enable-AppvClientConnectionGroup -Name "MyGroup" -Global
```

This command enables the connection group named MyGroup to all users on the computer.

### Example 2: Enable a connection group by using its ID
```
PS C:\> Enable-AppvClientConnectionGroup -GroupID 35ec9e5f-ab21-463f-8fe6-b90d4b66d182
```

This command enables the connection group that has the group ID 35ec9e5f-ab21-463f-8fe6-b90d4b66d182.

### Example 3: Enable all connection groups by names that match a string
```
PS C:\> Get-AppvClientConnectionGroup -Name "MyGr*" | Enable-AppvClientConnectionGroup
```

This command finds all connection groups that have the string MyGr in the name, and then enables them.

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
Indicates that this cmdlet enables the connection group is disabled for all users that log into the target computer.
Otherwise, it enables the connection group only for the currently running user.

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
Specifies the ID associated with a connection group.

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
Specifies the name of the App-V connection group.

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

### -UserSID
Specifies the SID of the intended user, in the form of S-1-2-34-56789012-3456789012-345678901-2345.
This parameter requires elevated rights to run.

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

### -VersionId
Specifies a GUID that differentiates a connection group version from other versions.
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
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns the following error: The action could not be performed due to current App-V permissions. Please modify the permissions and try the operation again.
* If the enable operation fails, the cmdlet returns the following error: The enable operation could not be completed. An error code is returned.
* If any package in the specified group is running, the connection group will not be enabled until all packages in the new group are shutdown. The cmdlet will still return success as long as the file is valid.
* If the cmdlet cannot find the connection group, the cmdlet returns an error stating The specified connection group could not be found on the target system.

## RELATED LINKS

[Add-AppvClientConnectionGroup](./Add-AppvClientConnectionGroup.md)

[Disable-AppvClientConnectionGroup](./Disable-AppvClientConnectionGroup.md)

[Get-AppvClientConnectionGroup](./Get-AppvClientConnectionGroup.md)

[Mount-AppvClientConnectionGroup](./Mount-AppvClientConnectionGroup.md)

[Remove-AppvClientConnectionGroup](./Remove-AppvClientConnectionGroup.md)

[Repair-AppvClientConnectionGroup](./Repair-AppvClientConnectionGroup.md)

[Stop-AppvClientConnectionGroup](./Stop-AppvClientConnectionGroup.md)

