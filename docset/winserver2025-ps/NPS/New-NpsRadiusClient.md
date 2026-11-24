---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: NPS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nps/new-npsradiusclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NpsRadiusClient
---

# New-NpsRadiusClient

## SYNOPSIS
Creates a RADIUS client.

## SYNTAX

```
New-NpsRadiusClient [-Name] <String> [-Address] <String> [-AuthAttributeRequired <Boolean>]
 [-SharedSecret <String>] [-VendorName <String>] [-Disabled] [<CommonParameters>]
```

## DESCRIPTION
The **New-NpsRadiusClient** cmdlet creates a Remote Authentication Dial-In User Service (RADIUS) client.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

> [!NOTE]
> The NPS Server service must be restarted after you run the **New-NpsRadiusClient** cmdlet.

## EXAMPLES

### Example 1: Add a new RADIUS client
```
PS C:\>New-NpsRadiusClient -Address "10.0.0.200" -Name "WirelessAP" -SharedSecret "9vq7822hFsJ8rm"
```

This command adds a wireless access point as a RADIUS client to the NPS configuration.
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
The default value is $False, which means disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disabled
Indicates whether the RADIUS client is disabled.

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
Specifies a name for the RADIUS client.
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
The default is RADIUS standard.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### NpsRadiusClient

## NOTES

## RELATED LINKS

[Get-NpsRadiusClient](./Get-NpsRadiusClient.md)

[Remove-NpsRadiusClient](./Remove-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

