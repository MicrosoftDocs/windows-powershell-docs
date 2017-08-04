---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-CimSession
ms.assetid: 9CAA4D18-6E40-416C-A679-7D1DE47C28ED
---

# Get-CimSession

## SYNOPSIS
Gets the CIM session objects from the current session.

## SYNTAX

### ComputerNameSet (Default)
```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### SessionIdSet
```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### InstanceIdSet
```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### NameSet
```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-CimSession** cmdlet gets the Common Information Model (CIM) session objects created in the current Windows PowerShell® session.

If used without any parameters, the cmdlet gets all of the CIM sessions created in the current Windows PowerShell session.
You can use the parameters of **Get-CimSession** to get the sessions that are for particular computers, or you can identify sessions by their names, IDs, or instance IDs.

For more information about Windows PowerShell sessions, see about_CimSessions.

## EXAMPLES

### Example 1: Get CIM sessions from the current Windows PowerShell session
```
PS C:\> New-CimSession -ComputerName "Server01,Server02"
PS C:\> Get-CimSession

Id           : 1 
Name         : CimSession1 
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59 
ComputerName : Server01 
Protocol     : WSMAN 
Id           : 2 

Name         : CimSession2 

InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710 

ComputerName : Server02 

Protocol     : WSMAN
```

This command first creates CIM sessions by using New-CimSession, and then gets the CIM sessions by using **Get-CimSession**.

By default, **Get-CimSession** only gets information about the CIM sessions that exist in the current Windows PowerShell session.
**Get-CimSession** does not get CIM sessions that were created in other Windows PowerShell sessions or that were created on other computers.

### Example 2: Get the CIM sessions from a specific computer
```
PS C:\> Get-CimSession -ComputerName "Server02"

Id           : 2 

Name         : CimSession2 

InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710 

ComputerName : Server02 

Protocol     : WSMAN
```

This command gets the CIM sessions that are connected to the computer named Server02.

### Example 3: Get a list of CIM sessions and then format the list
```
PS C:\> Get-CimSession | Format-Table -Property ComputerName,InstanceID
```

This command gets all of the CIM sessions in the current Windows PowerShell session, and then formats the list in a table containing only the *ComputerName* and *InstanceID* parameters.

### Example 4: Get all CIM sessions that have specific names
```
PS C:\> Get-CimSession -ComputerName "Serv*"

Id           : 1 

Name         : CimSession1 

InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59 

ComputerName : Server01 

Protocol     : WSMAN 
Id           : 2 

Name         : CimSession2 

InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710 

ComputerName : Server02 

Protocol     : WSMAN
```

This command gets all of the CIM sessions that have names that begin with the characters serv.

### Example 5: Get a specific CIM session
```
PS C:\> Get-CimSession -ID 2
```

This command gets the CIM session that has an ID of 2.

## PARAMETERS

### -ComputerName
Specifies the name of the computer from which to get CIM sessions.
Wildcard characters are permitted.

```yaml
Type: String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Specifies the identifier (ID) of the CIM session to get.
For multiple IDs, use commas to separate the IDs, or use the range operator (..) to specify a range of IDs.

An ID is an integer that uniquely identifies the CIM session in the current Windows PowerShell session.
It is easier to remember and type than *InstanceId*, but it is unique only within the current Windows PowerShell session.

For more information about the range operator, see [about_Operators](http://go.microsoft.com/fwlink/p/?LinkId=113242).

```yaml
Type: UInt32[]
Parameter Sets: SessionIdSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId
Specifies the instance IDs of the CIM session to get.

*InstanceID* is a GUID that uniquely identifies a CIM session.
The *InstanceID* is unique, even when you have multiple sessions running in Windows PowerShell.

The *InstanceID* is stored in the InstanceID property of the object that represents a CIM session.

```yaml
Type: Guid[]
Parameter Sets: InstanceIdSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Gets one or more CIM sessions which contain the specified friendly names.
Wildcard characters are permitted.

```yaml
Type: String[]
Parameter Sets: NameSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimSession

## NOTES

## RELATED LINKS

[New-CimSession](./New-CimSession.md)

[Remove-CimSession](./Remove-CimSession.md)

