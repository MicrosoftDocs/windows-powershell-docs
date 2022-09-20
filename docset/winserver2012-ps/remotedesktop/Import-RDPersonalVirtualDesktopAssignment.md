---
external help file: RemoteDesktop.psm1-help.xml
Module Name: RDMgmt
online version: https://learn.microsoft.com/powershell/module/rdmgmt/import-rdpersonalvirtualdesktopassignment?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-RDPersonalVirtualDesktopAssignment

## SYNOPSIS
Imports associations between user accounts and personal virtual desktops from a text file.

## SYNTAX

```
Import-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> -Path <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-RDPersonalVirtualDesktopAssignment** cmdlet imports associations between user accounts and personal virtual desktops from a text file.

## EXAMPLES

### 1: Import a personal virtual desktop assignment
```
PS C:\>Import-RDPersonalVirtualDesktopAssignment -CollectionName "Virtual Desktop Collection" -Path "C:\Import\VirtDeskAssignReport"
```

This command imports a personal virtual desktop assignment from the file named C:\Import\VirtDeskAssignReport.

## PARAMETERS

### -CollectionName
Specifies the name of a personal virtual desktop collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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
Specifies the path and file name of a file to import.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Export-RDPersonalVirtualDesktopAssignment](./Export-RDPersonalVirtualDesktopAssignment.md)

[Get-RDPersonalVirtualDesktopAssignment](./Get-RDPersonalVirtualDesktopAssignment.md)

[Remove-RDPersonalVirtualDesktopAssignment](./Remove-RDPersonalVirtualDesktopAssignment.md)

[Set-RDPersonalVirtualDesktopAssignment](./Set-RDPersonalVirtualDesktopAssignment.md)

