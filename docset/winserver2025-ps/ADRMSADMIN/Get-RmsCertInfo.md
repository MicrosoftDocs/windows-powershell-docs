---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/get-rmscertinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RmsCertInfo
---

# Get-RmsCertInfo

## SYNOPSIS
Generates a report about a certificate used in a user request for the AD RMS cluster.

## SYNTAX

```
Get-RmsCertInfo -CertificateId <String> [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RmsCertInfo** cmdlet generates a report about a certificate used in a user request on the Active Directory Rights Management Services (AD RMS) cluster.

To obtain the report, specify the CertificateID of the certificate for which you want a report and then set the *Path* parameter to the AD RMS provider drive path `<PSDrive>:\`Report where `<PSDrive>` is the provider drive ID.
You can also specify a relative path.
For example, a dot (.) specifies the current location.

Use the **Get-RmsCertChain** cmdlet to obtain the *CertificateID* of the certificate for which you want a report.
The *CertificateID* value returned is valid only for the cluster identified by the *Path* parameter of **Get-RmsCertChain**.
You cannot use a *CertificateID* to identify the same certificate in different clusters.

## EXAMPLES

### Example 1: Get a certificate report
```
PS C:\> Get-RmsCertInfo -Path "." -CertificateId "sH+lchPGEP9IKIajmnw5QGUqOl4="
```

This command displays detailed information for a particular certificate.

### Example 2: Pass a certificate and get a report for it
```
PS C:\> $certs= Get-RmsCertChain -Path "." -RequestId 2 | Where {$_.CertificateType -eq 'DRM-CA-Certificate'}
PS C:\> $certs[0] | Get-RmsCertInfo -Path "."
```

This command stores filtered results of the **Get-RmsCertChain** cmdlet in a variable and then pipes the first certificate in the array to the **Get-RmsCertInfo** cmdlet to display details about that certificate.

## PARAMETERS

### -CertificateId
Specifies a unique internal certificate ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Get-RmsCertChain](./Get-RmsCertChain.md)

[Get-RmsChildCert](./Get-RmsChildCert.md)

[Get-RmsUserRequestReport](./Get-RmsUserRequestReport.md)

