---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/new-addccloneconfigfile?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-ADDCCloneConfigFile

## SYNOPSIS
Performs prerequisite checks for cloning a domain controller and generates a clone configuration file if all checks succeed.

## SYNTAX

### IPv4DynamicSettings (Default)
```
New-ADDCCloneConfigFile [-CloneComputerName <String>] [-IPv4DNSResolver <String[]>] [-Path <String>]
 [-SiteName <String>] [<CommonParameters>]
```

### IPv4StaticSettings
```
New-ADDCCloneConfigFile [-AlternateWINSServer <String>] [-CloneComputerName <String>] -IPv4Address <String>
 [-IPv4DefaultGateway <String>] -IPv4DNSResolver <String[]> -IPv4SubnetMask <String> [-Path <String>]
 [-PreferredWINSServer <String>] [-SiteName <String>] [-Static] [<CommonParameters>]
```

### OfflineExecution
```
New-ADDCCloneConfigFile [-AlternateWINSServer <String>] [-CloneComputerName <String>] [-IPv4Address <String>]
 [-IPv4DefaultGateway <String>] [-IPv4DNSResolver <String[]>] [-IPv4SubnetMask <String>]
 [-IPv6DNSResolver <String[]>] [-Offline] -Path <String> [-PreferredWINSServer <String>] [-SiteName <String>]
 [-Static] [<CommonParameters>]
```

### IPv6DynamicSettings
```
New-ADDCCloneConfigFile [-CloneComputerName <String>] [-IPv6DNSResolver <String[]>] [-Path <String>]
 [-SiteName <String>] [<CommonParameters>]
```

### IPv6StaticSettings
```
New-ADDCCloneConfigFile [-CloneComputerName <String>] -IPv6DNSResolver <String[]> [-Path <String>]
 [-SiteName <String>] [-Static] [<CommonParameters>]
```

## DESCRIPTION
The New-DCCloneConfigFile cmdlet performs prerequisite checks for cloning a domain controller (DC) when run locally on the DC being prepared for cloning.
This cmdlet generates a clone configuration file, DCCloneConfig.xml, at an appropriate location, if all prerequisite checks succeed.

There are two mode of operation for this cmdlet, depending on where it is executed.
When run on the domain controller that is being prepared for cloning, it will run the following pre-requisite checks to make sure this DC is adequately prepared for cloning:

(1) Is the PDC emulator FSMO role hosted on a DC running Windows Server 2012? 
(2) Is this computer authorized for DC cloning (i.e.
is the computer a member of the Cloneable Domain Controllers group)?
(3) Are all program and services listed in the output of the Get-ADDCCloningExcludedApplicationList cmdlet captured in CustomDCCloneAllowList.xml?

If these pre-requisite checks all pass, the New-DCCloneConfigFile cmdlet will generate a DCCloneConfig.xml file at a suitable location based on the parameter values supplied.
This cmdlet can also be run from a client (with RSAT) and used to generate a DCCloneConfig.xml against offline media of the DC being cloned, however, none of the pre-requisite checks will be performed in this usage mode.
This usage is intended to generate DCCloneConfig.xml files with specific configuration values for each clone on copies of the offline media.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -Static -IPv4Address "10.0.0.2" -IPv4DNSResolver "10.0.0.1" -IPv4SubnetMask "255.255.255.0" -CloneComputerName "VirtualDC2" -IPv4DefaultGateway "10.0.0.3" -PreferredWINSServer "10.0.0.1" -SiteName "REDMOND"
```

Creates a clone domain controller named VirtualDC2 with a static IPv4 address.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -Static -CloneComputerName "Clone1" -IPv6DNSResolver "FEC0:0:0:FFFF::1"
```

Creates a clone domain controller named Clone1 with a static IPv6 settings.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -AlternateWINSServer "10.0.0.3" -CloneComputerName "Clone2"-IPv4DNSResolver "10.0.0.1" -PreferredWINSServer "10.0.0.1"
```

Creates a clone domain controller named Clone2 with dynamic IPv4 settings.

### -------------------------- EXAMPLE 4 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -IPv6DNSResolver "FEC0:0:0:FFFF::1" -SiteName "REDMOND"
```

Creates a clone domain controller with dynamic IPv6 settings.

### -------------------------- EXAMPLE 5 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -Static -IPv4Address "10.0.0.2" -IPv4DNSResolver "10.0.0.1" -IPv4SubnetMask "255.255.255.0" -Static -IPv6DNSResolver "FEC0:0:0:FFFF::1" -CloneComputerName "Clone2" -PreferredWINSServer "10.0.0.1"
```

Creates a clone domain controller named Clone2 with static IPv4 and static IPv6 settings.

### -------------------------- EXAMPLE 6 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -IPv4Address "10.0.0.2" -IPv4DNSResolver "10.0.0.1" -IPv4SubnetMask "255.255.255.0" -IPv4DefaultGateway "10.0.0.3" -IPv6DNSResolver "FEC0:0:0:FFFF::1"
```

