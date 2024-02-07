---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/get-gporeport?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-GPOReport
---

# Get-GPOReport

## SYNOPSIS

Generates a report either in XML or HTML format for a specified GPO or for all GPOs in a domain.

## SYNTAX

### ByGUID (Default)

```
Get-GPOReport [-Guid] <Guid> [-ReportType] <ReportType> [[-Path] <String>] [[-Domain] <String>]
 [[-Server] <String>] [<CommonParameters>]
```

### ByName

```
Get-GPOReport [-Name] <String> [-ReportType] <ReportType> [[-Path] <String>] [[-Domain] <String>]
 [[-Server] <String>] [<CommonParameters>]
```

### ReportAll

```
Get-GPOReport [-ReportType] <ReportType> [[-Path] <String>] [[-Domain] <String>]
 [[-Server] <String>] [-All] [<CommonParameters>]
```

## DESCRIPTION

The `Get-GPOReport` cmdlet generates a report in either XML or HTML format that describes
properties and policy settings for a specified Group Policy Object (GPO) or for all GPOs in a
domain. The information that is reported for each GPO includes: details, links, security filtering,
Windows Management Instrumentation (WMI) filtering, delegation, and computer and user
configurations.

You can specify the **All** parameter to generate a report for every GPO in the domain, or you can
specify either the **Name** or **Guid** parameter to generate a report for a single GPO. You can
also pipe GPO objects into this cmdlet. If you specify a file through the **Path** parameter, the
report is written to a file; otherwise, it is printed to the display.

## EXAMPLES

### Example 1: Generate an HTML report for the specified GPO

```powershell
Get-GPOReport -Name "TestGPO1" -ReportType HTML -Path "C:\GPOReports\GPOReport1.html"
```

This command generates a report in HTML format for the GPO `TestGPO1` and writes it to the file `C:\GPOReports\GPOReport1.html`

### Example 2: Generate an XML report for each GPO in the specified domain

```powershell
$params = @{
    All         = $true
    Domain      = 'sales.contoso.com'
    Server      = 'DC1'
    ReportType  = 'XML' 
    Path        = 'C:\GPOReports\GPOReportsAll.xml'
}
Get-GPOReport @params
```

This command generates a report in XML format for each GPO in the `sales.contoso.com` domain and
writes it to the file `C:\GPOReports\GPOReportsAll.xml`. The `DC1` domain controller is contacted to
complete the operation.

If the domain of the user account (or, for startup and shutdown scripts, the computer account) is
different from `sales.contoso2.com`, a trust must exist between the two domains.

### Example 3: Generate an XML report for a GPO with the specified GUID

```powershell
Get-GPOReport -GUID 73624cc9-e8f2-4f05-8802-193fae8773ce -ReportType XML
```

This command generates a report in XML format for the GPO with the specified GUID.
Because no **Path** parameter is supplied, the report is written to the display.

## PARAMETERS

### -All

Indicates that the cmdlet generates a report for all GPOs in the domain.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ReportAll
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Get-GPOReport` cmdlet:

- If a single GPO is specified, it must exist in this domain.

- If the **All** parameter is specified, a report is generated for each GPO in this domain.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session or, (for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user or the computer.

You can also refer to Domain by its built-in alias, **DomainName**. For more information, see
[about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid

Specifies the GPO for which to generate the report by its globally unique identifier (GUID). The
GUID uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases)

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO for which to generate the report by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely identify a
GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path

Specifies the path to the report file; for instance, `c:\Reports\GpoReport.xml`.
If no path is specified, the report is printed to the display.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportType

Specifies the format of the report.
You must specify either Html (for HTML format) or Xml (for XML format).
These values are not case sensitive.

The following values are permitted for this object type.

```yaml
Type: ReportType
Parameter Sets: (All)
Aliases: 
Accepted values: Xml, Html

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

You can refer to this parameter by its built-in alias, **DC**. For more information, see
[about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DC

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.Gpo

An object that represents a GPO.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### None

This cmdlet does not generate any output.

## NOTES

* You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For instance, the domain of the user who started the session by opening Windows
  PowerShell from the Program Files menu, or the domain of a user that is specified in a runas
  command. However, computer startup and shutdown scripts run under the context of the LocalSystem
  account. The LocalSystem account is a built-in local account, and it accesses network resources
  under the context of the computer account. Therefore, when this cmdlet is run from a startup or
  shutdown script, the default domain is the domain to which the computer is joined.

  Only one domain can be used by an instance of this cmdlet. If you pipe a collection of GPO
  (Microsoft.GroupPolicy.Gpo) objects to this cmdlet, the **DomainName** property of the first GPO
  object in the collection specifies the domain for the cmdlet. This is because domainname is a
  built-in alias for the **Domain** parameter, and the **Domain** parameter can take its value by
  property name from the pipeline. A non-terminating error occurs for any GPOs in the collection
  that are not in this domain. If this domain is different from the domain of the user account, for
  startup or shutdown scripts, the computer account, a trust must exist between the two domains.

## RELATED LINKS
