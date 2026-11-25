---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamGpo.psm1-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/invoke-ipamgpoprovisioning?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-IpamGpoProvisioning
---

# Invoke-IpamGpoProvisioning

## SYNOPSIS
Creates and links group policies in the specified domain for provisioning required access settings on the servers managed by the computer running the IPAM server.

## SYNTAX

```
Invoke-IpamGpoProvisioning [-Domain] <String> [-GpoPrefixName] <String> [-IpamServerFqdn <String>]
 [-DelegatedGpoUser <String[]>] [-DelegatedGpoGroup <String[]>] [-DomainController <String>] [-PassThru]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-IpamGpoProvisioning** cmdlet creates and links three group policies specified in the **Domain** parameter for provisioning required access settings on the server roles managed by the computer running the IP Address Management (IPAM) server.
The **GpoPrefixName** parameter specified should be the same as the prefix configured in the IPAM provisioning wizard.
The three Group Policy Objects (GPOs) are created with the suffixes `_DHCP`, `_DNS`, and `_DC_NPS` appended to the **GpoPrefixName** parameter value.
These suffixes signify the three different types of access settings that are propagated by them depending on the type of server role managed by the computer running the IPAM server.

The access settings propagated by the created GPOs are required by the periodic IPAM data collection tasks which run under the Network Service account by default.
Access settings are propagated for the computer account of the computer running the IPAM server, since that is the credential presented by Network Service to access remote resources.
If required the administrator can explicitly specify the fully qualified domain name (FQDN) of the computer running the IPAM server by using the **IpamServerFqdn** parameter By default the localhost name is used as the IpamServerFqdn value, if not specified.
The cmdlet creates a universal group named IPAMUG in the domain specified by the **Domain** parameter.
If the universal group is already present, then the creation step is skipped.
This cmdlet then adds the computer account specified by the **IpamServerFqdn** to the universal group named IPAMUG.
Any access setting propagation by IPAM GPOs is done for the universal group named IPAMUG.
The cmdlet also modifies the domain wide DNS ACL to enable DNS RPC access for the universal group named IPAMUG.

By default the GPO creation is done on the PDC emulator for the specified domain.
The Domain Controller on which the GPO creation is done may be explicitly selected using the **DomainController** parameter.
The GPOs created by this cmdlet can be returned using the **PassThru** parameter.

At the time of creation of GPOs, the security filter list of IPAM GPOs is empty.
When the manageability status of a server is edited by the user in IPAM server inventory view, the computer running the IPAM server automatically adds or deletes the server into the appropriate GPO security filter list, as appropriate.
Managed servers are added to the GPO security filtering and unmanaged servers are deleted from the list.

NOTE: The cmdlet requires domain administrator privileges in order to create the GPOs.
Subsequent IPAM GPO editing privileges can be delegated to IPAM administrators who are not domain or enterprise administrators, using the **DelegatedGpoUser** and **DelegatedGpoGroup** parameters.

## EXAMPLES

### Example 1: Provision GPOs
```
PS C:\> Invoke-IpamGpoProvisioning -Domain "child.contoso.com" -GpoPrefixName "IPAM1" -Force
```

This command creates the universal group IPAMUG in the domain named child.contoso,com, if not already present, and adds the computer account of the local computer running the IPAM server to the group.
This cmdlet creates and links the following IPAM GPOs: IPAM1_DHCP, IPAM1_DNS, and IPAM1_DC_NPS in the child.contoso.com domain  to enable access for the group IPAMUG.
This cmdlet also enables DNS read access for IPAMUG using domain wide DNS ACL.
Since the domain controller is not explicitly specified, this cmdlet contacts the PDC emulator to complete the GPO operations.
This cmdlet suppresses the default confirmation text.

### Example 2: Provision a GPO by using a specific domain controller
```
PS C:\> Invoke-IpamGpoProvisioning -Domain "child.contoso.com" -GpoPrefixName "IPAM1" -DomainController "dc1.child.contoso.com" -Force
```

This command creates the universal group IPAMUG in the domain named child.contoso.com, if not already present, and adds the computer account of the local computer running the IPAM server to the group.
This cmdlet also creates and links the following IPAM GPOs: IPAM1_DHCP, IPAM1_DNS, and IPAM1_DC_NPS in the domain child.contoso.com to enable access for the group IPAMUG.
This cmdlet enables DNS read access for IPAMUG using domain-wide DNS ACL.
This cmdlet uses the domain controller named dc1.child.contoso.com as the DC to complete the GPO operations.
This cmdlet suppresses the default confirmation text.

### Example 3: Provision a GPO by using an FQDN
```
PS C:\> Invoke-IpamGpoProvisioning -Domain "child.contoso.com" -GpoPrefixName "IPAM2" -IpamServerFqdn "Ipam2.Contoso.com" -Force
```

This command creates the universal group named IPAMUG, if not already present, and adds the computer account of the specified computer running the IPAM server named ipam2.contoso.com to the group.
This cmdlet creates and links the following IPAM GPOs: IPAM2_DHCP, IPAM2_DNS, and IPAM2_DC_NPS in the domain child.contoso.com to enable access for the universal group named IPAMUG.
This cmdlet enables DNS read access for the universal group named IPAMUG using domain-wide DNS ACL.
This cmdlet suppresses the default confirmation text.

### Example 4: Provision a GPO and delegate GPO users
```
PS C:\> Invoke-IpamGpoProvisioning -Domain "child.contoso.com" -GpoPrefixName "IPAM1" -DelegatedGpoUser "NetworkAdmin1,NetworkAdmin2" -Force
```

This command creates the universal group named IPAMUG in domain child.contoso.com, if not already present, and adds the computer account of the local computer running the IPAM server to the group.
This cmdlet creates and links the following IPAM GPOs: IPAM1_DHCP, IPAM1_DNS, and IPAM1_DC_NPS in the domain child.contoso.com to enable access for the universal group named IPAMUG.
This cmdlet delegates GPO edit privileges to users NetworkAdmin1 and NetworkAdmin2.
This cmdlet enables DNS read access for the universal group named IPAMUG using domain-wide DNS ACL.
This cmdlet suppresses the default confirmation text.

### Example 5: Provision GPO and delegate a GPO group
```
PS C:\> Invoke-IpamGpoProvisioning -Domain "child.contoso.com" -GpoPrefixName "IPAM1" -DelegatedGpoGroup "IPAMAdmins" -Force
```

This command creates the universal group named IPAMUG in domain child.contoso.com, if not already present, and adds the computer account of the local computer running the IPAM server to the group.
This cmdlet creates and links the following IPAM GPOs: IPAM1_DHCP, IPAM1_DNS, and IPAM1_DC_NPS in the domain child.contoso.com to enable access for the universal group named IPAMUG.
This cmdlet delegates GPO edit privileges to the group IPAMAdmins.
This cmdlet enables DNS read access for the universal group named IPAMUG using domain-wide DNS ACL.
This cmdlet suppresses the default confirmation text.

### Example 6: Provision GPO and output the objects
```
PS C:\> Invoke-IpamGpoProvisioning -Domain "Ds2-infra.Contoso.com" -GpoPrefixName "IPAM1" -PassThru -Force
DisplayName : IPAM1_DNS
DomainName : ds2-infra.contoso.com
Owner : DS2-INFRA\Domain Admins
Id : ac9dcf5e-8581-442d-ba12-ae7569985313
GpoStatus : AllSettingsEnabled
Description :
CreationTime : 2/7/2012 1:04:18 AM
ModificationTime : 2/7/2012 1:04:28 AM
UserVersion : AD Version: 1, SysVol Version: 1
ComputerVersion : AD Version: 1, SysVol Version: 1
WmiFilter :

