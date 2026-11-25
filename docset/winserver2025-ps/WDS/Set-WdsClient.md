---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsClient_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/set-wdsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WdsClient
---

# Set-WdsClient

## SYNOPSIS
Modifies a pre-staged client device.

## SYNTAX

### UserAndJoinRightsSearchForest
```
Set-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-ResetAccount] [-DeviceID <String>]
 [-BootImagePath <String>] -DeviceName <String> [-SearchForest] -User <String> -JoinRights <JoinRights>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### UserAndJoinRightsDomain
```
Set-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-ResetAccount] [-DeviceID <String>]
 [-BootImagePath <String>] -DeviceName <String> [-DomainName <String>] [-Domain] -User <String>
 -JoinRights <JoinRights> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### UserAndJoinRights
```
Set-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-ResetAccount] [-DeviceID <String>]
 [-BootImagePath <String>] -DeviceName <String> -User <String> -JoinRights <JoinRights>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### SearchForest
```
Set-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-ResetAccount] [-DeviceID <String>]
 [-BootImagePath <String>] -DeviceName <String> [-SearchForest] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Domain
```
Set-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-ResetAccount] [-DeviceID <String>]
 [-BootImagePath <String>] -DeviceName <String> [-DomainName <String>] [-Domain] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### DeviceName
```
Set-WdsClient [-Group <String>] [-ReferralServer <String>] [-PxePromptPolicy <PxePromptPolicy>]
 [-WdsClientUnattend <String>] [-JoinDomain <Boolean>] [-ResetAccount] [-DeviceID <String>]
 [-BootImagePath <String>] -DeviceName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WdsClient** cmdlet modifies a pre-staged client device.
Specify the client to modify by using its name.
You can specify a client within AD DS domain of the server that runs Windows Deployment Services, in a specified domain, or anywhere in the current AD DS forest.

You can modify the following:

- The device ID, which is a GUID, media access control (MAC) address, or Dynamic Host Configuration Protocol (DHCP) identifier associated with the computer.
- A server that runs Windows Deployment Services.
The client contacts this server for the network boot program and boot image.
- Whether the client prompts the user to boot in the Pre-Boot Execution Environment (PXE).
- A boot image for the client.
- A Windows Deployment Services answer file for the client.
- Whether the client joins a domain, the user account that joins the computer to the domain, and the join rights to granted to that user.

You can also reset the computer account, which allows for anyone granted appropriate permissions to join the computer to the domain again.

## EXAMPLES

### Example 1: Modify a pre-staged client in the current AD DS domain
```
PS C:\> Set-WdsClient -DeviceName "TSQA087" -BootImagePath "boot\x86\images\Contosox86boot.wim" -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -PxePromptPolicy OptOut -ReferralServer "WindowsDS07" -ResetAccount -WdsClientUnattend "WindowsDSClientUnattend\Unattend.xml"
```

This command modifies a pre-staged client named TSQA087.
The command specifies a boot image file, a device ID, and a referral server.
The command changes the prompt policy to opt-out.
The command specifies the *ResetAccount* parameter, so the command resets permissions so that anyone granted appropriate permissions can join the domain.
The command also specifies an answer file that is named Unattend.xml.

### Example 2: Modify a pre-staged client in the current AD DS domain
```
PS C:\>Set-WdsClient -DeviceName "TSQA103" -Domain -DomainName "TSQA.Contoso.com" -Group "2013Purchases" -JoinDomain $True -PxePromptPolicy NoPrompt
```

This command modifies a pre-staged client named TSQA103.
The command specifies the *Domain* parameter to indicate that the client belongs a specified domain that is named TSQA.Contoso.com.
The command adds the client to the group named 2013Purchases.
The command changes the prompt policy to no prompt.
The command includes the *JoinDomain* parameter, so the computer joins adomain.

### Example 3: Modify a pre-staged client in the current AD DS forest
```
PS C:\>Set-WdsClient -DeviceName "TSQA108" -SearchForest -BootImagePath "boot\x86\images\Contosox86boot.wim"
```

This command modifies specifies a boot image file for the pre-staged client named TSQA108.
The *SearchForest* parameter indicates the cmdlet can find that computer in any domain in the current AD DS forest.

