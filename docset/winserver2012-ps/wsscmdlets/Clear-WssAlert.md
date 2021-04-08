---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/clear-wssalert?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Clear-WssAlert

## SYNOPSIS
Deletes an alert.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Clear-WssAlert [-FeatureName] <String> [-HealthDefinitionName] <String> [[-MachineName] <String>] [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Clear-WssAlert [-Alert] <Alert> [-PassThru]
```

## DESCRIPTION
The **Clear-WssAlert** cmdlet deletes an alert from the server at the next network health evaluation cycle.
If you delete an alert and the server detects the problem again in the health evaluation cycle, it generates a new alert.
By default, the server refreshes alerts every thirty minutes.

## EXAMPLES

### Example 1: Delete an alert
```
PS C:\> Clear-WssAlert -FeatureName "MicrosoftServicing" -HealthDefinitionName "MUOptIn"
```

This command deletes the alert associated with the feature named MicrosoftServicing and the health definition named MUOptIn.

## PARAMETERS

### -Alert
Specifies a **WssAlert** object.
To obtain a **WssAlert** object, use the Get-WssAlert cmdlet.

```yaml
Type: Alert
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FeatureName
Specifies the name of the feature associated with the alert.

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

### -HealthDefinitionName
Specifies the name of the health definition associated with the alert.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Specifies the name of the computer on which the server generated the alert.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAlert](./Get-WssAlert.md)

[Enable-WssAlert](./Enable-WssAlert.md)

[Disable-WssAlert](./Disable-WssAlert.md)

[Repair-WssAlert](./Repair-WssAlert.md)

[Enable-WssAlert](./Enable-WssAlert.md)

