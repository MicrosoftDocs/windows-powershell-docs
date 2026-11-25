---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: NPS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nps/set-npsradiusclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NpsRadiusClient
---

# Set-NpsRadiusClient

## SYNOPSIS
Specifies configuration settings for a RADIUS client.

## SYNTAX

```
Set-NpsRadiusClient [-Name] <String> [-Address <String>] [-AuthAttributeRequired <Boolean>]
 [-SharedSecret <String>] [-VendorName <String>] [-Enabled <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NpsRadiusClient** cmdlet specifies configuration settings for a Remote Authentication Dial-In User Service (RADIUS) client.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

For more information about RADIUS client options, see [Managing RADIUS Clients](https://technet.microsoft.com/library/cc754717.aspx) on TechNet.

## EXAMPLES

### Example 1: Set a RADIUS client settings
```
PS C:\>Set-NpsRadiusClient -Name "WirelessAP" -Address "10.0.0.201" -Enabled $False -SharedSecret "1234567890"
```

This command changes settings for the RADIUS client named WirelessAP.
It sets the IP address to 10.0.0.201 and the shared secret to 1234567890.

## PARAMETERS

### -Address
Specifies the fully qualified domain name (FQDN) or IP address of a RADIUS client.

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

### -AuthAttributeRequired
Indicates whether verification for Access-Request messages is enabled.
The default value for this parameter is $False, which indicates that verification is disabled.

Set this parameter to $True if your access server supports use of the Message Authenticator attribute, also known as the signature attribute, for additional security.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates whether the RADIUS client is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the RADIUS client to update.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SharedSecret
Specifies a shared secret key that is configured at the RADIUS client.
Windows Server® 2012 uses the shared secret key to validate messages between the RADIUS client and NPS.

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

### -VendorName
Specifies the vendor name for the RADIUS client.
The default name is RADIUS standard.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### NpsRadiusClient

## NOTES

## RELATED LINKS

[Get-NpsRadiusClient](./Get-NpsRadiusClient.md)

[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Remove-NpsRadiusClient](./Remove-NpsRadiusClient.md)

