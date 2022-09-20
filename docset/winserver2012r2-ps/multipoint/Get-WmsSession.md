---
external help file: WmsCmdlets.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/06/2017
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmssession?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsSession
---

# Get-WmsSession

## SYNOPSIS
Returns session information.

## SYNTAX

```
Get-WmsSession [-SerializeString] [-Id <UInt32>] [-TimeoutInSecond <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Get-WmsSession cmdlet returns session information for the specified session.
If no session is specified, it returns session information for all sessions.

## EXAMPLES

### Example
```
PS C:\> get-WmsSession
Id           : 2


State        : RemoteConnection


IsAdmin      : True


UserName     : Test


StationId    : 0


ComputerName : Test1


ClientName   : Test2


DomainName   : TestDomain


IsRail       : False



Id           : 3


State        : ConnectedToStation


IsAdmin      : True


UserName     : Administrator


StationId    : 1


ComputerName : Test1


ClientName   : Test1


DomainName   : TestDomain


IsRail       : False
```

Sample output with 2 sessions. 

 Session ID #2 is a remote session and Session ID #1 is a session connected to a local Windows MultiPoint Server station.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Id
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerializeString
Returns data in XML format.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
Returns WmsSession collection as PSObject collection.

## NOTES

## RELATED LINKS

