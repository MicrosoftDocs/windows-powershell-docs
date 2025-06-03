---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/get-certificateenrollmentpolicyserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CertificateEnrollmentPolicyServer
---

# Get-CertificateEnrollmentPolicyServer

## SYNOPSIS
Returns all of the certificate enrollment policy server URL configurations.

## SYNTAX

```
Get-CertificateEnrollmentPolicyServer [-Url <Uri>] -Scope <EnrollmentPolicyServerScope>
 -Context <Context> [<CommonParameters>]
```

## DESCRIPTION

The `Get-CertificateEnrollmentPolicyServer` cmdlet retrieves information required for connecting to
one or more certificate enrollment policy servers configured for this user or computer. The returned
information can be filtered by providing a specific URL, a specific scope, or requesting only user
or computer (machine) context.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-CertificateEnrollmentPolicyServer -Scope All -Context User
```

This example returns all of the enrollment policy URL configurations that are included with the user
configuration, Group Policy, and local policy for the user context.

### EXAMPLE 2

```powershell
$params = @{
    Url = 'http://www.contoso.com/Policy/service.svc'
    Scope = 'All'
    Context = 'Machine'
}
Get-CertificateEnrollmentPolicyServer @params
```

This example returns all of the enrollment policy URL configurations that have the given URL for the
machine context.

### EXAMPLE 3

```powershell
Get-CertificateEnrollmentPolicyServer -Scope ConfiguredByYou -Context User
```

This example returns all of the enrollment policy server URL configurations that are configured for
the user context.

## PARAMETERS

### -Scope

Specifies where the cmdlet will find the enrollment policy server configuration.

```yaml
Type: Microsoft.CertificateServices.Commands.EnrollmentPolicyServerScope
Parameter Sets: (All)
Aliases:
Accepted values: Applied, ConfiguredByYou, All

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Url

Limits the returned enrollment policy servers to the servers that contain the provided URL.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Context

Retrieves information about the enrollment policy server for the local computer (machine) or current
user context.

```yaml
Type: Microsoft.CertificateServices.Commands.Context
Parameter Sets: (All)
Aliases:
Accepted values: Machine, User

Required: True
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

### None

## OUTPUTS

### Microsoft.CertificateServices.Commands.EnrollmentPolicyUrlDescription[]

Describes the enrollment policy obtained from the specified URL.

## NOTES

## RELATED LINKS

[Add-CertificateEnrollmentPolicyServer](./Add-CertificateEnrollmentPolicyServer.md)

[Remove-CertificateNotificationTask](./Remove-CertificateNotificationTask.md)
