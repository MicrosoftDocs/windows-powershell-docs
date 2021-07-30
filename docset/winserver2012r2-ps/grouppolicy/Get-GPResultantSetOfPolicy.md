---
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/grouppolicy/get-gpresultantsetofpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-GPResultantSetOfPolicy
---

# Get-GPResultantSetOfPolicy

## SYNOPSIS
Outputs the Resultant Set of Policy (RSoP) information for a user, a computer, or both to a file.

## SYNTAX

```
Get-GPResultantSetOfPolicy [-Computer <String>] [-User <String>] -ReportType <ReportType> -Path <String>
 [<CommonParameters>]
```

## DESCRIPTION
The Get-GPResultantSetOfPolicy cmdlet outputs the Resultant Set of Policy (RSoP) information for a user, a computer, or both to a file.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> get-GPResultantSetOfPolicy -reporttype xml -path c:\reports\LocalUserAndComputerReport.xml 

RsopMode        : Logging 
Namespace       : \\COMPUTER-02-PC\Root\Rsop\NS2BBE3F29_794F_4EAE_B9DB_0A2310622534 
LoggingComputer : COMPUTER-02 
LoggingUser     : CONTOSO\someuser 
LoggingMode     : UserAndComputer
```

Description

-----------

This command generates a report for the user (CONTOSO\someuser) that is running the session and the computer (COMPUTER-02) on which the session is running.
The report is generated in XML format, and is written to the specified file.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Get-GPResultantSetOfPolicy -reporttype xml -computer computer-08.contso.com -path c:\reports\computer-08.xml 

RsopMode        : Logging 
Namespace       : \\computer-08.contoso.com\Root\Rsop\NS643B2E66_8F54_4407_A813_7D47173B0922 
LoggingComputer : computer-08.contoso.com 
LoggingUser     : CONTOSO\Administrator 
LoggingMode     : Computer
```

Description

-----------

This command generates a report for the specified computer.
The computer is specified by its fully qualified domain name (FQDN), computer-08.contoso.com.
The report is generated in XML format, and is written to the specified file.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\> Get-GPResultantSetOfPolicy -user contoso\someuser -reporttype html -path c:\reports\UserReport.html 

RsopMode        : Logging 
Namespace       : \\COMPUTER-02\Root\Rsop\NS78355E76_C754_41B5_8F5E_B61551837A62 
LoggingComputer : COMPUTER-02 
LoggingUser     : contoso\someuser 
LoggingMode     : User
```

Description

-----------

This command generates a report for the specified user (contoso\someuser) in HTML format and saves it to the specified file.

### -------------------------- EXAMPLE 4 --------------------------
```
PS C:\> Get-GPResultantSetOfPolicy -user someuser -computer contoso.com\computer-08 -reporttype html -path c:\reports\UserAndComputerReport.html 

RsopMode        : Logging 
Namespace       : \\computer-08\Root\Rsop\NS72116C25_6570_4586_9B79_FC4F71372E57 
LoggingComputer : contoso.com\computer-08 
LoggingUser     : someuser 
LoggingMode     : UserAndComputer
```

Description

-----------

This command generates a report for the specified computer (contoso.com\computer-08) and user (someuser) in HTML format and saves it to the specified file.

## PARAMETERS

### -Computer
Specifies the name of the computer for which to generate the report.
You can specify the computer name in one of the following formats:

- Full computer name (FQDN computer name); for example, computer-01.sales.contoso.com.

- Fully qualified domain name (FQDN)\computer name; for example, sales.contoso.com\computer-01.

- NetBIOS domain name\computer name; for example, sales\computer-01.

- Computer name (host name): for example, computer-01.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to the report file; for example, c:\Reports\GpRsopReport.xml.

You can also refer to the Path parameter by its built-in alias, "filepath".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportType
Specifies the format of the RSoP report.
You must specify either Html (for HTML format) or Xml (for XML format).
These values are not case sensitive.

The following values are permitted for this object type.

```yaml
Type: ReportType
Parameter Sets: (All)
Aliases: 
Accepted values: Xml, Html

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies the user name of the user for which to generate the report.
You can specify the user name in one of the following formats:

- Fully qualified domain name (FQDN)\user name; for example, sales.contoso.com\someuser.

- NetBIOS domain name\user name; for example, sales\someuser.

- User name: for example, someuser.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet does not take any object as input.

## OUTPUTS

### Microsoft.GroupPolicy.GPRsop
Get-GPResultantSetOfPolicy returns an RSoP object.

## NOTES
* The Get-GPResultantSetOfPolicy cmdlet provides only the logging results for a specified computer and user. You must use the GPMC to generate RSoP modeling information.

## RELATED LINKS

