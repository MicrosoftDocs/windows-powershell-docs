---
external help file: Wssg.Setup.Commands.dll-Help.xml
Module Name: WSSSetup
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsssetup/start-wssconfigurationservice?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-WssConfigurationService
---

# Start-WssConfigurationService

## SYNOPSIS
Starts initial configuration of Windows Server Essentials.

## SYNTAX

```
Start-WssConfigurationService [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WssConfigurationService** cmdlet starts initial configuration of Windows Server Essentials.

## EXAMPLES

### Example 1: Start initial configuration
```
PS C:\> $cred = Get-Credential -UserName LocalAdmin -Message "Please specify the password for your new administrator account."
PS C:\> Start-WssConfigurationService -CompanyName "Contoso.Inc" -NetBiosName "contosodomain" -NewAdminCredential $cred
```

This command starts initial configuration of Windows Server Essentials.

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

## OUTPUTS

### Microsoft.WindowsServerSolutions.Setup.ICCommon.StatusInfo
The cmdlet generates an object that represents the configuration status.

## NOTES

## RELATED LINKS

[Get-WssConfigurationStatus](./Get-WssConfigurationStatus.md)

[Remove-WssConfigurationData](./Remove-WssConfigurationData.md)

[Test-WssConfigurationOption](./Test-WssConfigurationOption.md)

[Test-WssPrecheckResult](./Test-WssPrecheckResult.md)

