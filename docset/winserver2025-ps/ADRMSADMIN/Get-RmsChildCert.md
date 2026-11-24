---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/get-rmschildcert?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RmsChildCert
---

# Get-RmsChildCert

## SYNOPSIS
Returns all child certificates from a parent certificate used in a user request for the AD RMS cluster.

## SYNTAX

```
Get-RmsChildCert [-StartTime <DateTime>] [-EndTime <DateTime>] -ParentCertId <String> -ParentCertType <String>
 [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RmsChildCert** cmdlet returns all issuance licenses from a parent client licensor certificate (CLC) or all end-user licenses (EULs) from a parent issuance license used in a user request on the Active Directory Rights Management Services (AD RMS) cluster.

To obtain licenses, specify the *ParentCertID* and *ParentCertType* of the parent certificate for which you want to retrieve child certificates and then set the *Path* parameter to the AD RMS provider drive path `<PSDrive>:\`Report where `<PSDrive>` is the provider drive ID.
You can also specify a relative path.
For example, a dot (.) specifies the current location.

Use the **Get-RmsCertChain** cmdlet to obtain the *ParentCertID* and the *ParentCertType* of the certificate for which you to retrieve child certificates.
The *ParentCertID* value returned is valid only for the cluster identified by the *Path* parameter of **Get-RmsCertChain**.
You cannot use a *ParentCertID* to identify the same certificate in different clusters.

## EXAMPLES

### Example 1: Get all child certificates for a parent
```
PS C:\> Get-RmsChildCert -Path "." -ParentCertId "8AGI9GoWuobJDsTmr/CUHTCEpsI=" -ParentCertType CLC
```

This command returns all child certificates from a parent client licensor certificate.

### Example 2: Pass a certificate ID and get all child certificates
```
PS C:\> $parentCert = Get-RmsCertChain -Path "." -RequestID 3 | Where {$_.CertificateType -eq 'Client-Licensor-Certificate'}
PS C:\> Get-RmsChildCert -Path "." -ParentCertId $parentCert.CertificateID -ParentCertType $parentCert.CertificateType
```

This command stores a certificate obtained from the **Get-RmsCertChain** cmdlet in a variable and then uses that variable to pass the certificate ID and type to the **Get-RmsChildCert** cmdlet to return child certificates.

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

### -EndTime
Specifies the end of a time period for a system health report.
This parameter specifies a time value.
See the description of the StartTime parameter for information on specifying a time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ParentCertId
Specifies the parent certificate for which child certificates are to be returned.

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

### -ParentCertType
Specifies the type of parent certificate for which child certificates are to be returned.
Possible values for this parameter are Client-Licensor-Certificate (or CLC) or Issuance-License (or IL).

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: CLC, Client-Licensor-Certificate, IL, Issuance-License

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
This parameter is required.
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

### -StartTime
Specifies the beginning of a time period.
This parameter specifies a time value.

The following examples show commonly-used syntax to specify a time.
Time is assumed to be local time unless otherwise specified.
When a time value is not specified, the time is assumed to 12:00:00 AM local time.
When a date is not specified, the date is assumed to be the current date.

`4/17/2006`

`Monday, April 17, 2006`

`2:22:45 PM`

`Monday, April 17, 2006 2:22:45 PM`

These examples specify the same date and the time without the seconds.

`4/17/2006 2:22 PM`

`Monday, April 17, 2006 2:22 PM`

`2:22 PM`

The following example shows how to specify a date and time by using the RFC1123 standard.
This example defines time by using Greenwich Mean Time (GMT).

`Mon, 17 Apr 2006 21:22:48 GMT`

The following example shows how to specify a round-trip value as Coordinated Universal Time (UTC).
This example represents Monday, April 17, 2006 at 2:22:48 PM UTC.

`2000-04-17T14:22:48.0000000`

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

[Get-RmsCertInfo](./Get-RmsCertInfo.md)

[Get-RmsUserRequestReport](./Get-RmsUserRequestReport.md)

