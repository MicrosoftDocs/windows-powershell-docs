---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 4EA71110-A579-4C1F-A91B-F24FB99B8BBD
manager: dansimp
---

# Start-DtcDiagnosticResourceManager

## SYNOPSIS
Starts a diagnostic Resource Manager.

## SYNTAX

```
Start-DtcDiagnosticResourceManager [[-Port] <Int32>] [[-Name] <String>]
```

## DESCRIPTION
The **Start-DtcDiagnosticResourceManager** cmdlet starts a diagnostic Resource Manager (RM) as a Windows PowerShell® background job.

## EXAMPLES

### Example 1: Start a diagnostic resource manager
```
PS C:\>Start-DtcDiagnosticResourceManager -Port 17124 -Name "testRM"
```

This example starts a DTC diagnostic resource manager.

## PARAMETERS

### -Name
Specifies the name for the diagnostic resource manager to start.
You can later refer to the RM by using this name.
If you do not specify a name, the RM instance ID, a GUID, is always assigned to the RM and you can refer to it by that ID.

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

### -Port
Specifies the listening port of the test RM.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Join-DtcDiagnosticResourceManager](./Join-DtcDiagnosticResourceManager.md)

[Stop-DtcDiagnosticResourceManager](./Stop-DtcDiagnosticResourceManager.md)

