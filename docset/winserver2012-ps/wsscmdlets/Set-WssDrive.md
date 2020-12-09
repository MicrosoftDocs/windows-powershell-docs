---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: C64C5B46-86B8-4A6F-AC54-A9F3621B988E
manager: dansimp
---

# Set-WssDrive

## SYNOPSIS
Changes drive name or whether to enable snapshots.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-WssDrive [-Name] <String> [[-NewName] <String>] [[-SnapshotsEnabled] <Boolean>] [-Force] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-WssDrive [-Drive] <Drive> [[-NewName] <String>] [[-SnapshotsEnabled] <Boolean>] [-Force] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-WssDrive [-ID] <Guid> [[-NewName] <String>] [[-SnapshotsEnabled] <Boolean>] [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WssDrive** cmdlet changes the name of a drive or whether to enable snapshots for a drive.
You can specify a drive by using its name or its GUID, or you can use the Get-WssDrive cmdlet to obtain a **Drive** object.
To specify a new drive name, use the **NewName** parameter.
To specify whether to enable snapshots, use the **SnapShotsEnabled** parameter.

## EXAMPLES

### Example 1: Change the name of a drive
```
PS C:\>$Drive = Get-WssDrive -ID b6b093a2-1860-4172-a4a5-07ce2aebfa13 PS C:\> Set-WssDrive -Drive $Drive -NewName "Sarah Jones Volume"
```

This example renames a drive.
The first command uses the Get-WssDrive cmdlet to get a **Drive** object that has the specified GUID, and stores it in the **$Drive** variable.

The second command changes the name of the drive represented by the object stored in the **$Drive** variable to Sarah Jones Volume.

## PARAMETERS

### -Drive
Specifies a **Drive** object.
To obtain a **Drive** object, use the Get-WssDrive cmdlet.

```yaml
Type: Drive
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### -ID
Specifies the GUID of a drive.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a drive.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies a new name for the drive.

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

### -SnapshotsEnabled
Indicates whether to enable snapshots on the drive.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Drive

## NOTES

## RELATED LINKS

[Get-WssDrive](./Get-WssDrive.md)

[Test-WssDrive](./Test-WssDrive.md)

