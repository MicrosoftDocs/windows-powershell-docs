---
author: Kateyanne
external help file: DfsNamespaceServerConfig.cdxml-help.xml
manager: dansimp
Module Name: DFSN
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dfsn/get-dfsnserverconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DfsnServerConfiguration

## SYNOPSIS
Gets DFS namespace settings for a DFSN root server.

## SYNTAX

```
Get-DfsnServerConfiguration [-ComputerName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsnServerConfiguration** cmdlet gets Distributed File System (DFS) namespace settings for a DFS namespace root server.
A DFS namespace root server hosts one or more namespace root targets.
You can use this cmdlet to see current settings for a server, and you can use the Set-DfsnServerConfiguration cmdlet to make changes to a server.

## EXAMPLES

### Example 1: Get settings for a server
```
PS C:\> Get-DfsnServerConfiguration -ComputerName "Contoso-FS"
ComputerName              : Contoso-FS
LdapTimeoutSec            :
PreferLogonDC             :
EnableSiteCostedReferrals :
EnableInsiteReferrals     :
SyncIntervalSec           :
UseFqdn                   :
```

This command gets the Retrieves the configuration settings of the DFS namespace server Contoso-FS.

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

### -ComputerName
Specifies the host name or fully qualified domain name (FQDN) for a DFS namespace server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NamespaceServer

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceServerConfig

## NOTES

## RELATED LINKS

[Set-DfsnServerConfiguration](./Set-DfsnServerConfiguration.md)

