---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-VMReplicationAuthorizationEntry

## SYNOPSIS
Removes an authorization entry from a Replica server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMReplicationAuthorizationEntry [-AllowedPrimaryServer] <String> [-ComputerName <String[]>] [-PassThru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMReplicationAuthorizationEntry [-TrustGroup] <String> [-ComputerName <String[]>] [-PassThru] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMReplicationAuthorizationEntry [-VMReplicationAuthorizationEntry] <VMReplicationAuthorizationEntry[]>
 [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VMReplicationAuthorizationEntry** cmdlet removes an authorization entry from a Replica server, which cancels authorization for the primary server associated with the entry.
After the authorization entry is removed, the Replica server does not accept replication data from the corresponding primary server.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMReplicationAuthorizationEntry -AllowedPrimaryServer server01.domain01.contoso.com
```

This example removes an authorization entry on the local Replica server for allowed primary server server01.domain01.contoso.com.

### Example 2
```
PS C:\>Get-VMReplicationAuthorizationEntry | Remove-VMReplicationAuthorizationEntry
```

This example removes all authorization entries on the local Replica server.

## PARAMETERS

### -AllowedPrimaryServer
Specifies the allowed primary server for which the authorization entry is to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: AllowedPS

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the authorization entry is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that a **VMReplicationAuthorizationEntry** object is to be passed through to the pipeline representing the authorization entry to be removed.

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

### -TrustGroup
Specifies the trust group for which the authorization entries are to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMReplicationAuthorizationEntry
Specifies the authorization entry to be removed.

```yaml
Type: VMReplicationAuthorizationEntry[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: VMRepAuthEntry

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

## OUTPUTS

### None
Default

### VMReplicationAuthorizationEntry
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



