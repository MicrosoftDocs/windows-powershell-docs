---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: B5229656-7327-4255-8B75-51DEF1648F26
manager: dansimp
---

# Disable-WssAlert

## SYNOPSIS
Disables and ignores an alert.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-WssAlert [-FeatureName] <String> [-HealthDefinitionName] <String> [[-MachineName] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-WssAlert [-Alert] <Alert>
```

## DESCRIPTION
The **Disable-WssAlert** cmdlet disables and ignores an alert.
When you disable and ignore an alert, the alert becomes inactive and the server does not include the alert in the overall health assessment of the computer in the network.
Use the Enable-WssAlert cmdlet to activate an alert.

## EXAMPLES

### Example 1: Disable an alert
```
PS C:\> Disable-WssAlert -FeatureName "MicrosoftServicing" -HealthDefinitionName "MUOptIn"
```

This command disables and ignores the alert associated with the feature named MicrosoftServicing and the health definition named MUOptIn.

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

[Clear-WssAlert](./Clear-WssAlert.md)

[Repair-WssAlert](./Repair-WssAlert.md)

[Enable-WssAlert](./Enable-WssAlert.md)

