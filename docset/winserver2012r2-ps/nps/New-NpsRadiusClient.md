---
author: Kateyanne
description: 
external help file: Microsoft.NPS.Commands.dll-Help.xml
manager: jasgro
Module Name: NPS
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/nps/new-npsradiusclient?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NpsRadiusClient
---

# New-NpsRadiusClient

## SYNOPSIS
Creates a RADIUS client.

## SYNTAX

```
New-NpsRadiusClient [-Name] <String> [-Address] <String> [-AuthAttributeRequired <Boolean>]
 [-NapCompatible <Boolean>] [-SharedSecret <String>] [-VendorName <String>] [-Disabled] [<CommonParameters>]
```

## DESCRIPTION
The **New-NpsRadiusClient** cmdlet creates a Remote Authentication Dial-In User Service (RADIUS) client.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

## EXAMPLES

### Example 1: Add a new RADIUS client
```
PS C:\>New-NpsRadiusClient -Address "10.0.0.200" -Name "WirelessAP" -NapCompatible $True -SharedSecret "9vq7822hFsJ8rm"
```

This command adds an NAP-compatible wireless access point as a RADIUS client to the NPS configuration.
This RADIUS client has the IP address 10.0.0.200, the name WirelessAP, an enabled state, and a shared secret of 9vq7822hFsJ8rm.

## PARAMETERS

### -Address
Specifies a fully qualified domain name (FQDN) or IP address of the RADIUS client.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthAttributeRequired
Indicates whether the server has enabled verification for Access-Request messages.
The default is disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disabled
Indicates that the RADIUS client is disabled.

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

### -Name
Specifies a string that contains the name of the RADIUS client.
This name must be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NapCompatible
Indicates whether the RADIUS client is compatible with Network Access Protection (NAP).
The default is **$False**, which means that the RADIUS client is not compatible with NAP.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VendorName
Specifies the RADIUS client vendor name.
The default is "RADIUS standard".

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### NpsRadiusClient

## NOTES

## RELATED LINKS

[Get-NpsRadiusClient](./Get-NpsRadiusClient.md)

[Remove-NpsRadiusClient](./Remove-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

