---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbWitnessWmiClient.cdxml-help.xml
Module Name: SmbWitness
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbwitness/get-smbwitnessclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbWitnessClient
---

# Get-SmbWitnessClient

## SYNOPSIS
Retrieves information about the SMB clients connected to the SMB witness servers in a cluster.

## SYNTAX

```
Get-SmbWitnessClient [[-ClientName] <String[]>] [-State <State[]>] [-Flags <Flags[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbWitnessClient** cmdlet retrieves information about Server Message Block (SMB) witness client registrations with SMB witness servers in a failover cluster.
SMB witness clients can register for notification for multiple resources in the failover cluster, so there may be multiple entries for the same SMB witness client.

## EXAMPLES

### Example 1: Get information about all the SMB clients for the witness servers in a cluster
```
PS C:\> Get-SmbWitnessClient
Client Computer Name       Witness Node Name          File Server Node Name      Network Name               Share Name
--------------------       -----------------          ---------------------      ------------               ----------
Server01                   FileServer1                FileServer2                FSCluster                  Share
Server02                   FileServer2                FileServer1                FSCluster                  Share
Server02                   FileServer2                FileServer1                FSCluster
```

This example retrieves information about the all of the SMB clients connected to the SMB witness servers in a cluster.

### Example 2: Get information about a named SMB client
```
PS C:\>Get-SmbWitnessClient -ClientName "Server01"
Client Computer Name       Witness Node Name          File Server Node Name      Network Name               Share Name
--------------------       -----------------          ---------------------      ------------               ----------
Server01                   FileServer1                FileServer2                FSCluster                  Share
```

This example retrieves information about the SMB client named Server01 connected to the SMB witness servers in a cluster.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -ClientName
Specifies one or more SMB clients by name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Flags
Specifies an array of flags.

```yaml
Type: Flags[]
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, NetworkName, ShareName, MultiChannel

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies that the output is filtered based on the state of the SMB witness client registrations with SMB witness servers in a failover cluster.
The acceptable values for this parameter are:

- Connected
- Registered
- RequestedNotifications
- Cancelled
- Disconnected
- Unknown

```yaml
Type: State[]
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Connected, Registered, RequestedNotifications, Cancelled, Disconnected

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Move-SmbWitnessClient](./Move-SmbWitnessClient.md)

