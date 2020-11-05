---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B49B434A-027E-4AB5-9717-AD930B15AA5A
manager: dansimp
---

# Get-DAMgmtServer

## SYNOPSIS
Displays the configured management servers.
Management server here refers to update servers, Domain Controllers and other servers.

## SYNTAX

```
Get-DAMgmtServer [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
 [-Type <String>]
```

## DESCRIPTION
The **Get-DAMgmtServer** cmdlet displays the configured management servers.
Management server here refers to update servers, Domain Controllers, and other servers.

The server addresses are displayed in the same format in which the addresses were originally added (IPv4 or IPv6 address, or host name).

Management server configuration is applicable globally, to the entire DirectAccess (DA) deployment and hence is not impacted by multi-site deployments.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DAMgmtServer -Type DC
DC1.corp.contoso.com
```

This example retrieves a list of all domain controllers which were configured automatically by DA and does not include the servers configured manually.

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer specific tasks should be run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### -Type
Specifies the type of management server to be listed.
The acceptable values for this parameter are: DC, SCCM, Manual, or All.
If not specified, then manual and SCCM servers will be output.
Anything that is not a Domain Controllers is listed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Manual
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### System.String[]
The array of strings consists of the following properties: 

 -- The list of management servers configured.

## NOTES

## RELATED LINKS

[Add-DAMgmtServer](./Add-DAMgmtServer.md)

[Remove-DAMgmtServer](./Remove-DAMgmtServer.md)

[Update-DAMgmtServer](./Update-DAMgmtServer.md)

