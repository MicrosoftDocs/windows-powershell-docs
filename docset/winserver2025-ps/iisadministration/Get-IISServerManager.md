---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iisservermanager?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISServerManager
---

# Get-IISServerManager

## SYNOPSIS
Gets the IISAdministration view of IIS ServerManager.

## SYNTAX

```
Get-IISServerManager [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISServerManager** cmdlet gets Internet Information Services (IIS) server manager object from Microsoft.Web.Administration.

## EXAMPLES

### Example 1: Get an active Microsoft.Web.Administration.ServerManager object
```
PS C:\> $SM = Get-IISServerManager
```

This command gets the active Microsoft.Web.Administration.ServerManager object and stores the result into the variable $SM.

### Example 2: Use the ServerManager object to get site objects and list IIS Web sites
```
PS C:\> $SM = Get-IISServerManager
PS C:\> $Sites = $SM.Sites
PS C:\> $Sites
Name             ID   State      Physical Path                  Bindings
----             --   -----      -------------                  --------
Default Web Site 1    Stopped    %SystemDrive%\inetpub\wwwroot  http *:80:
Patti            2    Started    C:\inetpub\Patti               http *:8080:
                                                                http *:8033:

FTPSite          3               C:\inetpub\ftproot             ftp *:21:
DavidChe         4    Started    c:\                            http *:8088:
MyNewSite        6555 Started    C:\inetpub\wwwroot             http *:8099:
                                                                http *:8022:
TestSite         5    Stopped    C:\inetpub\testsite            http *:8080:
```

This command gets site objects and lists all IIS web sites by using the ServerManager object.

### Example 3: Use the ServerManager object to get application pool objects and recycle an application pool.
```
PS C:\> $SM = Get-IISServerManager
PS C:\> $SM.ApplicationPools["PattiFul"].Recycle()
```

This command uses the ServerManager object to get application pool objects and then recycles an application pool.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

