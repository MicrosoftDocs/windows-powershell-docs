---
external help file: SmbShare_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 6160AB3A-4385-421C-B6EE-9357FF436E1D
manager: dansimp
---

# Get-SmbSession

## SYNOPSIS
Retrieves information about the Server Message Block (SMB) sessions that are currently established between the SMB server and the associated clients.

## SYNTAX

```
Get-SmbSession [[-SessionId] <UInt64[]>] [[-ClientComputerName] <String[]>] [[-ClientUserName] <String[]>]
 [[-ScopeName] <String[]>] [[-ClusterNodeName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-IncludeHidden] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-SmbSession** cmdlet retrieves basic information about the Server Message Block (SMB) sessions that are currently established between the SMB server and the associated clients.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-SmbSession
SessionId                     ClientComputerName            ClientUserName                NumOpens 
---------                     ------------------            --------------                -------- 
85899345929                   [fe80::c8c0:f65d:3bc6:7313]   Contoso\Contoso-FS1$          0 
4415226380377                 192.168.102.14                Contoso\Contoso-HV2$          1 
4415226380385                 192.168.102.14                Contoso\Contoso-HV2$          1 
4415226380393                 192.168.102.14                Contoso\Contoso-HV2$          5 
8813272891397                 [fe80::6484:f325:adff:39eb]   Contoso\Contoso-FS2$          0 
8813272891441                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891449                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891457                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891461                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891469                 192.168.101.13                Contoso\Contoso-HV1$          5 
8813272891489                 192.168.102.14                Contoso\Contoso-HV2$          1 
8813272891493                 192.168.102.14                Contoso\Contoso-HV2$          1 
8813272891517                 192.168.102.14                Contoso\Contoso-HV2$          5 
8813272891581                 192.168.102.13                Contoso\Contoso-HV1$          1 
8813272891585                 192.168.102.13                Contoso\Contoso-HV1$          1 
8813272891609                 192.168.102.13                Contoso\Contoso-HV1$          3 
8813272891613                 192.168.101.13                Contoso\Contoso-HV1$          2 
8813272891621                 192.168.101.13                Contoso\Administrator         0
```

This example retrieves information about the SMB sessions that are currently established between the SMB server and the associated clients.

### EXAMPLE 2
```
PS C:\>Get-SmbSession -SessionId 8813272891621
SessionId                     ClientComputerName            ClientUserName                NumOpens 
---------                     ------------------            --------------                -------- 
8813272891621                 192.168.101.13                Contoso\Administrator         0
```

This example retrieves information about the SMB session identified as 8813272891621 that is currently established between the SMB server and the associated clients.

### EXAMPLE 3
```
PS C:\>Get-SmbSession -ClientComputerName 192.168.102.14
SessionId                     ClientComputerName            ClientUserName                NumOpens 
---------                     ------------------            --------------                -------- 
4415226380377                 192.168.102.14                Contoso\Contoso-HV2$          1 
4415226380385                 192.168.102.14                Contoso\Contoso-HV2$          1 
4415226380393                 192.168.102.14                Contoso\Contoso-HV2$          5 
8813272891489                 192.168.102.14                Contoso\Contoso-HV2$          1 
8813272891493                 192.168.102.14                Contoso\Contoso-HV2$          1 
8813272891517                 192.168.102.14                Contoso\Contoso-HV2$          5
```

This example retrieves information about the SMB sessions that are currently established between the SMB server and the SMB client at the IP address 192.168.102.14.

### EXAMPLE 4
```
PS C:\>Get-SmbSession -ClientUserName Contoso\Contoso-HV1$
SessionId                     ClientComputerName            ClientUserName                NumOpens 
---------                     ------------------            --------------                -------- 
8813272891441                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891449                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891457                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891461                 192.168.101.13                Contoso\Contoso-HV1$          1 
8813272891469                 192.168.101.13                Contoso\Contoso-HV1$          5 
8813272891581                 192.168.102.13                Contoso\Contoso-HV1$          1 
8813272891585                 192.168.102.13                Contoso\Contoso-HV1$          1 
8813272891609                 192.168.102.13                Contoso\Contoso-HV1$          3 
8813272891613                 192.168.101.13                Contoso\Contoso-HV1$          2
```

This example retrieves information about the SMB sessions that are currently established between the SMB server and the SMB client with the user name Contoso\Contoso-HV1$.

### EXAMPLE 5
```
PS C:\>Get-SmbSession -SessionId 8813272891441 | Select-Object -Property *
ClientComputerName    : 192.168.101.13 
ClientUserName        : Contoso\Contoso-HV1$ 
ClusterNodeName       : Contoso-FS1 
Dialect               : 3.00 
NumOpens              : 1 
ScopeName             : Contoso-FS 
SecondsExists         : 45346 
SecondsIdle           : 33 
SessionId             : 8813272891441 
TransportName         : 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbSession 
CimInstanceProperties : {ClientComputerName, ClientUserName, ClusterNodeName, Dialect...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This example retrieves all of the information about the SMB session identified as 8813272891441 that are currently established between the SMB server and the SMB client.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientComputerName
Specifies the client computer name from which the only sessions are returned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientUserName
Specifies the name of the user whose sessions are retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClusterNodeName
Specifies, in the case of a share hosted by a Windows cluster, the name of the server which is hosting the sessions is retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeHidden
Indicates that sessions that are created and used internally will be enumerated as well.

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

### -ScopeName
Specifies the scope of the sessions being retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionId
Specifies the identifiers (IDs) that uniquely identify the sessions for which the information is retrieved.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_SmbSession object represents the sessions established between the SMB server and the associated clients.

## NOTES

## RELATED LINKS

[Close-SmbSession](./Close-SmbSession.md)

