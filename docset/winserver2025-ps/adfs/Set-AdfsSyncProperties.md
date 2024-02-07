---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfssyncproperties?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsSyncProperties
---

# Set-AdfsSyncProperties

## SYNOPSIS
Modifies the frequency of synchronization for the AD FS configuration database and which server is primary in the farm.

## SYNTAX

```
Set-AdfsSyncProperties [-PrimaryComputerName <String>] [-PrimaryComputerPort <Int32>] [-PollDuration <Int32>]
 [-Role <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADFSSyncProperties** cmdlet modifies the frequency of synchronization for the Active Directory Federation Services (AD FS) configuration database.
The cmdlet also specifies which federation server is the primary server in the federation server farm.

## EXAMPLES

### Example 1: Modify the poll duration for a farm
```
PS C:\> Set-AdfsSyncProperties -PollDuration 3600 -PrimaryComputerName "FederationServerPrimary"
```

This command modifies the database synchronization to 3600 seconds.
The command makes the change to the primary federation server.

### Example 2: Change a server from secondary to primary
```
PS C:\> Set-AdfsSyncProperties -Role "PrimaryComputer"
```

This command changes an AD FS server in a WID farm from secondary to primary.

### Example 3: Change a primary server to a secondary server
```
PS C:\> Set-AdfsSyncProperties -Role "SecondaryComputer" -PrimaryComputerName "<FQDN of primary server>"
```

This command changes a primary AD FS server in a WID farm to a secondary server.
Note: The primary server must be accessible via HTTP on port 80 from the secondary server.

## PARAMETERS

### -PollDuration
Specifies how often, in seconds, the AD FS configuration database synchronizes with the primary federation server.

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

### -PrimaryComputerName
Specifies the name of the primary federation server in a federation server farm.
Modify settings for the Federation Service on the primary federation server.

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

### -PrimaryComputerPort
Specifies the primary computer port.
The primary computer in the federation server farm uses the TCP port that you specify.
Modify settings for the Federation Service on the primary federation server.

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

### -Role
Specifies the role for this federation server.
The acceptable values for this parameter are: primary and secondary.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsSyncProperties](./Get-AdfsSyncProperties.md)

