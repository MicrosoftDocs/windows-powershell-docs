---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VMConnectAccess

## SYNOPSIS
Gets entries showing users and the virtual machines to which they can connect on one or more Hyper-V hosts.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMConnectAccess [[-VMName] <String[]>] [-ComputerName <String[]>] [-UserName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMConnectAccess [-VMId] <Guid[]> [-ComputerName <String[]>] [-UserName <String[]>]
```

## DESCRIPTION
The **Get-VMConnectAccess** cmdlet gets entries showing users and the virtual machines to which they can connect on one or more Hyper-V hosts.
This cmdlet is intended for use in providing other applications with the appropriate permissions required to initiate a session with Virtual Machine Connection.
Examples of such applications are Virtual Machine Manager.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMConnectAccess
```

This command gets a list of all the users who have access to connect to any virtual machine on the local computer.
The example assumes that the Grant-VMConnectAccess has been run previously for at least one user account.

### Example 2
```
PS C:\>Get-VMConnectAccess -VMName VM1
```

This command gets a list of all the users who have access to connect to virtual machine VM1.
The example assumes that the Grant-VMConnectAccess has been run previously for at least one user account for virtual machine VM1.

### Example 3
```
PS C:\>Get-VMConnectAccess -UserName CONTOSO\John
```

This command gets a list of all the virtual machines on the local computer that user Contoso\John has access to connect to.
The example assumes that the Grant-VMConnectAccess has been run previously to grant access to Contoso\John.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts on which connect access entries are being sought.
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

### -UserName
Specifies the user or users for whom connect access entries are being sought, in one of the following forms:

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
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which connect access entries are being sought.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.VMConnectAce

## NOTES

## RELATED LINKS



