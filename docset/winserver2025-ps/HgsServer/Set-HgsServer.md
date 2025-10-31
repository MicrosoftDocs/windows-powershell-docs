---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsServer-help.xml
Module Name: HgsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsserver/set-hgsserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HgsServer
---

# Set-HgsServer

## SYNOPSIS
Sets the Host Guardian Service server configuration.

## SYNTAX

### httpAndHttpsThumbprint
```
Set-HgsServer [-Http] [-Https] [-HttpPort <UInt16>] [-HttpsPort <UInt16>]
 [-HttpsCertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### httpAndHttps
```
Set-HgsServer [-Http] [-Https] [-HttpPort <UInt16>] [-HttpsPort <UInt16>] [-HttpsCertificatePath <String>]
 [-HttpsCertificatePassword <SecureString>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### http
```
Set-HgsServer [-Http] [-HttpPort <UInt16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### httpsThumbprint
```
Set-HgsServer [-Https] [-HttpPort <UInt16>] [-HttpsPort <UInt16>] [-HttpsCertificateThumbprint <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### https
```
Set-HgsServer [-Https] [-HttpsPort <UInt16>] [-HttpsCertificatePath <String>]
 [-HttpsCertificatePassword <SecureString>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TrustActiveDirectory
```
Set-HgsServer [-TrustActiveDirectory] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TrustTpm
```
Set-HgsServer [-TrustTpm] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateMemoryLimit
```
Set-HgsServer [-UpdateMemoryLimit] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HgsServer** cmdlet sets the Host Guardian Service (HGS) server configuration.
The configuration properties changed include the communication protocol, the network ports, and the HTTPS certificate for the Attestation and Key Protection services.

## EXAMPLES

### Example 1: Configure the HGS server to be accessible over HTTP
```
PS C:\> Set-HgsServer -Http -HttpPort 81
```

This command configures the HGS server to be exposed over HTTP on port 81.

### Example 2: Configure the HGS server to be accessible over HTTP and HTTPS
```
PS C:\> Set-HgsServer -Http -Https -HttpsCertificatePath $PathToPfx -HttpsCertificatePassword $PfxSecureString
```

This command configures the HGS server to be exposed over both HTTP and HTTPS on the default ports.
HTTPS communication is secured with the certificate specified by $PathToPfx.

## PARAMETERS

### -Http
Indicates that the HGS Server is accessible over HTTP.

```yaml
Type: SwitchParameter
Parameter Sets: httpAndHttpsThumbprint, httpAndHttps, http
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpPort
Specifies the HTTP port.

```yaml
Type: UInt16
Parameter Sets: httpAndHttpsThumbprint, httpAndHttps, http, httpsThumbprint
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Https
Indicates that the HGS Server is accessible over HTTPS.

```yaml
Type: SwitchParameter
Parameter Sets: httpAndHttpsThumbprint, httpAndHttps, httpsThumbprint, https
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsCertificatePassword
Specifies the password to the certificate file specified in **HttpsCertificatePath**.

```yaml
Type: SecureString
Parameter Sets: httpAndHttps, https
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsCertificatePath
Specifies the path to the HTTPS certificate file (.pfx).

```yaml
Type: String
Parameter Sets: httpAndHttps, https
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsCertificateThumbprint
Indicates the thumbprint of the HTTPS certificate.

```yaml
Type: String
Parameter Sets: httpAndHttpsThumbprint, httpsThumbprint
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsPort
Specifies the HTTPS port of the HGS server.

```yaml
Type: UInt16
Parameter Sets: httpAndHttpsThumbprint, httpAndHttps, httpsThumbprint, https
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustActiveDirectory
Indicates that this cmdlet sets the Attestation service operation mode to Active Directory.

```yaml
Type: SwitchParameter
Parameter Sets: TrustActiveDirectory
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustTpm
Indicates that this cmdlet sets the Attestation service operation mode to trusted platform module (TPM).

```yaml
Type: SwitchParameter
Parameter Sets: TrustTpm
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateMemoryLimit
Indicates that the application pool memory limit for the attestation service should be updated to reflect the current amount of physical memory in the system.

```yaml
Type: SwitchParameter
Parameter Sets: UpdateMemoryLimit
Aliases:

Required: True
Position: Named
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[HGS Server Cmdlets](./hgsserver.md)

