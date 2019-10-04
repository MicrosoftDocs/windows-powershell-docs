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
title: Get-WebApplicationProxyApplication
ms.reviewer:
ms.assetid: 99D86A99-E40A-45E1-B048-06172CB73BE7
---

# Get-WebApplicationProxyApplication

## SYNOPSIS
Gets published web applications.

## SYNTAX

### ID
```
Get-WebApplicationProxyApplication -ID <Guid> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### Name
```
Get-WebApplicationProxyApplication [[-Name] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebApplicationProxyApplication** cmdlet gets objects that represent published web applications.
You can specify the ID of an application, or specify the name of an application, including a name that includes the wildcard characters * or ?.
If you do not specify name or ID, the cmdlet gets all the published applications.
If more than one application is found, then the cmdlet outputs a list of the applications.
If only one application is found, then the cmdlet displays properties of the application.

## EXAMPLES

### Example 1: Get all published applications
```
PS C:\> Get-WebApplicationProxyApplication
```

This command all of the published applications, and displays information about them.

### Example 2: Get an application by using an ID
```
PS C:\> Get-WebApplicationProxyApplication -ID 616b2e81-bada-4abc-996a-b0c806eb6f45
```

This command gets the application that has the specified ID.

### Example 3: Get an application by using a name
```
PS C:\> Get-WebApplicationProxyApplication -Name "ContosoApp"
```

This command gets the application named ContosoApp.

### Example 4: Get applications that have names that end in a specified string
```
PS C:\> Get-WebApplicationProxyApplication -Name "*Contoso"
```

This command gets applications that have names that end with the string Contoso.

### Example 5: Show the full details of a published application
```
PS C:\> Get-WebApplicationProxyApplication *Contoso | Format-List
```

This command shows the full details of applications that have names that end with the string Contoso.

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
Specifies the GUID of a web application.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a friendly name for the published web application.
You can use wildcard characters.

```yaml
Type: String
Parameter Sets: Name
Aliases: FriendlyName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#PublishedWebApp[]
If the cmdlet finds more than one application, it displays a list of the applications.
If the cmdlet gets a single application, it displays the properties of the application.

## NOTES

## RELATED LINKS

[Web Application Proxy Overview](http://technet.microsoft.com/library/dn280944.aspx)

[Publishing Internal Applications using Web Application Proxy](http://technet.microsoft.com/library/dn383650.aspx)

[Add-WebApplicationProxyApplication](./Add-WebApplicationProxyApplication.md)

[Remove-WebApplicationProxyApplication](./Remove-WebApplicationProxyApplication.md)

[Set-WebApplicationProxyApplication](./Set-WebApplicationProxyApplication.md)

