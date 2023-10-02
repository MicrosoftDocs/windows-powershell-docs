---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/set-wssdrive?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssDrive
---

# Set-WssDrive

## SYNOPSIS
Changes drive name or whether to enable snapshots.

## SYNTAX

### ByNameParamSet (Default)
```
Set-WssDrive [-Force] [-Name] <String> [[-NewName] <String>] [[-SnapshotsEnabled] <Boolean>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByObjectParamSet
```
Set-WssDrive [-Force] [-Drive] <Drive> [[-NewName] <String>] [[-SnapshotsEnabled] <Boolean>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByIdParamSet
```
Set-WssDrive [-Force] [-ID] <Guid> [[-NewName] <String>] [[-SnapshotsEnabled] <Boolean>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssDrive** cmdlet changes the name of a drive or whether to enable snapshots for a drive.
You can specify a drive by using its name or its GUID, or you can use the Get-WssDrive cmdlet to obtain a **Drive** object.
To specify a new drive name, use the **NewName** parameter.
To specify whether to enable snapshots, use the **SnapShotsEnabled** parameter.

## EXAMPLES

### Example 1: Change the name of a drive
```
PS C:\>$Drive = Get-WssDrive -ID b6b093a2-1860-4172-a4a5-07ce2aebfa13
PS C:\> Set-WssDrive -Drive $Drive -NewName "Sarah Jones Volume"
```

This example renames a drive.
The first command uses the Get-WssDrive cmdlet to get a **Drive** object that has the specified GUID, and stores it in the **$Drive** variable.

The second command changes the name of the drive represented by the object stored in the **$Drive** variable to Sarah Jones Volume.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Drive
Specifies a **Drive** object.
To obtain a **Drive** object, use the Get-WssDrive cmdlet.

```yaml
Type: Drive
Parameter Sets: ByObjectParamSet
Aliases: 

Required: True
Position: 0
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
Parameter Sets: ByIdParamSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a drive.

```yaml
Type: String
Parameter Sets: ByNameParamSet
Aliases: 

Required: True
Position: 0
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
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.Storage.Drive

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Drive
This cmdlet generates an object that represents the modifies drive.

## NOTES

## RELATED LINKS

[Get-WssDrive](./Get-WssDrive.md)

[Test-WssDrive](./Test-WssDrive.md)

