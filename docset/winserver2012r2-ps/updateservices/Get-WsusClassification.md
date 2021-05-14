---
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/updateservices/get-wsusclassification?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WsusClassification
---

# Get-WsusClassification

## SYNOPSIS
Get the list of all Windows Server Update Services (WSUS) classifications currently available in the system.

## SYNTAX

```
Get-WsusClassification [-UpdateServer <IUpdateServer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WsusClassification** cmdlet gets the list of all Windows Server Update Services (WSUS) classifications.
This list can be filtered using the Where-Objecthttp://go.microsoft.com/fwlink/?LinkID=113423 cmdlet with the results piped into the Set-WsusClassification cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusServer | Get-WsusClassification
Title                                                       ID 
-----                                                       -- 
Applications                                                5c9376ab-8ce6-464a-b136-22113dd69801 
Critical Updates                                            e6cf1350-c01b-414d-a61f-263d14d133b4 
Definition Updates                                          e0789628-ce08-4437-be74-2495b842f43b 
Drivers                                                     ebfc1fc5-71a4-4f7b-9aca-3b9a503104a0 
Feature Packs                                               b54e7d24-7add-428f-8b75-90a396fa584f 
Security Updates                                            0fa1201d-4330-4fa8-8ae9-b877473b6441 
Service Packs                                               68c5b0a3-d1a6-4553-ae49-01d3a7827828 
Tools                                                       b4832bd8-e735-4761-8daf-37f882276dab 
Update Rollups                                              28bc880e-0592-4cbf-8f95-c79b17911d5f 
Updates                                                     cd5ffd1e-e932-4e3a-bf74-18bf0b1bbd83
```

This example gets all classifications and prints them to the screen.

### EXAMPLE 2
```
PS C:\> Get-WsusServer | Get-WsusClassification | Where-Object -FilterScript {$_.Classification.Title -Eq "Drivers"}
Title                                                       ID 
-----                                                       -- 
Drivers                                                     ebfc1fc5-71a4-4f7b-9aca-3b9a503104a0
```

This example gets the classification with a title of Drivers.

## PARAMETERS

### -UpdateServer
Specifies the object that contains the WSUS server.
This value is obtained by calling the Get-WsusServer cmdlet and piping the resulting IUpdateServer object into this cmdlet.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Commands.IUpdateServer
IUpdateServer

## OUTPUTS

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Set-WsusClassification](./Set-WsusClassification.md)

