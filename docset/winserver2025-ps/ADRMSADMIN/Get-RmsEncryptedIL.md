---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/get-rmsencryptedil?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RmsEncryptedIL
---

# Get-RmsEncryptedIL

## SYNOPSIS
Returns use-license information from an issuance license used in a user request for the Active Directory Rights Management Services (AD RMS) cluster.

## SYNTAX

```
Get-RmsEncryptedIL -ILCertificateId <String> [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RmsEncryptedIL** cmdlet generates a report containing information about an issuance license used in a user request on the Active Directory Rights Management Services (AD RMS) cluster.
You must be logged in as an Enterprise Administrator to use this cmdlet.

To obtain licenses, specify the ILCertificateID of the certificate for which you want to obtain use-license information and then set the *Path* parameter to the AD RMS provider drive path `<PSDrive>:\`Report where `<PSDrive>` is the provider drive ID.
You can also specify a relative path.
For example, a dot (.) specifies the current location.

Use the **Get-RmsCertChain** cmdlet to obtain the *ILCertificateID* of the certificate for which you want to obtain use-license information.
The *ILCertificateID* value returned is valid only for the cluster identified by the *Path* parameter of **Get-RmsCertChain**.
You cannot use an *ILCertificateID* to identify the same certificate in different clusters.

## EXAMPLES

### Example 1: Get use-license information
```
PS C:\> Get-RmsEncryptedIL -Path "." -ILCertificateId "YJ3HGsG/ADg3rLm5LwWGgpAJmz4=" | Out-File -FilePath "C:\temp\RightsPolicyData.xml"
```

This command returns use-license information from an issuance license and saves the results in a file.

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

### -ILCertificateId
Specifies the issuance license certificate hash ID.

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

[Get-RmsCertInfo](./Get-RmsCertInfo.md)

[Get-RmsChildCert](./Get-RmsChildCert.md)

[Get-RmsRequestInfo](./Get-RmsRequestInfo.md)

[Get-RmsUserRequestReport](./Get-RmsUserRequestReport.md)

