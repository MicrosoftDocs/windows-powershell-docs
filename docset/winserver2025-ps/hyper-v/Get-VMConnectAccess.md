---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmconnectaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMConnectAccess
---

# Get-VMConnectAccess

## SYNOPSIS
Gets entries showing users and the virtual machines to which they can connect on one or more Hyper-V hosts.

## SYNTAX

### VMName (Default)
```
Get-VMConnectAccess [[-VMName] <String[]>] [-UserName <String[]>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

### VMId
```
Get-VMConnectAccess [-VMId] <Guid[]> [-UserName <String[]>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMConnectAccess** cmdlet gets entries showing users and the virtual machines to which they can connect on one or more Hyper-V hosts.
This cmdlet is intended for use in providing other applications with the appropriate permissions required to initiate a session with the Virtual Machine Connection protocol.
Examples of such applications are Virtual Machine Manager.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMConnectAccess
```

This command gets a list of all the users who have access to connect to any virtual machine on the local computer.
The example assumes that the Grant-VMConnectAccess has been run previously for at least one user account.

### Example 2
```
PS C:\> Get-VMConnectAccess -VMName VM1
```

This command gets a list of all the users who have access to connect to virtual machine VM1.
The example assumes that the Grant-VMConnectAccess has been run previously for at least one user account for virtual machine VM1.

### Example 3
```
PS C:\> Get-VMConnectAccess -UserName CONTOSO\John
```

This command gets a list of all the virtual machines on the local computer that user Contoso\John has access to connect to.
The example assumes that the Grant-VMConnectAccess has been run previously to grant access to Contoso\John.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies one or more Hyper-V hosts that run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user or users for whom connect access entries are being sought.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: UserId, Sid

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMId
Specifies the unique identifier of a virtual machine for which connect access entries are being sought.

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
Specifies the name of the virtual machine for which connect access entries are being sought.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMConnectAce

## NOTES

## RELATED LINKS

