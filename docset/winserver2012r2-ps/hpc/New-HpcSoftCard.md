---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/new-hpcsoftcard?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HpcSoftCard
---

# New-HpcSoftCard

## SYNOPSIS
Generates an HPC soft card certificate.

## SYNTAX

```
New-HpcSoftCard [-Template <String>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-HpcSoftCard** cmdlet generates a public key pair, obtains a certificate from the certificate authority, and places the certificate in the local certificate store.

## EXAMPLES

### Example 1: Create a soft card
```
PS C:\>New-HpcSoftCard -Template "MyTemplateName"
```

This command creates an HPC soft card based on the specified template located on the head node.

## PARAMETERS

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that will generate the HPC soft card certificate.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Template
Specifies the name of the template that contains the certificate credentials.
If the template is not found, an error is returned.

```yaml
Type: String
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

## NOTES
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2). It is not available in previous versions.
* You must enable soft card authentication on the cluster which will allow for smart card users to run jobs. To set this up, you must work with your Certificate Authentication or public key infrastructure (PKI) administrator to select or create a certificate template that must be used when generating a soft card for the cluster. The certificate template must allow for the private key to be exported, and can also have an associated access control list that defines who can use the certificate template.

## RELATED LINKS

[Get-HpcJobCredential](./Get-HpcJobCredential.md)


[Set-HpcJobCredential](/powershell/module/hpcpack2016/set-hpcjobcredential?view=hpc16-ps)
