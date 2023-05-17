---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsdeployment/install-adcswebenrollment?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-AdcsWebEnrollment
---

# Install-AdcsWebEnrollment

## SYNOPSIS
Installs the Certification Authority Web Enrollment.

## SYNTAX

```
Install-AdcsWebEnrollment [-CAConfig <String>] [-Force] 
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Install-AdcsWebEnrollment` cmdlet performs initial installation and configuration of the
Certification Authority (CA) Web Enrollment role service. To remove the Web Enrollment role service
use the `Uninstall-AdcsWebEnrollment` cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:

- `Import-Module ServerManager`
- `Add-WindowsFeature Adcs-Web-Enrollment`

## EXAMPLES

### Example 1: Install the Web Enrollment role service to a CA with confirmation

```powershell
Install-AdcsWebEnrollment -CAConfig "<CAComputerName>\<CACommonName>"
```

This command installs the Web Enrollment role service to a CA specified by
`<CAComputerName>\<CACommonName>`. Replace the computer name of the CA for `<CAComputerName>` and
replace the CA common name for `<CACommonName>` when running the command.

### Example 1: Install the Web Enrollment role service to a CA without confirmation

```powershell
Install-AdcsWebEnrollment -CAConfig "<CAComputerName>\<CACommonName>" -Force
```

This command installs the Web Enrollment role service to a CA specified by
`<CAComputerName>\<CACommonName>` without requiring user confirmation. Replace the computer name of
the CA for `<CAComputerName>` and replace the CA common name for `<CACommonName>` when running the
command.

## PARAMETERS

### -CAConfig

Specifies the CA config parameter string.
Do not specify this if there is a local CA installed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Specifies a **PSCredential** object for the CA Web Enrollment. To obtain a credential object, use the
`Get-Credential` cmdlet. For more information, type `Get-Help Get-Credential`. If the Web Enrollment
service is configured to use Standalone CA, then an account that is a member of the local
Administrators on the CA is required. If the Web Enrollment service is configured to use an
Enterprise CA, then an account that is a member of Domain Admins is required.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Common.WEP.WebEnrollmentResult

## NOTES

- Ensure you run Windows PowerShell as an administrator. You can use the **Force** parameter to
  bypass the prompt for confirmation. To see parameters, run the following command:

    `Install-AdcsWebEnrollment -?`

## RELATED LINKS

[Uninstall-AdcsWebEnrollment](./Uninstall-AdcsWebEnrollment.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)
