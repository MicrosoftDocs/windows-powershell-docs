---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/grant-vmconnectaccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-VMConnectAccess
---

# Grant-VMConnectAccess

## SYNOPSIS
Grants a user or users access to connect to a virtual machine or machines.

## SYNTAX

### VMName (Default)
```
Grant-VMConnectAccess [-VMName] <String[]> [-UserName] <String[]> [-Passthru] [-ComputerName <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMId
```
Grant-VMConnectAccess [-VMId] <Guid[]> [-UserName] <String[]> [-Passthru] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-VMConnectAccess** cmdlet grants access to a user or users to connect to a virtual machine or machines.
The cmdlet is intended for use in providing other applications with the appropriate permissions required to initiate a session with Virtual Machine Connection.
Examples of such applications are Virtual Machine Manager.

## EXAMPLES

### Example 1
```
PS C:\>Grant-VMConnectAccess -VMName VM1 -UserName Contoso\John
```

This command grants user Contoso\John access to connect to a virtual machine named VM1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which access to connect to a virtual machine is to be granted.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMConnectAce** object is to be passed through to the pipeline representing each grant of access.

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

### -UserName
Specifies a user or users to whom access to connect to a virtual machine or machines is to be granted, in one of the following forms:

Local User Account:
    john
    ComputerName\john

                         
Domain User Account:
    CONTOSO\john
    Contoso.com\john

                         
User Principal Name (UPN):
    john@contoso.com

                         
Security Identifier:
    S-1-5-21-3165297888-301567370-576410423-1103

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: UserId, Sid

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMId
Specifies the unique identifier of a virtual machine to which connect access is to be granted.

```yaml
Type: Guid[]
Parameter Sets: VMId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of a virtual machine to which connect access is to be granted.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.VMConnectAce** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

