---
external help file: SMTasks_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 2C57BC34-F9B7-419A-80E6-563465BCCF2A
manager: dansimp
---

# Get-SMServerClusterName

## SYNOPSIS
Retrieves the name of a server cluster.

## SYNTAX

```
Get-SMServerClusterName [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-SMServerClusterName** cmdlet retrieves the name of a server cluster, if the target server participates in a cluster.
A server cluster is a group of computers that work together as a single resource.

## EXAMPLES

### Example 1: Get the server cluster name
```
PS C:\>Get-SMServerClusterName
```

This command gets the server cluster name.

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

## OUTPUTS

## NOTES

## RELATED LINKS

