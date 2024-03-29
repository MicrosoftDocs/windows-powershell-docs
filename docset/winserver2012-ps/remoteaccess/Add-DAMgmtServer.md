---
external help file: UnifiedRA_Cmdlets.xml
Module Name: RemoteAccess
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-damgmtserver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DAMgmtServer

## SYNOPSIS
Adds the specified Management servers to the DirectAccess (DA) deployment.

## SYNTAX

```
Add-DAMgmtServer [-MgmtServer] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DAMgmtServer** cmdlet adds the specified Management servers to the DirectAccess (DA) deployment.
Management server here refers to update servers, Domain Controllers, and other servers.

Management server configuration is applicable globally, to the entire DA deployment and therefore is not impacted by multi-site deployments.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-DAMgmtServer -MgmtServer patch1.corp.contoso.com
```

This example will try to resolve the given servers to IP address and once resolved, the IP addresses would be added to the list of management servers configured for direct access.
Management server configuration is global and hence this will be added to all server GPOs.

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

### -MgmtServer
Specifies the list of management servers specified by IPv4 or IPv6 address, subnet or host name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### System.String[]
The array of strings consists of the following properties: 

List of management servers that were successfully added to the DA deployment.

## NOTES

## RELATED LINKS

[Get-DAMgmtServer](./Get-DAMgmtServer.md)

[Remove-DAMgmtServer](./Remove-DAMgmtServer.md)

[Update-DAMgmtServer](./Update-DAMgmtServer.md)

