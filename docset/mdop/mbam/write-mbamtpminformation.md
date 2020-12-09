---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: D273859D-0FDA-4CC6-99C7-C89B7B6015F8
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Write-MbamTPMInformation
ms.reviewer:
---

# Write-MbamTPMInformation

## SYNOPSIS
Writes Trusted Platform Module (TPM) information to a Microsoft BitLocker Administration and Monitoring (MBAM) server.

## SYNTAX

```
Write-MbamTPMInformation [-ComputerUser <String[]>] -TpmOwnerInformation <SecureString> [-Time <DateTime>]
 -Computer <String> -RecoveryServiceEndPoint <Uri> [-RetryCount <Int32>] [-RetryIntervalSeconds <Int32>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Write-MbamTpmInformation** cmdlet writes Trusted Platform Module (TPM) owner information for a single computer to a Microsoft BitLocker Administration and Monitoring (MBAM) server.
The *RecoveryServiceEndPoint* parameter is required and identifies the MBAM server instance to which the TPM information is written.
The *Computer* parameter is required and identifies the name and domain of the computer associated with the TPM information.
The timestamp of the *TpmOwnerInformation* parameter is required and is supplied through the *Time* parameter.
A value with a newer timestamp will overwrite an older value in the database.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Computer
Specifies the domain name and computer name of the domain-joined computer in \<domain name\>\\\<machine name\> format (for instance "contoso.com\User1-pc").

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerUser
Specifies a string array of fully qualified domain user accounts that have permission to access this volume recovery information in user principal name (UPN) (\<login name\>@\<domain name\> format (for instance: @("User1@contoso.com", "User2@contoso.com")).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: user

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -RecoveryServiceEndPoint
Specifies the path to the MBAM Recovery Service endpoint on the network.
The URL for MBAM Recovery service endpoint is http(s)://\<servername\>:\<port\>/MBAMRecoveryAndHardwareService/CoreService.svc.
(for instance: https://mbamserver.contoso.com:8080/ MBAMRecoveryAndHardwareService/CoreService.svc).

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: svc, service

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetryCount
Specifies the maximum number of times to retry to send recovery information.
The cmdlet proceeds to the next record after the retry limit is exceeded.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: rc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetryIntervalSeconds
Specifies the amount of time in seconds to wait before the cmdlet retries to send the recovery information.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Time
Specifies the timestamp associated with the recovery information.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TpmOwnerInformation
Specifies the TPM Password hash value.
This value corresponds to the **msTPM-OwnerInformation** value or **msTPM-InformationObject** in Active Directory (AD).

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

## NOTES

## RELATED LINKS

[Write-MbamComputerUser](write-mbamcomputeruser.md)

[Write-MbamRecoveryInformation](write-mbamrecoveryinformation.md)

[Microsoft BitLocker Administration and Monitoring](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)


