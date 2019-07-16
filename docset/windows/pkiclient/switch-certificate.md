---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Switch-Certificate
ms.reviewer:
ms.assetid: FEC58154-D4DF-4F65-9FF5-D26ADE2AA7B7
---

# Switch-Certificate

## SYNOPSIS
Marks one certificate as having been replaced by another certificate.

## SYNTAX

```
Switch-Certificate [-NotifyOnly] [-NewCert] <Certificate> [-OldCert] <Certificate> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Switch-Certificate** cmdlet marks one certificate as having been replaced by another certificate.
This cmdlet triggers a replace certificate notification and optionally sets the renewal property on the certificate being replaced.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Switch-Certificate -OldCert cert:\LocalMachine\My\E42DBC3B3F2771990A9B3E35D0C3C422779DACD7 -NewCert cert:\LocalMachine\My\4A346B4385F139CA843912D358D765AB8DEE9FD4
```

This example sets the renewal property of the certificate with the thumbprint E42DBC3B3F2771990A9B3E35D0C3C422779DACD7 as renewed by the certificate with the thumbprint 4A346B4385F139CA843912D358D765AB8DEE9FD4 and generates a replace certificate notification.

### EXAMPLE 2
```
PS C:\>Set-Location -Path cert:\LocalMachine\My



PS C:\>$oldCert = (Get-ChildItem -Path E42DBC3B3F2771990A9B3E35D0C3C422779DACD7)



PS C:\>$newCert = (Get-ChildItem -Path 4A346B4385F139CA843912D358D765AB8DEE9FD4)



PS C:\>Switch-Certificate -OldCert $oldCert -NewCert $newCert -NotifyOnly
```

This example locates two certificates in the machine MY store and assigns them the variables $oldCert and $newCert.
This cmdlet then generates a replacement notification without changing a renewal property of the old certificate.

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

### -NewCert
Specifies an X509 certificate or a certificate path for the certificate that replaces the certificate specified with the **OldCert** parameter.

```yaml
Type: Certificate
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotifyOnly
Creates a replacement certificate notification without replacing the **NewCert** parameter with the **OldCert** parameter. 
This mode is useful when testing a script that was registered with the New-CertificateNotificationTask cmdlet.

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

### -OldCert
Specifies an X509 certificate or a certificate path in the certificate provider for the certificate to be replaced.

```yaml
Type: Certificate
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.Certificate
The **Certificate** object can either be provided as a Path object to a certificate or an **X509Certificate2** object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-ChildItem](http://go.microsoft.com/fwlink/?LinkId=290488)

[Set-Location](http://go.microsoft.com/fwlink/?LinkID=293912)

[Get-CertificateNotificationTask](./Get-CertificateNotificationTask.md)

[New-CertificateNotificationTask](./New-CertificateNotificationTask.md)

[Remove-CertificateNotificationTask](./Remove-CertificateNotificationTask.md)

