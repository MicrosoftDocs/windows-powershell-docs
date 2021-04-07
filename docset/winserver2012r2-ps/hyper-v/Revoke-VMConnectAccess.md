---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/revoke-vmconnectaccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Revoke-VMConnectAccess
---

# Revoke-VMConnectAccess

## SYNOPSIS
Revokes access for one or more users to connect to a one or more virtual machines.

## SYNTAX

### VMName (Default)
```
Revoke-VMConnectAccess [-VMName] <String[]> [-UserName] <String[]> [-Passthru] [-ComputerName <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMId
```
Revoke-VMConnectAccess [-VMId] <Guid[]> [-UserName] <String[]> [-Passthru] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-VMConnectAccess** cmdlet revokes access for one or more users to connect to one or more virtual machines.
This cmdlet is intended for use in providing other applications with the appropriate permissions required to initiate a session with Virtual Machine Connection.
Examples of such applications are Virtual Machine Manager.

## EXAMPLES

### Example 1
```
PS C:\>Revoke-VMConnectAccess -VMName VM1 -UserName Contoso\John
```

This command revokes the access of user Contoso\John to connect to virtual machine VM1.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts on which access to connect to a virtual machine or machines is to be revoked.
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
Specifies that a **VMConnectAce** is to be passed through to the pipeline for each revocation of access.

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
Specifies the user or users to whom access to connect to a virtual machine or machines is to be revoked, in one of the following forms.

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
Specifies the unique identifier of a virtual machine or machines to which connect access is to be revoked.

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
Specifies the name or names of the virtual machine or machines to which access is being revoked.

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

