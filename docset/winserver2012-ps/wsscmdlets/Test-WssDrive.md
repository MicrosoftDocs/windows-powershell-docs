---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: DCE74A4E-AF23-4DED-B15D-0A3A31B15E03
manager: dansimp
---

# Test-WssDrive

## SYNOPSIS
Checks a drive for file system errors, and optionally repairs errors.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Test-WssDrive [-Drive] <Drive> [-Repair]
```

### UNNAMED_PARAMETER_SET_2
```
Test-WssDrive [-Drive] <Drive> [-Cancel]
```

## DESCRIPTION
The **Test-WssDrive** cmdlet checks a drive for file system errors.
You can use this cmdlet to attempt to repair file system errors.
You can also use this cmdlet to stop a current check for errors.
To obtain a **Drive** object to check, use the Get-WssDrive cmdlet.

## EXAMPLES

### Example 1: Check and repair a drive
```
PS C:\>$Drive = Get-WssDrive -ID b6b093a2-1860-4172-a4a5-07ce2aebfa13 PS C:\> Test-WssDrive -Drive $Drive -Repair
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Repair
Indicates that the cmdlet attempts to repair file system errors that it finds.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### CheckDiskRequest, CancelOperationRequest

## NOTES

## RELATED LINKS

[Get-WssDrive](./Get-WssDrive.md)

[Set-WssDrive](./Set-WssDrive.md)

