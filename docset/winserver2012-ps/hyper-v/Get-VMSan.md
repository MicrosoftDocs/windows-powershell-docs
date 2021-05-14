---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmsan?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMSan

## SYNOPSIS
Gets the available virtual machine storage area networks on a Hyper-V host or hosts.

## SYNTAX

```
Get-VMSan [[-Name] <String[]>] [-ComputerName <String[]>]
```

## DESCRIPTION
The **Get-VMSan** cmdlet gets the available virtual storage area networks (SANs) on one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSan -Name ProductionSAN
```

Gets a virtual storage area network (SAN) named ProductionSAN.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the available virtual machine storage area networks (SANs) are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of a virtual storage area network (SAN) to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



