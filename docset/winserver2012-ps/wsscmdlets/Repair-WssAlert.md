---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/repair-wssalert?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Repair-WssAlert

## SYNOPSIS
Repairs an alert.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Repair-WssAlert [-FeatureName] <String> [-HealthDefinitionName] <String> [[-MachineName] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Repair-WssAlert [-Alert] <Alert>
```

## DESCRIPTION
The **Repair-WssAlert** cmdlet runs the repair task for an alert.
Specify an alert object or specify the feature and health definition file associated with the alert.

## EXAMPLES

### Example 1: Repair an alert
```
PS C:\> Repair-WssAlert -FeatureName "MicrosoftServicing" -HealthDefinitionName "MUOptIn"
```

This command runs the repair task for the alert associated with the feature named MicrosoftServicing and the health definition named MUOptIn.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAlert](./Get-WssAlert.md)

[Enable-WssAlert](./Enable-WssAlert.md)

[Disable-WssAlert](./Disable-WssAlert.md)

[Clear-WssAlert](./Clear-WssAlert.md)

[Enable-WssAlert](./Enable-WssAlert.md)

