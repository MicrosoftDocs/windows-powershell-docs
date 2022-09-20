---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netprefixpolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetPrefixPolicy

## SYNOPSIS
Gets information about the prefix policy.

## SYNTAX

```
Get-NetPrefixPolicy [[-Prefix] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-Label <UInt32[]>]
 [-Precedence <UInt32[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetPrefixPolicy** cmdlet gets the prefix policy.
The prefix policy is used in source and destination address selection.
The prefix policy is described in RFC 3484http://www.ietf.org/rfc/rfc3484.txt.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetPrefixPolicy
```

This example gets information about the prefix policy.

### EXAMPLE 2
```
PS C:\>Get-NetPrefixPolicy -Precedence 1
```

This example gets information about the prefix policy that has a precedence of 1.

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

### -Label
Gets prefix policy by a specific Label.
The label value allows for policies that prefer a particular source address prefix for use with a destination address prefix.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Precedence
Gets prefix policy by a specific Precedence.
The Precedence value is used for sorting destination addresses.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefix
Gets prefix policy by a specific Prefix.
The Prefix determines the IP address prefix used to by source and destination address selection algorithms.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetPrefixPolicy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Source and Destination Address Selection for IPv6 on TechNet](https://technet.microsoft.com/library/bb877985.aspx)

