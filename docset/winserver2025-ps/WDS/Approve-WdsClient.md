---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsClient_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/approve-wdsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Approve-WdsClient
---

# Approve-WdsClient

## SYNOPSIS
Approves clients.

## SYNTAX

### SingleMachineUserAndJoinRights
```
Approve-WdsClient [-BootImagePath <String>] [-BootProgram <String>] [-JoinDomain <Boolean>] [-OU <String>]
 [-ReferralServer <String>] [-WdsClientUnattend <String>] -JoinRights <JoinRights> -User <String>
 [-DeviceName <String>] -RequestId <UInt32> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### SingleMachine
```
Approve-WdsClient [-BootImagePath <String>] [-BootProgram <String>] [-JoinDomain <Boolean>] [-OU <String>]
 [-ReferralServer <String>] [-WdsClientUnattend <String>] [-DeviceName <String>] -RequestId <UInt32>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### MultipleMachineUserAndJoinRights
```
Approve-WdsClient [-BootImagePath <String>] [-BootProgram <String>] [-JoinDomain <Boolean>] [-OU <String>]
 [-ReferralServer <String>] [-WdsClientUnattend <String>] -JoinRights <JoinRights> -User <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### MultipleMachine
```
Approve-WdsClient [-BootImagePath <String>] [-BootProgram <String>] [-JoinDomain <Boolean>] [-OU <String>]
 [-ReferralServer <String>] [-WdsClientUnattend <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Approve-WdsClient** cmdlet approves clients that need administrative approval.
Unknown clients require approval before the server that runs Windows Deployment Services boots the client in the Pre-Boot Execution Environment (PXE).
You can specify a single device to approve by using a request ID.
The server that runs Windows Deployment Services allocates a request ID to a device.
If you do not specify a client to approve, the cmdlet approves all pending clients.

At the time that you approve an unknown client, you can also modify settings for the client.
Use the New-WdsClient and Set-WdsClient cmdlets to create and modify pre-staged clients.

## EXAMPLES

### Example 1: Approve all pre-staged clients and modify settings
```
PS C:\> Approve-WdsClient -BootImagePath "boot\x86\images\Contosox86boot.wim" -BootProgram "boot\x86\PxeBoot.com" -JoinDomain $True -OU "OU=Unit21,CN=TSQAMain,DC=Contoso,DC=com" -ReferralServer "WindowsDS01" -WdsClientUnattend "WindowsDSClientUnattend\Unattend.xml"
```

This command approves all pending pre-staged clients.
The command also specifies a boot image, boot program, and referral server.
The PXE boot process refers to the answer file specified by the *WdsClientUnattend* parameter.

The *JoinDomain* parameter has a value of $True, so these computers join a domain.
The command specifies an OU for the computers.

### Example 2: Approve all pre-staged clients and specify a user
```
PS C:\> Approve-WdsClient -JoinRights JoinOnly -User "TSQADOMAIN\PattiFuller" -BootImagePath "boot\x86\images\Contosox86boot.wim" -BootProgram "boot\x86\PxeBoot.com" -JoinDomain $True -OU "OU=Unit21,CN=TSQAMain,DC=Contoso,DC=com"
```

This command approves all pending pre-staged clients.
The command also specifies a boot image and boot program.

The *JoinDomain* parameter has a value of $True, so these computers join a domain.
The command specifies the user TSQADOMAIN\PattiFuller and specifies an OU for the computers.

### Example 3: Approve a pre-staged client
```
PS C:\> Approve-WdsClient -RequestId 7 -DeviceName "TSQA004"
```

This command approves a pre-staged client that has a request ID of seven, and assigns the device name TSQA004.

### Example 4: Approve a pre-staged client and modify settings
```
PS C:\> Approve-WdsClient -JoinRights Full -RequestId 22 -User "ITAdmin01@TSQADomain.Contoso.com" -BootImagePath "boot\x86\images\Contosox86boot.wim" -BootProgram "boot\x86\PxeBoot.com" -DeviceName "TSQA009" -JoinDomain $True -OU "OU=Unit21,CN=TSQAMain,DC=Contoso,DC=com"
```

This command approves a pre-staged client that has a request ID of 22 and assigns the device name TSQA009.
The command also specifies a boot image and boot program.

The *JoinDomain* parameter has a value of $True, so this computer joins a domain.
The command specifies the user ITAdmin01@TSQADomain.Contoso.com and specifies an OU for the computer.
The user has full join rights.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -BootImagePath
Specifies a path of the boot image.
This is a relative path from the RemoteInstall share to the boot image file for the computer.

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

### -BootProgram
Specifies the relative path from the RemoteInstall share to the network boot program for the computer.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the computer associated with the pre-staged client.
This is a **sAMAccountName** value.

```yaml
Type: String
Parameter Sets: SingleMachineUserAndJoinRights, SingleMachine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JoinDomain
Indicates whether to join the computer to a domain as the account specified by the *User* parameter.

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

### -JoinRights
Specifies the rights to assign to the account.
The acceptable values for this parameter are:

- Full.
Assigns full access rights, which includes the right to join the computer to the domain at any time.
- JoinOnly.
Requires the administrator to reset the computer account before the user can join the computer to the domain.

```yaml
Type: JoinRights
Parameter Sets: SingleMachineUserAndJoinRights, MultipleMachineUserAndJoinRights
Aliases:
Accepted values: JoinOnly, Full

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OU
Specifies the distinguished name of an OU.
The cmdlet creates the computer account object in this location.
If you do not specify this parameter, Windows Deployment Services creates the account in the default computer container in the domain of the server that runs Windows Deployment Services.

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

### -ReferralServer
Specifies the name of a server.
If you specify a referral server, the computer connects to this Windows Deployment Services server to download the network boot program and boot image by using Trivial File Transfer Protocol (TFTP).

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

### -RequestId
Specifies the request ID that the server that runs Windows Deployment Services allocates to a device in the Pending Device database.
If you do not specify this parameter, the cmdlet approves all clients in the Pending Device database.

```yaml
Type: UInt32
Parameter Sets: SingleMachineUserAndJoinRights, SingleMachine
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies a user, in the format DOMAIN\User or User@Domain.
If you specify a value of $True for the *JoinDomain* parameter, the cmdlet assigns the user the right to join the computer to the domain specified by the *Domain* parameter.
To join the client computer to the specified domain without granting any user rights, specify a value of $True for the *JoinDomain* parameter, but do not specify a user.

```yaml
Type: String
Parameter Sets: SingleMachineUserAndJoinRights, MultipleMachineUserAndJoinRights
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WdsClientUnattend
Specifies an answer file as a relative path from the RemoteInstall share.
This file contains information for the Windows Deployment Services client user interface screens, such as entering credentials, selecting an install image, and configuring the disk.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsClient

## NOTES

## RELATED LINKS

[Deny-WdsClient](./Deny-WdsClient.md)

[Get-WdsClient](./Get-WdsClient.md)

[New-WdsClient](./New-WdsClient.md)

[Remove-WdsClient](./Remove-WdsClient.md)

[Set-WdsClient](./Set-WdsClient.md)

