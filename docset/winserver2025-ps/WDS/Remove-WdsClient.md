---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsClient_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/remove-wdsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WdsClient
---

# Remove-WdsClient

## SYNOPSIS
Removes a pre-staged client from AD DS or the stand-alone server device database, or clears the Pending Devices database.

## SYNTAX

### PrestagedClientByDeviceName (Default)
```
Remove-WdsClient -DeviceName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### PendingClientByStatus
```
Remove-WdsClient -PendingClientStatus <PendingClientStatusFlag> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### PrestagedClientByDeviceIdSearchForest
```
Remove-WdsClient -DeviceID <String> [-SearchForest] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### PrestagedClientByDeviceIdDomain
```
Remove-WdsClient -DeviceID <String> [-DomainName <String>] [-Domain] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### PrestagedClientByDeviceId
```
Remove-WdsClient -DeviceID <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### PrestagedClientByDeviceNameDomain
```
Remove-WdsClient [-DomainName <String>] [-Domain] -DeviceName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### PrestagedClientByDeviceNameSearchForest
```
Remove-WdsClient [-SearchForest] -DeviceName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WdsClient** cmdlet removes a pre-staged client from Active Directory® Domain Services (AD DS) or the stand-alone server device database, or clears the Pending Devices database.

To remove pre-staged client from AD DS, specify the name of the computer or the device ID, which is a GUID, media access control (MAC) address, or Dynamic Host Configuration Protocol (DHCP) identifier associated with the computer.
You can specify a client within AD DS domain of the server that runs Windows Deployment Services, in a specified domain, or anywhere in the current AD DS forest.

To clear the Pending Devices database, specify whether to remove devices that are approved, denied, or pending.

## EXAMPLES

### Example 1: Remove a device by using its ID from a specified domain
```
PS C:\> Remove-WdsClient -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -Domain -DomainName "TSQA.Contoso.com"
```

This command removes the pre-staged device that has the specified ID.
The cmdlet searches the domain named TSQA.Contoso.com for the device.

### Example 2: Remove a device by using its name from a specified domain
```
PS C:\>Remove-WdsClient -DeviceName "TSQA014" -Domain -DomainName "TSQA.Contoso.com"
```

This command removes the pre-staged device named TSQA014.
The cmdlet searches the domain named TSQA.Contoso.com for the device.

### Example 3: Remove a device by using its ID
```
PS C:\>Remove-WdsClient -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -SearchForest
```

This command removes a pre-staged device that has the specified ID.
The cmdlet searches the whole forest for the device.

### Example 4: Remove a device by using its name
```
PS C:\>Remove-WdsClient -DeviceName "TSQA073" -SearchForest
```

This command removes a pre-staged device named TSQA073.
The cmdlet searches the whole forest for the device.

### Example 5: Remove all approved devices in the local domain
```
PS C:\>Remove-WdsClient -PendingClientStatus Approved
```

This command removes pre-staged devices that have a pending status of Approved.
Because the command does not specify the *Domain* parameter or the *SearchForest* parameter, it removes devices only in the local domain.

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
Parameter Sets: PrestagedClientByDeviceIdSearchForest, PrestagedClientByDeviceIdDomain, PrestagedClientByDeviceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the computer associated with the pre-staged client.
This is a **sAMAccountName** value.

```yaml
Type: String
Parameter Sets: PrestagedClientByDeviceName, PrestagedClientByDeviceNameDomain, PrestagedClientByDeviceNameSearchForest
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Domain
Indicates that the cmdlet refers to pre-staged clients in the domain specified by the *DomainName* parameter, instead of the domain of the server that runs Windows Deployment Services or the whole forest.

```yaml
Type: SwitchParameter
Parameter Sets: PrestagedClientByDeviceIdDomain, PrestagedClientByDeviceNameDomain
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
Parameter Sets: PrestagedClientByDeviceIdDomain, PrestagedClientByDeviceNameDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PendingClientStatus
Specifies a pending client status.
The acceptable values for this parameter are:

- Any
- Approved
- Denied
- Pending

```yaml
Type: PendingClientStatusFlag
Parameter Sets: PendingClientByStatus
Aliases:
Accepted values: Pending, Approved, Denied, Any

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SearchForest
Indicates that the cmdlet refers to pre-staged devices anywhere in the current AD DS forest.
If you do not specify this parameter and do not specify the *Domain* parameter, the cmdlet looks for pre-staged devices in the local domain.

```yaml
Type: SwitchParameter
Parameter Sets: PrestagedClientByDeviceIdSearchForest, PrestagedClientByDeviceNameSearchForest
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Approve-WdsClient](./Approve-WdsClient.md)

[Deny-WdsClient](./Deny-WdsClient.md)

[Get-WdsClient](./Get-WdsClient.md)

[New-WdsClient](./New-WdsClient.md)

[Set-WdsClient](./Set-WdsClient.md)

