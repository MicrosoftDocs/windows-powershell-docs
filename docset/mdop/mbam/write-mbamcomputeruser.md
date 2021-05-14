---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Write-MbamComputerUser
---

# Write-MbamComputerUser

## SYNOPSIS
Writes a set of users to a computer's Trusted Platform Module (TPM) owner authorization and each of the currently known computer's encrypted volumes.

## SYNTAX

```
Write-MbamComputerUser -ComputerUser <String[]> -Computer <String> -RecoveryServiceEndPoint <Uri>
 [-RetryCount <Int32>] [-RetryIntervalSeconds <Int32>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Write-MbamComputerUser** cmdlet writes a set of users to a computer's Trusted Platform Module (TPM) owner authorization and each of the currently known computer's encrypted volumes.

## EXAMPLES

### Example 1: Give a user permission to recover TPM and Bitlocker information for a specified computer
```
PS C:\>Write-MbamComputerUser -RecoveryServiceEndPoint http://MBAMServer.contoso.com:8080 -Computer User12-PC.Contoso.com -user @("User12@Contoso.com")
```

This command gives User12@Contoso.com permission to recover TPM and Bitlocker information from self-service portal for computer User12-PC.Contoso.com and its volumes.

### Example 2: Give a user permission to recover TPM and Bitlocker information for a specified computer and suppress user confirmation
```
PS C:\>Write-MbamComputerUser -RecoveryServiceEndPoint http://MBAMServer.contoso.com:8080 -Computer User12-PC.Contoso.com -user @("User12@Contoso.com") -Force
```

This command gives User12@Contoso.com permission to recover TPM and Bitlocker information from self-service portal for computer User12-PC.Contoso.com and its volumes.

This command additionally suppresses user confirmation.

### Example 3: Give multiple users permission to recover TPM and Bitlocker information for a specified computer and attempt recovery if the cmdlet fails
```
PS C:\>Write-MbamComputerUser -svc http://MBAMServer.contoso.com:8080 -Computer User12-PC.Contoso.com -ComputerUser @("User12@Contoso.com", "User13@Contoso.net") -RetryCount 2 -RetryIntervalSeconds 10 -Force
```

This command gives  User12@Contoso.com and User13@Contoso.com permission to recover TPM and Bitlocker information from self-service portal for computer User12-PC.Contoso.com and its volumes.

The command also attempts recovery two more times with a ten second wait time between attempts.
This command additionally suppresses user confirmation.

### Example 4: Give a user permission to recover TPM and Bitlocker information for a specified computer and attempt recovery if the cmdlet fails
```
PS C:\>Write-MbamComputerUser -service http://MBAMServer.contoso.com:8080 -Computer User13-Desktop.Domain.Net -user @("User12@Contoso.com") -rc 2 -ri 10
```

This command gives User12@Contoso.com permission to recover TPM and Bitlocker information from self-service portal for the computer User13-Desktop.Domain.Net and its volumes.

This command attempts recovery two more times with a ten second wait time between attempts.

### Example 5: Give a user permission to recover TPM and Bitlocker information for a specified machine and attempt recovery if the cmdlet fails
```
PS C:\>Write-MbamComputerUser -service http://MBAMServer.contoso.com:8080 -Computer User13-Desktop.Domain.Net -user @("User12@Contoso.com") -rc 2 -ri 10 -Confirm
```

This command gives  User12@Contoso.com permission to recover TPM and Bitlocker information from the self-service portal for the machine User13-Desktop.Domain.Net and its volumes.

This command also attempts recovery two more times with a ten second wait time between attempts.

## PARAMETERS

### -Computer
Specifies the domain name and machine name of the domain-joined computer in \<domain name\>\\\<machine name\> format (For instance, "contoso.com\ user12-pc").

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
Specifies an array of fully qualified domain user accounts that have permission to access this volume recovery information in user principal name (UPN) (\<login name\>@\<domain name\> format (For instance, @("user12@contoso.com", " user13@contoso.com")).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: user

Required: True
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
Specifies the path to the Microsoft BitLocker Administration and Monitoring (MBAM) Recovery Service endpoint on the network.
The URL for the MBAM Recovery service endpoint is http(s)://\<servername\>:\<port\>/MBAMRecoveryAndHardwareService/CoreService.svc (for instance, https://mbamserver.contoso.com:8080/ MBAMRecoveryAndHardwareService/CoreService.svc).

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

[Write-MbamRecoveryInformation](write-mbamrecoveryinformation.md)

[Write-MbamTPMInformation](write-mbamtpminformation.md)

[Microsoft BitLocker Administration and Monitoring](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)


