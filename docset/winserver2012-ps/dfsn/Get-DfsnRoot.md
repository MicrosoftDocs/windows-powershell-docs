---
author: Kateyanne
external help file: DfsNamespace.cdxml-help.xml
manager: dansimp
Module Name: DFSN
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dfsn/get-dfsnroot?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DfsnRoot

## SYNOPSIS
Gets settings for DFS namespaces.

## SYNTAX

### ByDomain (Default)
```
Get-DfsnRoot [[-Domain] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByRoot
```
Get-DfsnRoot [[-Path] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByServer
```
Get-DfsnRoot [[-ComputerName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsnRoot** cmdlet gets configuration settings for Distributed File System (DFS) namespaces.
You can specify DFS namespaces by using a standalone or domain-based namespace path, by using a server, or by using a domain.
Use this cmdlet without parameters to see information on all DFS namespaces.
You can make changes to DFS settings by using the Set-DfsnRoot cmdlet.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Get DFS namespace configuration settings
```
PS C:\> Get-DfsnRoot -Path "\\Contoso\AccountingResources" | Format-List
Path          : \\Contoso\AccountingResources
Description   :
Type          : Standalone
State         : Online
Flags         : Site Costing
TimeToLiveSec : 300
```

This command gets configuration settings for the namespace that has the Path \\\\Contoso\AccountingResources.
The command uses the **Format-List** cmdlet to format the output.
For more information about this cmdlet, type `Get-Help Format-List`.

### Example 2: Get all DFS namespaces for a domain
```
PS C:\> Get-DfsnRoot -Domain "Contoso.com"
```

This command gets all the DFS namespaces hosted in the domain Contoso.com.

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
Specifies the name of a server.
This cmdlet gets configuration settings for all DFS namespaces that the specified server hosts.

```yaml
Type: String
Parameter Sets: ByServer
Aliases: Server

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Domain
Specifies a domain name.
This cmdlet gets configuration settings for DFS namespaces in the domain specified.

```yaml
Type: String
Parameter Sets: ByDomain
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies a path for the root folder of a DFS namespace.
This cmdlet gets configuration settings for the DFS namespace that has the root path specified.

```yaml
Type: String
Parameter Sets: ByRoot
Aliases: RootPath, root, namespace, NamespaceRoot

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespace[]

## NOTES

## RELATED LINKS

[New-DfsnRoot](./New-DfsnRoot.md)

[Remove-DfsnRoot](./Remove-DfsnRoot.md)

[Set-DfsnRoot](./Set-DfsnRoot.md)

