---
external help file: UnifiedRA_Cmdlets.xml
Module Name: RemoteAccess
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-daentrypointdc?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DAEntryPointDC

## SYNOPSIS
Retrieves a list of entry points and the associated domain controllers (DCs).

## SYNTAX

```
Get-DAEntryPointDC [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-EntryPointName <String>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DAEntryPointDC** cmdlet retrieves a list of entry point names and the associated domain controllers (DCs).

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DAEntryPointDC

EntryPointName       : Entry Point 1 
DomainControllerName : dc1.domain1.corp.contoso.com 
 
EntryPointName       : Entry Point 2 
DomainControllerName : dc2.domain2.corp.contoso.com
```

This example displays all of the entry points and the associated DCs.
The output shows that, Entry Point 1 is associated with dc1.domain1.corp.contoso.com and Entry Point 2 is associated with dc2.domain2.corp.contoso.com.

### EXAMPLE 2
```
PS C:\>Get-DAEntryPointDC -EntryPointName "Entry Point 1"
EntryPointName       : Entry Point 1 
DomainControllerName : dc1.domain1.corp.contoso.com
```

This example displays a single entry point and the associated DC.
The output shows that, Entry Point 1 is associated with dc1.domain1.corp.contoso.com.

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
Specifies the IPv4 or IPv6 address, or host name, of a server or server cluster in the entry point.

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

### -EntryPointName
Specifies the name of the entry point for which DC information should be retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DADomainController[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of DADomainController objects contains the following: 

 -- Entry points. 

 -- Associated DCs.

## NOTES

## RELATED LINKS

[Add-DAEntryPoint](./Add-DAEntryPoint.md)

[Get-DAEntryPoint](./Get-DAEntryPoint.md)

[Remove-DAEntryPoint](./Remove-DAEntryPoint.md)

[Set-DAEntryPoint](./Set-DAEntryPoint.md)

[Set-DAEntryPointDC](./Set-DAEntryPointDC.md)

