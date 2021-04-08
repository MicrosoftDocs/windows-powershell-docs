---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/test-wssdrive?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WssDrive
---

# Test-WssDrive

## SYNOPSIS
Checks a drive for file system errors, and optionally repairs errors.

## SYNTAX

### OpParamSet (Default)
```
Test-WssDrive [-Drive] <Drive> [-Repair] [<CommonParameters>]
```

### CancelParamSet
```
Test-WssDrive [-Drive] <Drive> [-Cancel] [<CommonParameters>]
```

## DESCRIPTION
The **Test-WssDrive** cmdlet checks a drive for file system errors.
You can use this cmdlet to attempt to repair file system errors.
You can also use this cmdlet to stop a current check for errors.
To obtain a **Drive** object to check, use the Get-WssDrive cmdlet.

## EXAMPLES

### Example 1: Check and repair a drive
```
PS C:\>$Drive = Get-WssDrive -ID b6b093a2-1860-4172-a4a5-07ce2aebfa13
PS C:\> Test-WssDrive -Drive $Drive -Repair
```

This example runs a check on a drive, and attempts to repair any file system errors.
The first command uses the Get-WssDrive cmdlet to get a **Drive** object that has the specified GUID, and stores it in the **$Drive** variable.

The second command runs a check on the **Drive** object stored in the **$Drive** variable.
The command includes the **Repair** parameter, therefore the command attempts to repair any file system errors it finds.

## PARAMETERS

### -Cancel
Indicates that the cmdlet cancels an in-progress Test-WssDrive check.

```yaml
Type: SwitchParameter
Parameter Sets: CancelParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Drive
Specifies a **Drive** object.
To obtain a **Drive** object, use the Get-WssDrive cmdlet.

```yaml
Type: Drive
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Repair
Indicates that the cmdlet attempts to repair file system errors that it finds.

```yaml
Type: SwitchParameter
Parameter Sets: OpParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.Storage.Drive

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.CheckDiskRequest
This cmdlet generates a request to check or repair a disk.

## NOTES

## RELATED LINKS

[Get-WssDrive](./Get-WssDrive.md)

[Set-WssDrive](./Set-WssDrive.md)

