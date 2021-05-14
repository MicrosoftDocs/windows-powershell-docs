---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-addccloningexcludedapplicationlist?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADDCCloningExcludedApplicationList

## SYNOPSIS
Returns the list of installed programs and services present on this domain controller that are not in the default or user defined inclusion list.

## SYNTAX

### Default (Default)
```
Get-ADDCCloningExcludedApplicationList [<CommonParameters>]
```

### Xml
```
Get-ADDCCloningExcludedApplicationList [-Force] [-GenerateXml] [-Path <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADDCCloningExcludedApplicationList cmdlet searches the local domain controller for programs and services in the installed programs database, the services control manager that are not specified in the default and user defined inclusion list.
The applications in the resulting list can be added to the user defined exclusion list if they are determined to support cloning.
If the applications are not cloneable, they should be removed from the source domain controller before the clone media is created.
Any application that appears in cmdlet output and is not included in the user defined inclusion list will force cloning to fail.

Once you have granted a source virtualized DC permissions to be cloned, the Get-ADDCCloningExcludedApplicationList cmdlet should be run a first time with no additional parameters on the source virtualized domain controller to identify all programs or services that are to be evaluated for cloning.
Next, vet the returned list with your software vendors and remove any applications from the list that cannot be safely cloned.
Finally, you can run the Get-ADDCCloningExcludedApplicationList cmdlet again using the **-GenerateXml** parameter set to create the CustomDCCloneAllowList.xml file.

The Get-ADDCCloningExcludedApplicationList cmdlet needs to be run before the New-ADDCCloneConfigFile cmdlet is used because if the New-ADDCCloneConfigFile cmdlet detects an excluded application, it will not create a DCCloneConfig.xml file.
For more information on virtual domain controller cloning, see the guidance on AD DS virtualization at http://go.microsoft.com/fwlink/?LinkId=208030http://go.microsoft.com/fwlink/?LinkId=208030.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADDCCloningExcludedApplicationList
```

Description

-----------

Displays the excluded application list to the console.
If there is already a CustomDCCloneAllowList.xml, this cmdlet displays the delta of that list compared to the operating system (which may be nothing if the lists match).

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDCCloningExcludedApplicationList -GenerateXml -Path C:\Windows\NTDS -Force
```

Description

-----------

Generates the excluded application list as a file named CustomDCCloneAllowList.xml at the specified folder path (C:\Windows\NTDS) and forces overwrite if a file by that name is found to already exist at that path location.

## PARAMETERS

### -Force
Forces an overwrite of an existing CustomDCCloneAllowList.xml file if one is found to exist at the folder path specified in the -Path parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Xml
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateXml
Creates the CustomDCCloneAllowList.xml file and writes it in the location specified using the -Path parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Xml
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
The folder path to use when creating the CustomDCCloneAllowList.xml file using the -GenerateXml switch parameter.

```yaml
Type: String
Parameter Sets: Xml
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

### ADEntity

## NOTES

## RELATED LINKS

