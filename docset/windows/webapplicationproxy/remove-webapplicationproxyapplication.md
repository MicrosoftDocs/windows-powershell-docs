---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: WebApplicationProxy-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-WebApplicationProxyApplication
ms.reviewer:
ms.assetid: 40B9DAF7-48F3-425F-806A-9A6A9F1566A6
---

# Remove-WebApplicationProxyApplication

## SYNOPSIS
Removes web applications published in Web Application Proxy.

## SYNTAX

### ID (Default)
```
Remove-WebApplicationProxyApplication [-ID] <Guid[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### Name
```
Remove-WebApplicationProxyApplication [-Name] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebApplicationProxyApplication** cmdlet removes web applications published in Web Application Proxy.
Specify web applications by name or by ID.
If you specify a string that contains wildcard characters, * and ?, as the name, the cmdlet removes all the web applications that match that string.

When you remove a web application, Web Application Proxy drops any current connections for that application.
The cmdlet does not uninstall the application from its backend server.

## EXAMPLES

### Example 1: Remove all published applications
```
PS C:\> Remove-WebApplicationProxyApplication
```

This command removes all of the published web applications.

### Example 2: Remove an application by using an ID
```
PS C:\> Remove-WebApplicationProxyApplication -ID 616b2e81-bada-4abc-996a-b0c806eb6f45
```

This command removes the application that has the specified ID.

### Example 3: Remove an application by using a name
```
PS C:\> Remove-WebApplicationProxyApplication -Name "ContosoApp"
```

This command removes the application named ContosoApp.

### Example 4: Remove applications that have names that contain a specified string
```
PS C:\> Remove-WebApplicationProxyApplication -Name "*Contoso*"
```

This command removes applications that have names that contain the string Contoso.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies an array of GUIDs of web applications.

```yaml
Type: Guid[]
Parameter Sets: ID
Aliases: ApplicationID

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies a friendly name for the published web application.
You can use wildcard characters.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Web Application Proxy Overview](http://technet.microsoft.com/library/dn280944.aspx)

[Publishing Internal Applications using Web Application](http://technet.microsoft.com/library/dn383650.aspx)

[Add-WebApplicationProxyApplication](./Add-WebApplicationProxyApplication.md)

[Get-WebApplicationProxyApplication](./Get-WebApplicationProxyApplication.md)

[Set-WebApplicationProxyApplication](./Set-WebApplicationProxyApplication.md)

