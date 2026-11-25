---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsClient_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/get-wdsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WdsClient
---

# Get-WdsClient

## SYNOPSIS
Gets client devices from the pending device database, or pre-staged devices from Active Directory or the stand-alone server device database.

## SYNTAX

### PrestagedClientByDeviceName (Default)
```
Get-WdsClient [-DeviceName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### PendingClientByRequestId
```
Get-WdsClient -RequestId <UInt32> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### PendingClientByStatus
```
Get-WdsClient -PendingClientStatus <PendingClientStatusFlag> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### PrestagedClientByDeviceIdSearchForest
```
Get-WdsClient -DeviceID <String> [-SearchForest] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### PrestagedClientByDeviceIdDomain
```
Get-WdsClient -DeviceID <String> [-Domain] [-DomainName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### PrestagedClientByDeviceId
```
Get-WdsClient -DeviceID <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### PrestagedClientByDeviceNameDomain
```
Get-WdsClient [-Domain] [-DomainName <String>] [-DeviceName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### PrestagedClientByDeviceNameSearchForest
```
Get-WdsClient [-SearchForest] [-DeviceName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WdsClient** cmdlet gets client devices from the Pending Device database, or pre-staged clients from Active Directory® Domain Services (AD DS) or the stand-alone server device database.

You can get client devices or pre-staged clients by specifying a name or an ID.
An ID is a GUID, media access control (MAC) address, or Dynamic Host Configuration Protocol (DHCP) identifier associated with the computer.

When you get clients from AD DS, you can specify a client within AD DS domain of the server that runs Windows Deployment Services, in a specified domain, or anywhere in the current AD DS forest.

To get pre-staged clients from the Pending Devices database, specify whether to get devices that are approved, denied, or pending.

## EXAMPLES

### Example 1: Get a device in a domain by specifying its ID
```
PS C:\> Get-WdsClient -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -Domain -DomainName "TSQA.Contoso.com"
```

This command gets the device that has the specified ID.
The command looks for this device in the AD DS domain named TSQA.Contoso.com.

### Example 2: Get a device in a domain by specifying its ID
```
PS C:\>Get-WdsClient -DeviceName "TSQA076" -Domain "TSQA.Contoso.com"
```

This command gets the device named TSQA076.
The command looks for this device in the AD DS domain named TSQA.Contoso.com.

### Example 3: Get a device in the current forest by specifying its ID
```
PS C:\>Get-WdsClient -DeviceID "5a7a1def-2e1f-4a7b-a792-ae5275b6ef92" -SearchForest
```

This command gets the device that has the specified ID.
The command looks for this device in the current AD DS forest.

### Example 4: Get a device in the current forest by specifying its name
```
PS C:\>Get-WdsClient -DeviceName "TSQA022" -SearchForest
```

This command gets the device named TSQA022.
The command looks for this device in the current AD DS forest.

### Example 5: Get all pending devices
```
PS C:\>Get-WdsClient -PendingClientStatus Pending
```

This command gets all clients that have a status of Pending in the Pending Devices database.

### Example 6: Get a pending device by specifying its request ID
```
PS C:\>Get-WdsClient -RequestId 21
```

This command gets the client that has the request ID 21 in the Pending Devices database.

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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the computer associated with the pre-staged client.
This is a **sAMAccountName** value.

```yaml
Type: String
Parameter Sets: PrestagedClientByDeviceName, PrestagedClientByDeviceNameDomain, PrestagedClientByDeviceNameSearchForest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Accept pipeline input: False
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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RequestId
Specifies the request ID that the server that runs Windows Deployment Services allocates to a device in the Pending Device database.
If you do not specify this parameter, the cmdlet gets all devices that match the value specified in the *PendingClientStatus* parameter.

```yaml
Type: UInt32
Parameter Sets: PendingClientByRequestId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsClient

## NOTES

## RELATED LINKS

[Approve-WdsClient](./Approve-WdsClient.md)

[Deny-WdsClient](./Deny-WdsClient.md)

[New-WdsClient](./New-WdsClient.md)

[Remove-WdsClient](./Remove-WdsClient.md)

[Set-WdsClient](./Set-WdsClient.md)

