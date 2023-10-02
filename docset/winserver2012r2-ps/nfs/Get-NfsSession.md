---
external help file: MSFT_NfsSession.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfssession?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NfsSession
---

# Get-NfsSession

## SYNOPSIS
Gets information about which client computers are currently connected to one or more shares on an NFS server.

## SYNTAX

```
Get-NfsSession [[-SessionId] <String[]>] [[-ClientId] <UInt64[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NfsSession** cmdlet gets information about Network File System (NFS) sessions that client computers establish on an NFS server.
The session ID characterizes each NFS session.
You can specify a session ID in the **Get-NfsOpenFile** and **Get-NfsClientLock** cmdlets to get a list of open or locked files or on a client computer.

## EXAMPLES

### Example 1: Get all NFS sessions for a specified client computer
```
PS C:\> Get-NfsSession -ClientId 101
```

This command gets all NFS sessions on a local NFS server for a client computer that has the ID 101.

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

### -ClientId
Specifies the ID of one or more NFS clients.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionId
Specifies the unique ID of one or more NFS sessions.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsSession

## NOTES

## RELATED LINKS

[Disconnect-NfsSession](./Disconnect-NfsSession.md)

[Get-NfsOpenFile](./Get-NfsOpenFile.md)

[Get-NfsClientLock](./Get-NfsClientLock.md)