Creates a clone domain controller named Clone2 with static IPv4 and dynamic IPv6 settings.

### -------------------------- EXAMPLE 7 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -Static -IPv6DNSResolver "FEC0:0:0:FFFF::1" -CloneComputerName "Clone1" -PreferredWINSServer "10.0.0.1" -SiteName "REDMOND"
```

Creates a clone domain controller named Clone1 with dynamic IPv4 and static IPv6 settings.

### -------------------------- EXAMPLE 8 --------------------------
```
PS C:\>New-ADDCCloneConfigFile -IPv4DNSResolver "10.0.0.1" -IPv6DNSResolver "FEC0:0:0:FFFF::1"
```

Creates a clone domain controller with dynamic IPv4 and dynamic IPv6 settings.

### -------------------------- EXAMPLE 9 --------------------------
```
PS C:\>New-DCCloneConfig -Offline -CloneComputerName CloneDC1 -SiteName REDMOND -Path F:\Windows\NTDS -Force
```

Creates a clone domain controller named CloneDC1 in offline mode, in a site called "REDMOND" with a dynamic IPv4 address.
This command also uses the -Force parameter to force overwrite of any previous DCCloneConfig.xml file created at the specified path (F:\Windows\NTDS).

## PARAMETERS

### -AlternateWINSServer
Specifies the name of the alternate Windows Internet Naming Service (WINS) server for the cloned DC to use if the preferred WINS Server is not available.

```yaml
Type: String
Parameter Sets: IPv4StaticSettings, OfflineExecution
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloneComputerName
Specifies the computer name for the cloned DC.
If this parameter is not specified as a unique name within the enterprise of 15 characters or less, the following formula is used to programmatically generate a name:

(1) The first 8 characters of the source DC computer name.
For example, a source computer name of "SourceComputer" is truncated to a prefix string of "SourceCo".
(2) A unique naming suffix of the format "**-CL**nnnn" is appended to the prefix string where nnnn is the next available value from 0001-9999 that the PDC determines is not currently in use.
For example, if 0047 is the next available number within the allowed range, using the above source computer prefix of "SourceCo" the derived name to use for the clone computer will be SourceCo-CL0047.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Address
Specifies the Internet Protocol version 4 (IPv4) address to be assigned to the cloned DC.

```yaml
Type: String
Parameter Sets: IPv4StaticSettings
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: OfflineExecution
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4DNSResolver
Specifies the Internet Protocol version 4 (IPv4) address for the DNS server to be used by the cloned DC to resolve names.
A maximum of 4 string values can be provided.

```yaml
Type: String[]
Parameter Sets: IPv4DynamicSettings, OfflineExecution
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: IPv4StaticSettings
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4DefaultGateway
Specifies the Internet Protocol version 4 (IPv4) address for the default gateway to be used by the cloned DC.

```yaml
Type: String
Parameter Sets: IPv4StaticSettings, OfflineExecution
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4SubnetMask
Specifies the Internet Protocol version 4 (IPv4) subnet mask to use for the subnet where the cloned DC is to be located.

```yaml
Type: String
Parameter Sets: IPv4StaticSettings
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: OfflineExecution
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6DNSResolver
Specifies the Internet Protocol version 6 (IPv6) address for the DNS server to be used by the cloned DC to resolve names.

```yaml
Type: String[]
Parameter Sets: OfflineExecution, IPv6DynamicSettings
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: IPv6StaticSettings
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Offline
Indicates whether the cmdlet is being run against an offline media or on the DC being prepared for cloning.

```yaml
Type: SwitchParameter
Parameter Sets: OfflineExecution
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the folder path to use when writing the clone configuration file.
If the cmdlet is run and all prerequisite checks succeed, a DCCloneConfig.xml file will be written and appear in this location as output.
The **Path** parameter is optional when running the cmdlet on the DC being prepared for cloning.
In this case, the default location of the DIT folder will be used and this parameter does not need to be specified.
When running the New-DCCLoneConfigFile cmdlet in offline mode (i.e.
when the **Offline** parameter is specified), however, the **Path** parameter is required.

```yaml
Type: String
Parameter Sets: IPv4DynamicSettings, IPv4StaticSettings, IPv6DynamicSettings, IPv6StaticSettings
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: OfflineExecution
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredWINSServer
Specifies the name of the primary Windows Internet Naming Service (WINS) server to use as the preferred WINS Server for the cloned DC.

```yaml
Type: String
Parameter Sets: IPv4StaticSettings, OfflineExecution
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteName
Specifies the name of the Active Directory site in which to place the cloned DC.

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

### -Static
Indicates whether the TCP/IP configuration specified for the cloned DC is static or dynamic IP configuration.

```yaml
Type: SwitchParameter
Parameter Sets: IPv4StaticSettings, IPv6StaticSettings
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: OfflineExecution
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

### None

## NOTES

## RELATED LINKS

[Get-ADDCCloningExcludedApplicationList](./Get-ADDCCloningExcludedApplicationList.md)

