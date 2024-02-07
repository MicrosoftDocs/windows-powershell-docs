---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: http://go.microsoft.com
external help file: Microsoft.SystemInsights.Management.PowerShell.dll-help.xml
Locale: en-US
Module Name: SystemInsights
ms.date: 06/18/2018
online version: https://learn.microsoft.com/powershell/module/systeminsights/set-insightscapabilityaction?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-InsightsCapabilityAction
---

# Set-InsightsCapabilityAction

## SYNOPSIS
Sets a remediation action that is tied to a prediction result.

## SYNTAX

```
Set-InsightsCapabilityAction [-Name] <String> [-Type] <PredictionStatus> [-Action] <String>
 [-ActionCredential] <PSCredential> [[-ComputerName] <String>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-InsightsCapabilityAction** cmdlet sets a remediation action that is tied to a prediction result.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## EXAMPLES

### Example 1
```powershell
PS C:\> $Cred = Get-Credential
PS C:\> Set-InsightsCapabilityAction -Name "CPU capacity forecasting" -Type Critical -Action "C:\Users\Public\CriticalAction.ps1" -ActionCredential $Cred
```

This example sets a **Critical** action for the **CPU capacity forecasting** capability, using the credentials specified using the **Get-Credential** cmdlet.

### Example 2
```powershell
PS C:\> $Cred = Get-Credential
PS C:\> Set-InsightsCapabilityAction -Name "CPU capacity forecasting" -Type Warning -Action "C:\Users\Public\WarningAction.ps1" -ActionCredential $Cred
```

This example sets a **Warning** action for the **CPU capacity forecasting** capability, using the credentials specified using the **Get-Credential** cmdlet.

## PARAMETERS

### -Action
Specifies the path of a PowerShell script, as well as any arguments, to be run if the capability outputs the associated prediction status.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActionCredential
Specifies the credential used to run the action.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
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
Parameter Sets: (All)
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

[Remove-InsightsCapabilityAction](remove-insightscapabilityaction.md)
