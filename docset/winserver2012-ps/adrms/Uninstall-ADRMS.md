---
external help file: Microsoft.RightsManagementServices.Configuration.dll-Help.xml
Module Name: ADRMS
online version: https://docs.microsoft.com/powershell/module/adrms/uninstall-adrms?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Uninstall-ADRMS

## SYNOPSIS
Removes configuration for an existing deployment of AD RMS Server.

## SYNTAX

```
Uninstall-ADRMS [-ADFSOnly] [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-ADRMS cmdlet removes configuration for the Active Directory Rights Management Services (AD RMS) server role and, if appropriate, role services that were installed with AD RMS.
To remove configuration for Identity Federation Support only, specify the ADFSOnly parameter.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Uninstall-ADRMS -Force
```

Description

-----------

This command removes the rms_2 configuration on this computer.
For more information on using this cmdlet, see https://go.microsoft.com/fwlink/?LinkId=136806

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Uninstall-ADRMS -ADFSOnly -Force
```

Description

-----------

This command removes the Identity Federation Support configuration on this computer.
For more information on using this cmdlet, see https://go.microsoft.com/fwlink/?LinkId=136806

## PARAMETERS

### -ADFSOnly
Removes configuration support for Active Directory Federated Services (AD FS) from this computer, but does not otherwise change the AD RMS configuration.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies user credentials to use for the configuration process.
If this parameter is specified, you will be prompted to enter credentials.
This parameter operates in a similar manner to the RunAs command.

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

### -Force
Forces completion of the command by overriding restrictions that would prevent it from succeeding (so long as a the changes made do not compromise security).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SwitchParameter, PSCredential

## OUTPUTS

## NOTES
* To totally remove the rms_2 role from the system, the **Remove-WindowsFeature** cmdlet must be run after this cmdlet is used. The command to do so is the **Remove-WindowsFeature ADRMS -IncludeManagementTools** command.

## RELATED LINKS

[Install-ADRMS](./Install-ADRMS.md)

[Update-ADRMS](./Update-ADRMS.md)

