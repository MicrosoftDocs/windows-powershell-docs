---
external help file: MSFT_WdsClient_v1.0.cdxml-help.xml
Module Name: WDS
online version: 
schema: 2.0.0
title: New-WdsClient
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 72818B2B-8F4D-4436-8985-A78D3D30E32B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-WdsClient

## SYNOPSIS
Creates a pre-staged client.

## SYNTAX

### UserAndJoinRights
```
New-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-BootImagePath <String>] [-OU <String>]
 [-Domain <String>] -DeviceID <String> -DeviceName <String> -User <String> -JoinRights <JoinRights>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BasicParams
```
New-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-BootImagePath <String>] [-OU <String>]
 [-Domain <String>] -DeviceID <String> -DeviceName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-WdsClient** cmdlet creates a pre-staged client, which is an account for a computer within Active Directory® Domain Services (AD DS).
Use pre-staged clients to provision computer accounts before a server that runs Windows Deployment Services installs a version of the Windows operating system on the computer.
To create a pre-staged client, specify the GUID, media access control (MAC) address, or Dynamic Host Configuration Protocol (DHCP) identifier associated with the computer, and a name for the computer.

You can also specify the following:

- A server that runs Windows Deployment Services.
The client contacts this server for the network boot program and boot image. 
- Whether the client prompts the user to boot in the Pre-Boot Execution Environment (PXE).
- A boot image for the client.
- A Windows Deployment Services answer file for the client. 
- Whether the client joins a domain, the user account that joins the computer to the domain, and the join rights to granted to that user.
- If Windows Deployment Services server is domain joined,  the domain and organizational unit (OU) in which to create the computer account.
If you do not specify this information, the cmdlet creates the account in the default computer container in the domain that the Windows Deployment Services server belongs to.

## EXAMPLES

### Example 1: Create a pre-staged client
```
PS C:\> New-WdsClient -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -DeviceName "TSQA031" -BootImagePath "boot\x86\images\Contosox86boot.wim" -JoinDomain $False -WdsClientUnattend "WindowsDSClientUnattend\Unattend.xml"
```

This command creates a pre-staged client named TSQA031 that has the specified ID.
The command specifies a boot image and an answer file.
The **JoinDomain** parameter has a value of $False, so this computer does not join a domain.

### Example 2: Create a pre-staged client that joins a domain
```
PS C:\>New-WdsClient -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -DeviceName "TSQA048" -JoinRights Full -User "TSQADOMAIN\PattiFuller" -Domain "TSQADomain.Contoso.com" -Group "NewComputers" -JoinDomain $True -OU "OU=Unit21,CN=TSQAMain,DC=Contoso,DC=com" -PxePromptPolicy OptIn -ReferralServer "WindowsDS01"
```

This command creates a pre-staged client named TSQA048 that has the specified ID.
The command specifies a referral server and an opt-in PXE prompt policy.
The computer belongs to the NewComputers group.

The **JoinDomain** parameter has a value of $True, so this computer joins the domain specified by the **Domain** parameter.
The command assigns the user TSQADOMAIN\PattiFuller full join rights for the domain and specifies an OU for the computer.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Specifies a path to the boot image.
This is the path to the boot image file for the computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -DeviceID
Specifies the ID of the computer.
This identifier is the GUID of a network interface card, a MAC address, or a DHCP unique identifier associated with the computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the computer associated with the pre-staged client.
This is a **sAMAccountName** value.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Domain
Specifies the domain in which to create the computer account name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Group
Specifies the group name of the client associated with the pre-staged client.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -JoinDomain
Indicates whether to join the computer to a domain as the account specified by the **User** parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: TRUE
Accept pipeline input: True (ByPropertyName, ByValue)
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
Parameter Sets: UserAndJoinRights
Aliases: 
Accepted values: JoinOnly, Full

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PxePromptPolicy
Specifies the prompt policy for this computer to boot in PXE.
The acceptable values for this parameter are:

- Adopt
- NoPrompt
- OptIn
- OptOut

```yaml
Type: PxePromptPolicy
Parameter Sets: (All)
Aliases: 
Accepted values: OptIn, NoPrompt, OptOut, Abort

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
If you specify a value of $True for the **JoinDomain** parameter, the cmdlet assigns the user the right to join the computer to the domain specified by the **Domain** parameter.
To join the client computer to the specified domain without granting any user rights, specify a value of $True for the **JoinDomain** parameter, but do not specify a user.

```yaml
Type: String
Parameter Sets: UserAndJoinRights
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WdsClientUnattend
Specifies an answer file as a relative path from the RemoteInstall share.
This file contains information for the Windows Deployment Services client user interface screens, such as entering credentials, choosing an install image, and configuring the disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsClient

## NOTES

## RELATED LINKS

[Approve-WdsClient](./Approve-WdsClient.md)

[Deny-WdsClient](./Deny-WdsClient.md)

[Get-WdsClient](./Get-WdsClient.md)

[Remove-WdsClient](./Remove-WdsClient.md)

[Set-WdsClient](./Set-WdsClient.md)

