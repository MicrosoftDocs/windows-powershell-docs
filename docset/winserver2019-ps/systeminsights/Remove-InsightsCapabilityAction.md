---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
Module Name: systeminsights
Download Help Link: http://go.microsoft.com
Locale: en-US
title: Remove-InsightsCapabilityAction
ms.reviewer:
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file:
keywords: powershell, cmdlet
author: Kateyanne
manager: elizapo
ms.date: 06/18/2018
ms.topic: reference
ms.prod: w10
ms.technology: 
ms.assetid: 38D3C557-40AB-4E35-943F-5AC58EEB55A7
schema: 2.0.0
---

# Remove-InsightsCapabilityAction

## SYNOPSIS
Removes the action(s) associated with a capability.

## SYNTAX

### All actions
```
Remove-InsightsCapabilityAction [-Name] <String> [-AllActions] [[-ComputerName] <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Specific actions
```
Remove-InsightsCapabilityAction [-Name] <String> [-Type] <PredictionStatus> [[-ComputerName] <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-InsightsCapabilityAction** cmdlet removes the action(s) associated with a capability.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-InsightsCapabilityAction -Name "CPU capacity forecasting" -Type OK, Warning
```

This example removes the **OK** and **Warning** actions for the **CPU capacity forecasting** capability. 

### Example 2
```powershell
PS C:\> Remove-InsightsCapabilityAction -Name "CPU capacity forecasting" -AllActions
```

This example removes all actions for the **CPU capacity forecasting** capability. 

## PARAMETERS

### -AllActions
Removes all actions associated with a capability.

```yaml
Type: SwitchParameter
Parameter Sets: AllActions
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a fully qualified domain name (FQDN). If not specified, uses the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credential for accessing the computer specified by the -ComputerName parameter.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a capability using a capability name. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: N

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Type
Specifies the prediction status of the capability. If the capability outputs this status, the action associated with this status will be automatically invoked.

```yaml
Type: PredictionStatus
Parameter Sets: ByActionType
Aliases:
Accepted values: None, Ok, Warning, Error, Critical

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.SystemInsights.Management.PowerShell.Capability

You can use the pipeline operator to pass a capability object to the *Name* parameter.

## OUTPUTS

### None

## RELATED LINKS
[Get-InsightsCapability](get-insightscapability.md)

[Get-InsightsCapabilityAction](get-insightscapabilityaction.md)

[Set-InsightsCapabilityAction](set-insightscapabilityaction.md)