DisplayName : IPAM1_DC_NPS
DomainName : ds2-infra.contoso.com
Owner : DS2-INFRA\Domain Admins
Id : 5aaf16d7-9818-47c4-ade9-3860bc00c292
GpoStatus : AllSettingsEnabled
Description :
CreationTime : 2/7/2012 1:04:19 AM
ModificationTime : 2/7/2012 1:04:28 AM
UserVersion : AD Version: 1, SysVol Version: 1
ComputerVersion : AD Version: 1, SysVol Version: 1
WmiFilter :

DisplayName : IPAM1_DHCP
DomainName : ds2-infra.contoso.com
Owner : DS2-INFRA\Domain Admins
Id : 51fb3dee-0032-4d9a-8b92-84af318dcb51
GpoStatus : AllSettingsEnabled
Description :
CreationTime : 2/7/2012 1:04:20 AM
ModificationTime : 2/7/2012 1:04:28 AM
UserVersion : AD Version: 1, SysVol Version: 1
ComputerVersion : AD Version: 1, SysVol Version: 1
WmiFilter :
```

This command creates the universal group named IPAMUG in the domain child.contoso.com, if not already present, and adds the computer account of the local computer running the IPAM server to the group.
This cmdlet creates and links the following IPAM GPOs: IPAM1_DHCP, IPAM1_DNS, and IPAM1_DC_NPS in the domain Ds2-infra.Contoso.com to enable access for the universal group named IPAMUG.
This cmdlet enables DNS read access for the universal group named IPAMUG using a domain-wide DNS ACL.
This cmdlet suppresses the default confirmation text.
This cmdlet outputs the GPOs created during this operation.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelegatedGpoGroup
Specifies the comma separated list of domain groups which are delegated edit permissions on the three IPAM GPOs created by this cmdlet.
The standard GPO delegation privilege of `Edit settings, Delete, Modify Security` is enabled for these groups.
Delegation for users or groups without domain administrator privileges can also be enabled from GPMC or GPO cmdlets for the existing IPAM GPOs.
This delegation is leveraged by the computer running the IPAM server to automatically edit the GPO filter list in security context of the logged in user who is modifying the server manageability status from the IPAM server inventory view.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelegatedGpoUser
Specifies the comma separated list of domain users which are delegated edit permissions on the three IPAM GPOs created by this cmdlet.
The standard GPO delegation privilege of `Edit settings, Delete, Modify Security` is enabled for these users.
Delegation for users or groups without domain administrator privileges can also be enabled from GPMC or GPO cmdlets for the existing IPAM GPOs.
This delegation is leveraged by the computer running the IPAM server to automatically edit the GPO filter list in security context of the logged in user who is modifying the server manageability status from the IPAM server inventory view.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies the FQDN of the domain for which the IPAM GPOs are created and linked.
Specify only one domain name at a time.
This cmdlet needs to be invoked one by one for each domain in the Active Directory (AD) forest that needs to be managed by the computer running IPAM server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController
Specifies the name of the domain controller that is contacted to complete the GPO operation.
Either the FQDN or simply the host name of the domain controller can be specified.
A valid domain controller name for the specified domain must be provided.
By default, the computer running the IPAM server contacts the PDC emulator of the specified domain unless this parameter is explicitly provided.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -GpoPrefixName
Specifies the unique GPO prefix name to use when creating the group policy objects.
The GPO prefix name, such as IPAMGPO_ServerX, specified here must be same as the one specified in the IPAM provisioning wizard while selecting Group Policy based provisioning method.
The three IPAM GPOs are created with the suffixes `_DHCP`, `_DNS`, and `_DC_NPS` appended to this parameter value, such as IPAMGPO_ServerX_DHCP, IPAMGPO_ServerX_DNS, and IPAMGPO_ServerX_DC_NPS.
These suffixes signify the three different types of access settings that are propagated by them depending on the type of server role managed by the computer running the IPAM server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpamServerFqdn
Specifies the FQDN of the computer running the IPAM server for which the GPOs enables access settings.
By default, IPAM uses the FQDN of the computer running the IPAM server from where the cmdlet is running to enable access settings.
The specified computer account is added to the universal group named IPAMUG created by this cmdlet.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-IpamCustomField](./Add-IpamCustomField.md)

[Add-IpamCustomValue](./Add-IpamCustomValue.md)

[Export-IpamAddress](./Export-IpamAddress.md)

[Export-IpamRange](./Export-IpamRange.md)

[Get-IpamConfiguration](./Get-IpamConfiguration.md)

[Get-IpamCustomField](./Get-IpamCustomField.md)

[Import-IpamAddress](./Import-IpamAddress.md)

[Import-IpamRange](./Import-IpamRange.md)

[Set-IpamConfiguration](./Set-IpamConfiguration.md)

