---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Configuration.dll-Help.xml
Module Name: ADRMS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrms/uninstall-adrms?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-ADRMS
---

# Uninstall-ADRMS

## SYNOPSIS
Removes configuration for an existing deployment of AD RMS Server.

## SYNTAX

```
Uninstall-ADRMS [-ADFSOnly] [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-ADRMS** cmdlet removes configuration for the Active Directory Rights Management Services (AD RMS) server role and, if appropriate, role services that were installed with AD RMS.
To remove configuration for Identity Federation Support only, specify the *ADFSOnly* parameter.

## EXAMPLES

### Example 1: Remove the AD RMS configuration
```
PS C:\> Uninstall-ADRMS -Force
```

This command removes the AD RMS configuration on this computer.
For more information on using this cmdlet, see [Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806).

### Example 2: removes the Identity Federation Support configuration
```
PS C:\> Uninstall-ADRMS -ADFSOnly -Force
```

This command removes the Identity Federation Support configuration on this computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SwitchParameter, PSCredential

## OUTPUTS

## NOTES
* To totally remove the AD RMS role from the system, the **Remove-WindowsFeature** cmdlet must be run after this cmdlet is used. The command to do so is the `Remove-WindowsFeature ADRMS -IncludeManagementTools` command.

## RELATED LINKS

[Install-ADRMS](./Install-ADRMS.md)

[Update-ADRMS](./Update-ADRMS.md)

