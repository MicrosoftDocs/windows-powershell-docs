---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: adcsdeployment
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/adcsdeployment/install-adcswebenrollment?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-AdcsWebEnrollment
---

# Install-AdcsWebEnrollment

## SYNOPSIS
Installs Certification Authority Web Enrollment

## SYNTAX

```
Install-AdcsWebEnrollment [-CAConfig <String>] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Install-AdcsWebEnrollment cmdlet performs initial installation and configuration of the Certification Authority Web Enrollment role service.
To remove the Web Enrollment role service use the Uninstall-AdcsWebEnrollment cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:
Import-Module ServerManager
Add-WindowsFeature Adcs-Web-Enrollment

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-AdcsWebEnrollment -CAConfig <CAComputerName>\<CACommonName>
```

Description

-----------

This command installs the Web Enrollment role service to a CA specified by \<CAComputerName\>\\\<CACommonName\>.
Replace the computer name of the certification authority (CA) for \<CAComputerName\> and replace the CA common name for \<CACommonName\> when running the command.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Install-AdcsWebEnrollment -CAConfig <CAComputerName>\<CACommonName> -force
```

Description

-----------

This command installs the Web Enrollment role service to a CA specified by \<CAComputerName\>\\\<CACommonName\> without requiring user confirmation.
Replace the computer name of the certification authority (CA) for \<CAComputerName\> and replace the CA common name for \<CACommonName\> when running the command.

## PARAMETERS

### -CAConfig
CAConfig parameter string.
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
If the Web Enrollment service is configured to use Standalone certification authority (CA), then an account that is a member of the local Administrators on the CA is required.
If the Web Enrollment service is configured to use an Enterprise CA, then an account that is a member of Domain Admins is required.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.WebEnrollment.WebEnrollmentResult

## NOTES
* Ensure you run Windows PowerShell® as an administrator. You can use the -force switch to bypass the prompt for confirmation.
To see parameters, run the following command: install-AdcsWebEnrollment -?

## RELATED LINKS

[Uninstall-AdcsWebEnrollment](./Uninstall-AdcsWebEnrollment.md)

