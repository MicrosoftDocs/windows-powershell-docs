---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfssyncproperties?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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
The cmdlet also specifies which adfs2_fs is the primary server in the adfs2_fs farm.

## EXAMPLES

### Example 1: Modify the poll duration for a farm
```
PS C:\>Set-AdfsSyncProperties -PollDuration 3600 -PrimaryComputerName "FederationServerPrimary"
```

This command modifies the database synchronization to 3600 seconds.
The command makes the change to the primary adfs2_fs.

## PARAMETERS

### -PollDuration
Specifies how often, in seconds, the AD FS configuration database synchronizes with the primary adfs2_fs.

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
Specifies the name of the primary adfs2_fs in a adfs2_fs farm.
Modify settings for the Federation Service on the primary adfs2_fs.

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
The primary computer in the adfs2_fs farm uses the TCP port that you specify.
Modify settings for the Federation Service on the primary adfs2_fs.

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
Specifies the role for this adfs2_fs.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsSyncProperties](./Get-AdfsSyncProperties.md)