### Example 4: Modify join rights and user
```
PS C:\>Set-WdsClient -DeviceName "TSQA117" -JoinRights JoinOnly -User "TSQADOMAIN\PattiFuller" -BootImagePath "boot\x86\images\Contosox86boot.wim" -ReferralServer "WindowsDS07"
```

This command modifies a pre-staged client named TSQA117.
The command specifies a user named TSQADOMAIN\PattiFuller, and assigns JoinOnly rights for that user.
The command also specifies boot image and a referral server.

### Example 5: Modify join rights, user, and prompt policy
```
PS C:\>Set-WdsClient -DeviceName "TSQA121" -Domain -JoinRights Full -User "TSQADOMAIN\PattiFuller" -PxePromptPolicy OptIn
```

This command modifies a pre-staged client named TSQA121.
The command specifies a user named TSQADOMAIN\PattiFuller Unlike the previous example, the command assigns the user full join rights.
The command specifies opt-in as the prompt policy.

### Example 6: Modify join rights, user, and prompt policy for a client in the current AD DS forest
```
PS C:\>Set-WdsClient -DeviceName "TSQA128" -JoinRights JoinOnly -SearchForest -User "TSQADOMAIN\PattiFuller" -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -JoinDomain $True -ResetAccount -WdsClientUnattend "WindowsDSClientUnattend\Unattend.xml"
```

This command modifies a pre-staged client named TSQA128.
The *SearchForest* parameter indicates the cmdlet can find that computer could be in any domain in the current AD DS forest.

The command specifies a value of $True for the *JoinDomain* parameter, so the cmdlet joins the computer to a domain.
The command specifies a user named TSQADOMAIN\PattiFuller, and assigns JoinOnly rights for that user.
The command also specifies the *ResetAccount* parameter, so the command resets permissions so that anyone granted appropriate permissions can join the domain.

This command also assigns an ID to the client by using the *DeviceID* parameter.
The command also specifies an answer file that is named Unattend.xml.

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
This is the path of the boot image file for the computer.

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

### -DeviceID
Specifies the ID of the computer.
This identifier is the GUID of a network adapter, a MAC address, or a DHCP unique identifier associated with the computer.

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

### -DeviceName
Specifies the name of the computer associated with the pre-staged client.
This is a **sAMAccountName** value.

```yaml
Type: String
Parameter Sets: UserAndJoinRightsSearchForest, UserAndJoinRightsDomain, UserAndJoinRights, SearchForest, Domain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: DeviceName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Indicates that the cmdlet refers to pre-staged clients in the domain specified by the *DomainName* parameter, instead of the domain of the server that runs Windows Deployment Services or the whole forest.

```yaml
Type: SwitchParameter
Parameter Sets: UserAndJoinRightsDomain, Domain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies a domain name.
Specify a value for this parameter only if you specify the *Domain* parameter.

```yaml
Type: String
Parameter Sets: UserAndJoinRightsDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Indicates whether to join the computer to a domain as the account specified by the *User* parameter.

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
Parameter Sets: UserAndJoinRightsSearchForest, UserAndJoinRights
Aliases:
Accepted values: JoinOnly, Full

Required: True
Position: Named
Default value: TRUE
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

```yaml
Type: JoinRights
Parameter Sets: UserAndJoinRightsDomain
Aliases:
Accepted values: JoinOnly, Full

Required: True
Position: Named
Default value: TRUE
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

### -ResetAccount
Indicates that the cmdlet resets the permissions on the computer so that anyone granted appropriate permissions can join the domain using the account specified by the *User* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SearchForest
Indicates that the cmdlet refers to pre-staged devices in the current AD DS forest.
If you do not specify this parameter and do not specify the *Domain* parameter, the cmdlet looks for pre-staged devices in the local domain.

```yaml
Type: SwitchParameter
Parameter Sets: UserAndJoinRightsSearchForest, SearchForest
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: UserAndJoinRightsSearchForest, UserAndJoinRights
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UserAndJoinRightsDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsClient

## NOTES

## RELATED LINKS

[Approve-WdsClient](./Approve-WdsClient.md)

[Deny-WdsClient](./Deny-WdsClient.md)

[Get-WdsClient](./Get-WdsClient.md)

[New-WdsClient](./New-WdsClient.md)

[Remove-WdsClient](./Remove-WdsClient.md)

