---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Write-MbamRecoveryInformation
---

# Write-MbamRecoveryInformation

## SYNOPSIS
Writes the recovery information of a BitLocker encrypted volume to the Microsoft BitLocker Administration and Monitoring (MBAM) server.

## SYNTAX

```
Write-MbamRecoveryInformation [-ComputerUser <String[]>] [-RecoveryPackage <Byte[]>]
 -RecoveryPassword <SecureString> -RecoveryPasswordID <Guid> -VolumeID <Guid> [-Time <DateTime>]
 -Computer <String> -RecoveryServiceEndPoint <Uri> [-RetryCount <Int32>] [-RetryIntervalSeconds <Int32>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Write-MbamRecoveryInformation** cmdlet writes the recovery information of a BitLocker encrypted volume to the Microsoft BitLocker Administration and Monitoring (MBAM) server.
The *RecoveryServiceEndPoint* parameter is required and identifies the MBAM server instance to which the recovery information will be written.
The *Computer* parameter is required and identifies the name and domain of the computer associated with the recovery information.
The *VolumeID* parameter is required and uniquely identifies the BitLocker encrypted volume associated with the recovery information.
The *RecoveryPassword* parameter is required and is the 48-digit value used for securing the recovery key package of the BitLocker encrypted volume.
The *RecoveryPasswordID* parameter is required and uniquely identifies the correct recovery password.
The timestamp of the recovery information is required and is supplied through the *Time* parameter.

## EXAMPLES

### Example 1: Write user recovery information on a specified computer to the MBAM server
```
PS C:\>Write-MbamRecoveryInformation -Computer Computer.Contoso.com -ComputerUser @("User1@Contoso.com") -Time 1/20/2015 -RecoveryPassword 311111-363319-126170-621720-547228-519706-367873-363880 -RecoveryPasswordID Af3d4a74-f650-4370-AAA2-cbfc7fe2abb8 -VolumeId Bf3d4a74-f650-4370-BBB2-cbfc7fe2abb8 -RecoveryPackage @(49, 48, 49, 48, 49, 48, 49, 48, 49, 48, 49, 48, 49) -RecoveryServiceEndPoint http://mbamserver.contoso.com:8080 -Force
```

This command writes the recovery information for the user named User1@Contoso.com on the computer named Computer.Contoso.com to the MBAM server listening at the recovery service end point address http://mbamserver.contoso.com:8080.

### Example 2: Write user recovery information on a specified computer to the MBAM server with verbose output
```
PS C:\>Write-MbamRecoveryInformation -Computer Machine.Contoso.com -ComputerUser @("User1@Contoso.com") -Time 1/20/2015 -RecoveryPassword 311111-363319-126170-621720-547228-519706-367873-363880 -RecoveryPasswordID Af3d4a74-f650-4370-AAA2-cbfc7fe2abb8  -VolumeId Bf3d4a74-f650-4370-BBB2-cbfc7fe2abb8 -RecoveryPackage @(49, 48, 49, 48, 49, 48, 49, 48, 49, 48, 49, 48, 49) -RecoveryServiceEndPoint http://mbamserver.contoso.com:8080 -Force -Verbose
VERBOSE: Performing the operation "Write-MbamRecoveryInformation" on target "MBAM Recovery Database".
VERBOSE: Recovery Information for Volume bf3d4a74-f650-4370-bbb2-cbfc7fe2abb8 on Computer Machine.Contoso.com sent
 successfully.
```

This command writes the recovery information specified by the cmdlet input parameters to the MBAM server listening at the recovery service end point address http://mbamserver.contoso.com:8080.

This command also displays a confirmation message.

### Example 3: Write user recovery information on a specified computer to the MBAM server with verbose output and attempt recovery if the cmdlet fails
```
PS C:\>Write-MbamRecoveryInformation -Computer Machine.Contoso.com -ComputerUser @("user@Contoso.com") -Time 1/20/2015 -RetryCount 2 -RetryIntervalSeconds 5 -RecoveryPassword 311111-363319-126170-621720-547228-519706-367873-363880  -RecoveryPasswordID Af3d4a74-f650-4370-AAA2-cbfc7fe2abb8 -VolumeId Bf3d4a74-f650-4370-BBB2-cbfc7fe2abb8 -RecoveryPackage @(49, 48, 49, 48, 49, 48, 49, 48, 49, 48, 49, 48, 49) -RecoveryServiceEndPoint http://mbamserver.contoso.com:8080 -Force -Verbose
VERBOSE: Performing the operation "Write-MbamRecoveryInformation" on target "MBAM Recovery Database".
VERBOSE: Recovery Information for Volume bf3d4a74-f650-4370-bbb2-cbfc7fe2abb8 on Computer Machine.Contoso.com sent
successfully.
```

This command writes the recovery information specified by the cmdlet input parameters to the MBAM server listening at the recovery service end point address http://mbamserver.contoso.com:8080.

This command also displays a confirmation message.

If the write attempt is unsuccessful, the cmdlet retries two more times after an interval of five seconds.

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
Specifies a string array of fully qualified domain user accounts that have permission to access this volume recovery information in user principal name (UPN) (\<login name\>@\<domain name\> format (for instance: @("User1@contoso.com", "User2@contoso.com"))

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

### -RecoveryPackage
Specifies a byte array representing the BitLocker encryption key secured by the corresponding recovery password.
The package is associated with the volume identified by the VolumeID.
The recovery package corresponds to the **ms-FVE-KeyPackage** value in Active Directory (AD).

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: rkp, package

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecoveryPassword
Specifies the 48-digit recovery password used for securing the recovery key package and unlocking BitLocker-protected drive in recovery mode.
The recovery password corresponds to the **ms-FVE-RecoveryPassword** value in AD, and has the standard 8 tuples of 6 digits format dddddd-dd ...
dd-dddddd.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: rp, password

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecoveryPasswordID
Specifies the unique identifier associated with a BitLocker recovery password, used for identifying the correct recovery password.
The identifier is in GUID format (for instance: {xxxxxxxx-xxxx ...
xxxx}) and corresponds to the **ms-FVE-RecoveryGuid**, and has the standard GUID format.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: rpid, passwordid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecoveryServiceEndPoint
Specifies the path to the MBAM Recovery Service endpoint on the network.
The URL for MBAM Recovery service endpoint is http(s)://\<servername\>:\<port\>/MBAMRecoveryAndHardwareService/CoreService.svc.
(for instance: https://mbamserver.contoso.com:8080/ MBAMRecoveryAndHardwareService/CoreService.svc)

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
Specifies the maximum number of times to retry to send Recovery Information.
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

### -VolumeID
Specifies the unique drive identifier of the BitLocker protected drive associated with the recovery information.
The identifier is in GUID format (for instance: {xxxxxxxx-xxxx ...
xxxx}) and corresponds to the **msFVE-VolumeGuid** value in AD.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: vid

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

[Write-MbamTPMInformation](write-mbamtpminformation.md)

[Microsoft BitLocker Administration and Monitoring](/microsoft-desktop-optimization-pack/mbam-v25/)
