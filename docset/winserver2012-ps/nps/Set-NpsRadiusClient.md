---
external help file: NPS_Cmdlets.xml
Module Name: NPS
online version: https://learn.microsoft.com/powershell/module/nps/set-npsradiusclient?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NpsRadiusClient

## SYNOPSIS
Specifies configuration settings for a RADIUS client.

## SYNTAX

```
Set-NpsRadiusClient [-Name] <String> [-Address <String>] [-AuthAttributeRequired <Boolean>]
 [-Enabled <Boolean>] [-NapCompatible <Boolean>] [-SharedSecret <String>] [-VendorName <String>]
```

## DESCRIPTION
The **Set-NpsRadiusClient** cmdlet specifies configuration settings for a Remote Authentication Dial-In User Service (RADIUS) client.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

For more information about RADIUS client options, see Managing RADIUS Clientshttp://technet.microsoft.com/library/cc754717(v=ws.10).aspx (http://technet.microsoft.com/library/cc754717(v=ws.10).aspx) on TechNet.

## EXAMPLES

### Example 1: Set a RADIUS client's settings
```
PS C:\>Set-NpsRadiusClient -Name "WirelessAP" -Address "10.0.0.201" -NapCompatible $False -SharedSecret "1234567890"
```

This command changes the following settings for the RADIUS client named WirelessAP: sets the IP address to 10.0.0.201, the client to not NAP-compatible, and the shared secret to 1234567890.

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
The default value for this parameter is **$False**, which indicates that verification is disabled.

Set this parameter to **$True** if your access server supports use of the Message Authenticator attribute, also known as the signature attribute, for additional security.

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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NapCompatible
Indicates whether the RADIUS client is compatible with Network Access Protection (NAP).

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
The default name is "RADIUS standard".

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

## INPUTS

## OUTPUTS

### NpsRadiusClient

## NOTES

## RELATED LINKS



