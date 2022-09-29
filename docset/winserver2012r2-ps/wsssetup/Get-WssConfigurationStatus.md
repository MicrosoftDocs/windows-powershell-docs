---
external help file: Wssg.Setup.Commands.dll-Help.xml
Module Name: WSSSetup
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsssetup/get-wssconfigurationstatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssConfigurationStatus
---

# Get-WssConfigurationStatus

## SYNOPSIS
Gets the status of the configuration of Windows Server Essentials.

## SYNTAX

```
Get-WssConfigurationStatus [-ShowProgress] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssConfigurationStatus** cmdlet gets the status of the configuration of Windows Server Essentials.
Specify the **ShowProgress** parameter to view a progress indicator.

## EXAMPLES

### Example 1: Get configuration status
```
PS C:\> Get-WssConfigurationStatus
```

This command gets configuration status of Windows Server Essentials.

## PARAMETERS

### -ShowProgress
Indicates that the cmdlet displays a progress indicator.
If you do not specify this parameter, the cmdlet displays current status information.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Setup.ICCommon.StatusInfo
This cmdlet gets an object that represents the configuration status.

## NOTES

## RELATED LINKS

[Remove-WssConfigurationData](./Remove-WssConfigurationData.md)

[Start-WssConfigurationService](./Start-WssConfigurationService.md)

[Test-WssConfigurationOption](./Test-WssConfigurationOption.md)

[Test-WssPrecheckResult](./Test-WssPrecheckResult.md)

