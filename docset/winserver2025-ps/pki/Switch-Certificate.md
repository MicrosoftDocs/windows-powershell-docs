---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/switch-certificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Switch-Certificate
---

# Switch-Certificate

## SYNOPSIS
Marks one certificate as having been replaced by another certificate.

## SYNTAX

```
Switch-Certificate [-NotifyOnly] [-NewCert] <Certificate> [-OldCert] <Certificate> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Switch-Certificate` cmdlet marks one certificate as having been replaced by another
certificate. This cmdlet triggers a replace certificate notification and optionally sets the renewal
property on the certificate being replaced.

## EXAMPLES

### EXAMPLE 1

```powershell
$params = @{
    OldCert = 'Cert:\LocalMachine\My\E42DBC3B3F2771990A9B3E35D0C3C422779DACD7'
    NewCert = 'Cert:\LocalMachine\My\4A346B4385F139CA843912D358D765AB8DEE9FD4'
}
Switch-Certificate @params
```

This example sets the renewal property of the certificate with the thumbprint
E42DBC3B3F2771990A9B3E35D0C3C422779DACD7 as renewed by the certificate with the thumbprint
4A346B4385F139CA843912D358D765AB8DEE9FD4 and generates a replace certificate notification.

### EXAMPLE 2

```powershell
Set-Location -Path cert:\LocalMachine\My
$oldCert = Get-ChildItem -Path E42DBC3B3F2771990A9B3E35D0C3C422779DACD7
$newCert = Get-ChildItem -Path 4A346B4385F139CA843912D358D765AB8DEE9FD4
Switch-Certificate -OldCert $oldCert -NewCert $newCert -NotifyOnly
```

This example locates two certificates in the machine MY store and assigns them the variables
`$oldCert` and `$newCert`. This cmdlet then generates a replacement notification without changing a
renewal property of the old certificate.

## PARAMETERS

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewCert

Specifies an X509 certificate or a certificate path for the certificate that replaces the
certificate specified with the **OldCert** parameter.

```yaml
Type: Microsoft.CertificateServices.Commands.Certificate
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotifyOnly

Creates a replacement certificate notification without replacing the **NewCert** parameter with the
**OldCert** parameter. This mode is useful when testing a script that was registered with the
`New-CertificateNotificationTask` cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OldCert

Specifies an X509 certificate or a certificate path in the certificate provider for the certificate
to be replaced.

```yaml
Type: Microsoft.CertificateServices.Commands.Certificate
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.Certificate

The **Certificate** object can either be provided as a Path object to a certificate or an
**X509Certificate2** object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/?LinkId=290488)

[Set-Location](https://go.microsoft.com/fwlink/?LinkID=293912)

[Get-CertificateNotificationTask](./Get-CertificateNotificationTask.md)

[New-CertificateNotificationTask](./New-CertificateNotificationTask.md)

[Remove-CertificateNotificationTask](./Remove-CertificateNotificationTask.md)
