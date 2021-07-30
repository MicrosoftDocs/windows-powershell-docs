---
external help file: DfsNamespaceFolder.cdxml-help.xml
Module Name: DFSN
online version: https://docs.microsoft.com/powershell/module/dfsn/set-dfsnfolder?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DfsnFolder

## SYNOPSIS
Changes settings for a DFS namespace folder.

## SYNTAX

```
Set-DfsnFolder [-Path] <String> [[-EnableInsiteReferrals] <Boolean>] [[-EnableTargetFailback] <Boolean>]
 [[-State] <State>] [[-TimeToLiveSec] <UInt32>] [[-Description] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsnFolder** cmdlet changes settings for a Distributed File System (DFS) namespace folder.

A DFS namespace folder has one or more folder targets that are shared folders on computers.
When a client attempts to connect to a folder, the DFS namespace server provides a list of folder targets, called referrals.
The server determines the order for referrals and clients attempt to connect to a folder target in the order that the server provides.

You can use this cmdlet to enable or disable the following settings: 

- In-site referrals. 
- Target failback.

You can also add or change a descriptive comment, change the state of the DFS namespace, or set the Time to Live (TTL) interval for referrals.

For more information about DFS namespaces, see Overview of DFS Namespaceshttps://technet.microsoft.com/library/cc730736 (https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Enable settings for a DFS namespace folder
```
PS C:\> Set-DfsnFolder -Path "\\Contoso\AccountingResources\LegacySoftware" -EnableInsiteReferrals $True -EnableTargetFailback $True
```

This command enables in-site referrals and target failback for the DFS namespace folder \\\\Contoso\AccountingResources\LegacySoftware.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for a DFS namespace folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: desc

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableInsiteReferrals
Indicates whether a DFS namespace server provides a client only with referrals that are in the same site as the client.
If this value is $True, a DFS namespace server provides only in-site referrals.
If this value is $False, the DFS namespace server provides in-site referrals first, then other referrals.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: insite

Required: False
Position: 1
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableTargetFailback
Indicates whether a DFS namespace uses target failback.
If a client attempts to access target link on a server and that server is not available, the client fails over to another referral.
If this value is $True, once the first server becomes available again, the client fails back to the first server.
If this value is $False, the DFS namespace server does not require the client to use the preferred server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: failback, TargetFailback

Required: False
Position: 2
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies a path for the DFS namespace folder.
This cmdlet modifies the folder that has the path specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DfsPath, FolderPath, NamespacePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the DFS namespace folder.
The acceptable values for this parameter are:

- Online
- Offline

Clients do not receive referrals for a DFS namespace folder that is offline.

```yaml
Type: State
Parameter Sets: (All)
Aliases: 
Accepted values: Offline, Online

Required: False
Position: 3
Default value: ONLINE
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

### -TimeToLiveSec
Specifies a TTL interval, in seconds, for referrals.
Clients store referrals to targets for this length of time.
The default TTL interval for folder referrals is 1800 seconds (30 minutes).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: ttl, TimeToLive

Required: False
Position: 4
Default value: 300
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceFolder

## NOTES

## RELATED LINKS

[Get-DfsnFolder](./Get-DfsnFolder.md)

[Move-DfsnFolder](./Move-DfsnFolder.md)

[New-DfsnFolder](./New-DfsnFolder.md)

[Remove-DfsnFolder](./Remove-DfsnFolder.md)

