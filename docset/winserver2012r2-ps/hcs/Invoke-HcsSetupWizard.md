---
author: Kateyanne
description: 
external help file: Microsoft.HCS.Management.dll-Help.xml
manager: jasgro
Module Name: HCS
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hcs/invoke-hcssetupwizard?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-HcsSetupWizard
---

# Invoke-HcsSetupWizard

## SYNOPSIS
Performs initial configuration and device registration.

## SYNTAX

```
Invoke-HcsSetupWizard [-BypassValidations <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-HcsSetupWizard** cmdlet performs initial configuration and device registration with the azure_1 StorSimple Manager Service.
This wizard configures the following settings: 

- Data0 IP address 
- Primary DNS server 
- Primary NTP server 
- Web proxy (optional) 
- Password for accessing Windows PowerShell Interface for StorSimple 
- Password for StorSimple SnapShot Manager connections
- Device registration with the StorSimple Manager Service

To register a device with the StorSimple Manager Service, you need your service registration key and service data encryption key.
For the first device that you register, the StorSimple Manager Service generates a new service data encryption key for you.

## EXAMPLES

### Example 1: Invoke setup wizard
```
PS C:\> Invoke-HcsSetupWizard
Which IP address family would you like to configure on interface Data0? 
[4] IPv4 [6] IPv6 [B] Both (Default is "4"): 4

Data0 IPv4 address []:10.126.173.190
Data0 IPv4 subnet []:255.255.252.0
Data0 IPv4 gateway []:10.126.172.1
Network configuration may take a few minutes. Please wait... 

IPv4 primary DNS server []:172.16.0.1
DNS configuration may take a few minutes. Please wait... 

Primary NTP server [time.contoso.com]: 

Would you like to configure a web proxy? 
[Y] Yes [N] No (Default is "N"): n

The device administrator password must be between 8 and 15 characters. The 
password must contain a combination of uppercase letters, lowercase letters, numbers 
and special characters. 
Administrator Password: 
Confirm Administrator Password: 

StorSimple Snapshot Manager password must be between 14 and 15 characters. The 
password must contain a combination of uppercase letters, lowercase letters, 
numbers and special characters. 
StorSimple Snapshot Manager Password: 
Confirm StorSimple Snapshot Manager Password: 

The service registration key is available in the StorSimple Manager service. 
Enter service registration key:                                                 
Device registration is in progress. Please wait. 

Congratulations on registering your device with azure_1 StorSimple Manager 
service!  Your service data encryption key is cbJYxRFFXubypefZAIlDcw==
Please save a copy of this key as it will be required for additional devices 
that will register with this service. 

Have you saved a copy of this key? 
[Y] Yes [N] No (Default is "N"): y
```

This command invokes the setup wizard.
The wizard prompts you for input.

## PARAMETERS

### -BypassValidations
{{Fill BypassValidations Description}}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-HcsFirmwareCheck](./Start-HcsFirmwareCheck.md)

[Start-HcsHotfix](./Start-HcsHotfix.md)

[Get-HcsUpdateAvailability](./Get-HcsUpdateAvailability.md)

[Start-HcsUpdate](./Start-HcsUpdate.md)

