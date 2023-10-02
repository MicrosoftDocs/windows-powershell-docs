---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfssyncconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADFSSyncConfiguration

## SYNOPSIS
Sets the configuration properties of the database synchronization engine for the federation server farm.

## SYNTAX

```
Set-ADFSSyncConfiguration [-PrimaryComputerName <String>] [-PrimaryComputerPort <Int32>]
 [-PollDuration <Int32>] [-Role <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSSyncConfiguration cmdlet changes the frequency of AD FS configuration database synchronization.
It also specifies which federation server is the primary federation server in the federation server farm

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Set-ADFSSyncConfiguration -PrimaryComputerName fs1.fabrikam.com
```

Sets the name of the primary federation server in a federation server farm.

## PARAMETERS

### -PollDuration
Specifies (in seconds) how often the AD FS configuration database is synchronized from the primary federation server.

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
Specifies the name of the primary federation server in the federation server farm.
Settings for the Federation Service may be modified on the primary federation server.

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
Specifies the TCP port to use on the primary computer in the federation service farm.
Settings for the federation service may be modified on the primary computer.

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
Specifies whether this federation server is the primary federation server or a secondary federation server.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* This cmdlet is for use when working with server computers as part of a federation server farm.

## RELATED LINKS

[Get-ADFSSyncConfiguration](./Get-ADFSSyncConfiguration.md)

