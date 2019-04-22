---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: kenwith
ms.prod: w10
ms.sitesec: library
author: kenwith
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: F048BEC0-1C06-4D6C-91D9-2D987091B34F
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-AppvClientConnectionGroup
---

# Remove-AppvClientConnectionGroup

## SYNOPSIS
Delete an App-V connection group on the client.

## SYNTAX

### ByGuid (Default)
```
Remove-AppvClientConnectionGroup [-GroupId] <Guid> [-VersionId] <Guid> [<CommonParameters>]
```

### ByName
```
Remove-AppvClientConnectionGroup [-Name] <String> [<CommonParameters>]
```

### ByConnectionGroup
```
Remove-AppvClientConnectionGroup [-ConnectionGroup] <AppvClientConnectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AppvClientConnectionGroup** cmdlet deletes an existing Microsoft Application Virtualization (App-V) connection group on the client.
All packages that were in the group are separated.

## EXAMPLES

### Example 1: Remove a named connection group
```
PS C:\> Remove-AppvClientConnectionGroup -Name "MyGroup"
```

This command removes the connection group named MyGroup from the computer.

### Example 2: Remove a connection group by using its ID
```
PS C:\> Remove-AppvClientConnectionGroup -GroupID 35ec9e5f-ab21-463f-8fe6-b90d4b66d182
```

This command removes the connection group that has the group ID 35ec9e5f-ab21-463f-8fe6-b90d4b66d182.

### Example 3: Remove all connection groups that have names that match a string
```
PS C:\> Get-AppvClientConnectionGroup -Name MyGr* | Remove-AppvClientConnectionGroup
```

This command finds any connection group that has the string MyGr in the name, and then removes them from the computer.

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

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Specifies the GUID that differentiates a package version from other versions, whether older, newer, or of a completely different lineage.
If you do not specify this parameter, the cmdlet operates on all versions of the package.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvClientConnectionGroup

## OUTPUTS

## NOTES
* If any packages in the group are still running, the cmdlet returns an error.
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns an error.
* If the remove operation fails, the cmdlet returns the following error:  The remove operation could not be completed. An error code is returned.
* If any package within the specified group is running, the connection group is not removed until all packages in the new group are shutdown. The cmdlet still returns success as long as the file is valid.

## RELATED LINKS

[Add-AppvClientConnectionGroup](./Add-AppvClientConnectionGroup.md)

[Disable-AppvClientConnectionGroup](./Disable-AppvClientConnectionGroup.md)

[Enable-AppvClientConnectionGroup](./Enable-AppvClientConnectionGroup.md)

[Get-AppvClientConnectionGroup](./Get-AppvClientConnectionGroup.md)

[Mount-AppvClientConnectionGroup](./Mount-AppvClientConnectionGroup.md)

[Repair-AppvClientConnectionGroup](./Repair-AppvClientConnectionGroup.md)

[Stop-AppvClientConnectionGroup](./Stop-AppvClientConnectionGroup.md)


