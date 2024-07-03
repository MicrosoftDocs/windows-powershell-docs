---
title: about_ActiveDirectory_ObjectModel
ms.date: 04/22/2013
description: Describes the object model of the Active Directory module for Windows PowerShell.
Locale: en-US
schema: 2.0.0
---

# about_ActiveDirectory_ObjectModel

## SHORT DESCRIPTION
Describes the object model of the Active Directory module for Windows
PowerShell.

## LONG DESCRIPTION

This topic explains the Active Directory module classes and their properties
used to model actual Active Directory attributes. It also outlines the class
hierarchy constructed from its Active Directory counterpart. The object model
establishes a data foundation for all the operations supported by Active
Directory module cmdlets.

### Class Hierarchy

The following list shows the class hierarchy defined in the Active Directory
module object model, with class inheritance implied by indentation. This
inheritance model allows for Active Directory cmdlets to accept a range of
object types as input. This means, for example, that the cmdlet
Get-ADPrincipalGroupMembership can accept as input any of the following
objects: ADGroup, ADAccount, ADComputer, ADServiceAccount or ADUser. This works
because of the inheritance model and guarantees that an ADUser object has all
of the properties of an ADPrincipal object.

```
ADEntity
  ADRootDSE
  ADObject
    ADFineGrainedPasswordPolicy
    ADOptionalFeature
    ADOrganizationalUnit
    ADPartition
      ADDomain
    ADPrincipal
      ADAccount
        ADComputer
        ADServiceAccount
        ADUser
      ADGroup
  ADDefaultDomainPasswordPolicy
  ADForest
  ADDirectoryServer
    ADDomainController
```

### Active Directory Module Classes

The following listing shows every Active Directory module class from the class
hierarchy listing. Each class defines a set of properties, some of which are
LDAP attributes that are retrieved by default and some are new properties
created specifically for the Active Directory module. These new properties are
derived from one or more LDAP attributes as outlined in the class listings.


- ADEntity - The base level class from which all other classes are derived.
  - ADRootDSE - Represents the rootDSE and is derived from ADEntity. An
    ADRootDSE may contain the following properties in addition to those
    inherited from its parent.
    - ConfigurationNamingContext - A property of type System.String, derived
      from the directory attribute ConfigurationNamingContext
    - CurrentTime - A property of type System.DateTime, derived from the
      directory attribute CurrentTime
    - DefaultNamingContext - A property of type System.String, derived from the
      directory attribute DefaultNamingContext
    - DnsHostName - A property of type System.String, derived from the
      directory attribute DnsHostName
    - DomainControllerFunctionality - A property of type
      ADDomainControllerMode, derived from the directory attribute
      DomainControllerFunctionality
    - DomainFunctionality - A property of type ADDomainMode, derived from the
      directory attribute DomainFunctionality
    - DsServiceName - A property of type System.String, derived from the
      directory attribute DsServiceName
    - ForestFunctionality - A property of type ADForestMode, derived from the
      directory attribute ForestFunctionality
    - GlobalCatalogReady - A property of type System.Boolean, derived from the
      directory attribute GlobalCatalogReady
    - HighestCommittedUSN - A property of type System.Long, derived from the
      directory attribute HighestCommittedUSN
    - LdapServiceName - A property of type System.String, derived from the
      directory attribute LdapServiceName
    - NamingContexts - A property of type System.String, derived from the
      directory attribute NamingContexts
    - RootDomainNamingContext - A property of type System.String, derived from
      the directory attribute RootDomainNamingContext
    - SchemaNamingContext - A property of type System.String, derived from the
      directory attribute SchemaNamingContext
    - ServerName - A property of type System.String, derived from the directory
      attribute ServerName
    - SubschemaSubentry - A property of type ADObject, derived from the
      directory attribute SubschemaSubentry
    - SupportedCapabilities - A property of type ADObjectIdentifier, derived
      from the directory attribute SupportedCapabilities
    - SupportedControl - A property of type ADObjectIdentifier, derived from
      the directory attribute SupportedControl
    - SupportedLDAPPolicies - A property of type System.String, derived from
      the directory attribute SupportedLDAPPolicies
    - SupportedLDAPVersion - A property of type System.Int, derived from the
      directory attribute SupportedLDAPVersion
    - SupportedRootDSEOperations - A property of type
      ADPropertyValueCollection, derived from the directory attribute
      SupportedRootDSEOperations
    - SupportedSASLMechanisms - A property of type System.String, derived from
      the directory attribute SupportedSASLMechanisms
    - Syncronized - A property of type System.Boolean, derived from the
      directory attribute IsSynchronized.
  - ADObject - Represents any object in Active Directory and is derived from
    ADEntity. An ADObject may contain the following properties in addition to
    those inherited from its parent.
    - CanonicalName - A property of type System.String, derived from the
      directory attribute: canonicalName
    - CN - A property of type System.String, derived from the directory
      attribute: cn
    - Created - A property of type System.DateTime, derived from the directory
      attribute: createTimeStamp
    - Deleted - A property of type System.Boolean, derived from the directory
      attribute: isDeleted
    - Description - A property of type System.String, derived from the
      directory attribute: description
    - DisplayName - A property of type System.String, derived from the
      directory attribute: displayName
    - DistinguishedName - A property of type System.String, derived from the
      directory attribute: distinguishedName
    - LastKnownParent - A property of type System.String, derived from the
      directory attribute: lastKnownParent
    - Modified - A property of type System.DateTime, derived from the directory
      attribute: modifyTimeStamp
    - Name - A property of type System.String, derived from the directory
      attribute: name
    - ObjectCategory - A property of type System.String, derived from the
      directory attribute: objectCategory
    - ObjectClass - A property of type System.String, derived from the
      directory attribute: objectClass
    - ObjectGUID - A property of type System.Guid, derived from the directory
      attribute: objectGUID
    - ProtectedFromAccidentalDeletion - A property of type System.Boolean,
      derived from the directory attributes: nTSecurityDescriptor,
      sdRightsEffective, instanceType, isDeleted
    - ADFineGrainedPasswordPolicy Represents a fine grained password policy
      object; that is, an AD object of type msDS-PasswordSettings in AD DS and
      is derived from ADObject. This class is not supported by AD LDS. An
      ADFineGrainedPasswordPolicy may contain the following properties in
      addition to those inherited from its parent.
      - AppliesTo - A property of type System.String, derived from the
        directory attribute: msDS-PSOAppliesTo
      - ComplexityEnabled - A property of type System.Boolean, derived from the
        directory attribute: msDS-PasswordComplexityEnabled
      - LockoutDuration - A property of type System.TimeSpan, derived from the
        directory attribute: msDS-LockoutDuration
      - LockoutObservationWindow - A property of type System.TimeSpan, derived
        from the directory attribute: msDS-LockoutObservationWindow
      - LockoutThreshold - A property of type System.Int32, derived from the
        directory attribute: msDS-LockoutThreshold
      - MaxPasswordAge - A property of type System.TimeSpan, derived from the
        directory attribute: msDS-MaximumPasswordAge
      - MinPasswordAge - A property of type System.TimeSpan, derived from the
        directory attribute: msDS-MinimumPasswordAge
      - MinPasswordLength - A property of type System.Int32, derived from the
        directory attribute: msDS-MinimumPasswordLength
      - PasswordHistoryCount - A property of type System.Int32, derived from
        the directory attribute: msDS-PasswordHistoryLength
      - Precedence - A property of type System.Int32, derived from the
        directory attribute: msDS-PasswordSettingsPrecedence
      - ReversibleEncryptionEnabled - A property of type System.Boolean,
        derived from the directory attribute:
        msDS-PasswordReversibleEncryptionEnabled
    - ADOptionalFeature Represents an optional feature, an Active Directory
      object of type msDS-OptionalFeature, and is derived from ADObject. An
      ADOptionalFeaturemay contain the following properties in addition to
      those inherited from its parent.
      - EnabledScopes - A property of type System.String, derived from the
        directory attribute: msDS-EnabledFeatureBL
      - FeatureGUID - A property of type System.Guid, derived from the
        directory attribute: msDS-OptionalFeatureGUID
      - FeatureScope - A property of type System.Int32, derived from the
        directory attribute: msDS-OptionalFeatureFlags
      - IsDisableable - A property of type System.Boolean, derived from the
        directory attribute: msDS-OptionalFeatureFlags
      - RequiredDomainMode - A property of type
        Microsoft.ActiveDirectory.Management.ADDomainMode, derived from the
        directory attribute: msDS-RequiredDomainBehaviorVersion
      - RequiredForestMode - A property of type
        Microsoft.ActiveDirectory.Management.ADForestMode, derived from the
        directory attribute: msDS-RequiredForestBehaviorVersion
    - ADOrganizationalUnit Represents an organizationalUnit (OU) object and is
      derived from ADObject. An ADOrganizationalUnit may contain the following
      properties in addition to those inherited from its parent.
      - City - A property of type System.String, derived from the directory
        attribute: l
      - Country - A property of type System.String, derived from the directory
        attribute: c
      - LinkedGroupPolicyObjects - A property of type System.String, derived
        from the directory attribute: gpLink. This property is not supported on
        AD LDS.
      - ManagedBy - A property of type System.String, derived from the
        directory attribute: managedBy
      - PostalCode - A property of type System.String, derived from the
        directory attribute: postalCode
      - State - A property of type System.String, derived from the directory
        attribute: st
      - StreetAddress - A property of type System.String, derived from the
        directory attribute: street
    - ADPartition - Represents a naming context, Configuration, Schema, Domain
      or Application Partition(ND NC) and is derived from ADObject. This class
      is not supported by AD LDS. An ADPartition may contain the following
      properties in addition to those inherited from its parent.
      - DeletedObjectsContainer - A property of type System.String, derived
        from the directory attribute: DeletedObjectsContainer
      - DNSRoot - A property of type System.String, derived from the directory
        attribute: DNSRoot
      - LostAndFoundContainer - A property of type System.String, derived from
        the directory attribute: LostAndFoundContainer
      - QuotasContainer - A property of type System.String, derived from the
        directory attribute: QuotasContainer
      - ReadOnlyReplicaDirectoryServers - A property of type System.String,
        derived from the directory attribute: ReadOnlyReplicaDirectoryServers
      - ReplicaDirectoryServers - A property of type System.String, derived
        from the directory attribute: ReplicaDirectoryServers
      - SubordinateReferences - A property of type System.String, derived from
        the directory attribute: SubordinateReferences
      - ADDomain - Represents a domain in AD DS or an instance in AD LDS; for
        example, an Active Directory object of type domainDNS and is derived
        from ADPartition. This class is not supported by AD LDS. An ADDomain
        may contain the following properties in addition to those inherited
        from its parent.
        - AllowedDNSSuffixes - A property of type System.String, derived from
          the directory attribute: msDS-AllowedDNSSuffixes
        - ChildDomains - A property of type System.String, derived from the
          directory attribute: ChildDomains
        - ComputersContainer - A property of type System.String, derived from
          the directory attribute: ComputersContainer
        - DomainControllersContainer - A property of type System.String,
          derived from the directory attribute: DomainControllersContainer
        - DomainMode - A property of type System.Int32, derived from the
          directory attribute: msDS-Behavior-Version
        - DomainSID - A property of type
          System.Security.Principal.SecurityIdentifier, derived from the
          directory attribute: objectSid
        - ForeignSecurityPrincipalsContainer - A property of type
          System.String, derived from the directory attribute:
          ForeignSecurityPrincipalsContainer
        - Forest - A property of type System.String, derived from the directory
          attribute: Forest
        - InfrastructureMaster - A property of type System.String, derived from
          the directory attribute: InfrastructureMaster
        - LastLogonReplicationInterval - A property of type System.TimeSpan,
          derived from the directory attribute: msDS-LogonTimeSyncInterval
        - LinkedGroupPolicyObjects - A property of type System.String, derived
          from the directory attribute: LinkedGroupPolicyObjects
        - ManagedBy - A property of type System.String, derived from the
          directory attribute: managedBy
        - NetBIOSName - A property of type System.String, derived from the
          directory attribute: NetBIOSName
        - ParentDomain - A property of type System.String, derived from the
          directory attribute: ParentDomain
        - PDCEmulator - A property of type System.String, derived from the
          directory attribute: PDCEmulator
        - RIDMaster - A property of type System.String, derived from the
          directory attribute: RIDMaster
        - SystemsContainer - A property of type System.String, derived from the
          directory attribute: SystemsContainer
        - UsersContainer - A property of type System.String, derived from the
          directory attribute: UsersContainer
      - ADPrincipal - Represents a security principal, which is an Active
        Directory object of type user, computer, group or iNetOrgPerson and is
        derived from ADObject. An ADPrincipal may contain the following
        properties in addition to those inherited from its parent.
        - HomePage - A property of type System.String, derived from the
          directory attribute: wWWHomePage
        - MemberOf - A property of type System.String, derived from the
          directory attribute: memberOf
        - SamAccountName - A property of type System.String, derived from the
          directory attribute: sAMAccountName. This property is not supported
          for AD LDS.
        - SID - A property of type
          System.Security.Principal.SecurityIdentifier, derived from the
          directory attribute: objectSid
        - SIDHistory - A property of type
          System.Security.Principal.SecurityIdentifier, derived from the
          directory attribute: sIDHistory. This property is not supported for
          AD LDS.
        - ADAccount - Represents a security account; that is, an Active
          Directory object of type user, computer or iNetOrgPerson and is
          derived from ADPrincipal. An ADAccount may contain the following
          properties in addition to those inherited from its parent.
          - AccountExpirationDate - A property of type System.DateTime, derived
            from the directory attribute: accountExpires
          - AccountLockoutTime - A property of type System.DateTime, derived
            from the directory attribute: lockoutTime
          - AccountNotDelegated - A property of type System.Boolean, derived
            from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed. This property is not supported
            by AD LDS.
          - AllowReversiblePasswordEncryption - A property of type
            System.Boolean, for AD DS it is derived from the directory
            attribute: userAccountControl; for AD LDS it is derived from the
            directory attribute: ms-DS-UserEncryptedTextPasswordAllowed
          - BadLogonCount - A property of type System.Int32, derived from the
            directory attribute: badPwdCount
          - CannotChangePassword - A property of type System.Boolean, derived
            from the directory attribute: nTSecurityDescriptor
          - Certificates - A property of type
            System.Security.Cryptography.X509Certificates.X509Certificate,
            derived from the directory attribute: userCertificate
          - DoesNotRequirePreAuth - A property of type System.Boolean, derived
            from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed. This property is not supported
            by AD LDS.
          - Enabled - A property of type System.Boolean, for AD DS it is
            derived from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed; for AD LDS it is derived from
            the directory attribute msDS-UserAccountDisabled
          - HomedirRequired - A property of type System.Boolean, derived from
            the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed. This property is not supported
            by AD LDS.
          - LastBadPasswordAttempt - A property of type System.DateTime,
            derived from the directory attribute: badPasswordTime
          - LastLogonDate - A property of type System.DateTime, derived from
            the directory attribute: lastLogonTimestamp
          - LockedOut - A property of type System.Boolean, for AD DS it is
            derived from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed, lockoutTime; for AD LDS it is
            derived from the directory attribute msDS-UserAccountDisabled
          - MNSLogonAccount - A property of type System.Boolean, derived from
            the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed. This property is not supported
            by AD LDS.
          - PasswordExpired - A property of type System.Boolean, for AD DS it
            is derived from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed; for AD LDS it is derived from
            the directory attribute msDS-UserPasswordExpired
          - PasswordLastSet - A property of type System.DateTime, derived from
            the directory attribute: pwdLastSet
          - PasswordNeverExpires - A property of type System.Boolean, for AD
            LDS it is derived from the directory attributes:
            userAccountControl, msDS-User-Account-Control-Computed; for AD LDS
            it is derived from the directory attribute:
            msDS-UserDontExpirePassword
          - PasswordNotRequired - A property of type System.Boolean, for AD DS
            it is derived from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed; for AD LDS it is derived from
            the directory attribute: ms-DS-UserPasswordNotRequired
          - PrimaryGroup - A property of type System.String, derived from the
            directory attributes: primaryGroupID, objectSid. This property is
            not supported by AD LDS.
          - ServicePrincipalNames - A property of type System.String, derived
            from the directory attribute: servicePrincipalName. This property
            is not supported by AD LDS.
          - TrustedForDelegation - A property of type System.Boolean, derived
            from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed. This property is not supported
            by AD LDS.
          - TrustedToAuthForDelegation - A property of type System.Boolean,
            derived from the directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed. This property is not supported
            by AD LDS.
          - UseDESKeyOnly - A property of type System.Boolean, derived from the
            directory attributes: userAccountControl,
            msDS-User-Account-Control-Computed. This property is not supported
            by AD LDS.
          - UserPrincipalName - A property of type System.String, derived from
            the directory attribute: userPrincipalName
          - ADComputer - Represents a computer and is derived from ADAccount.
            An ADComputer may contain the following properties in addition to
            those inherited from its parent.
            - DNSHostName - A property of type System.String, derived from the
              directory attribute: dNSHostName
            - IPv4Address - A property of type System.String, derived from the
              directory attribute: dNSHostName
            - IPv6Address - A property of type System.String, derived from the
              directory attribute: dNSHostName
            - Location - A property of type System.String, derived from the
              directory attribute: location
            - ManagedBy - A property of type System.String, derived from the
              directory attribute: managedBy
            - OperatingSystem - A property of type System.String, derived from
              the directory attribute: operatingSystem
            - OperatingSystemHotfix - A property of type System.String, derived
              from the directory attribute: operatingSystemHotfix
            - OperatingSystemServicePack - A property of type System.String,
              derived from the directory attribute: operatingSystemServicePack
            - OperatingSystemVersion - A property of type System.String,
              derived from the directory attribute: operatingSystemVersion
            - ServiceAccount - A property of type System.String, derived from
              the directory attribute: msDS-HostServiceAccount
          - ADServiceAccount - Represents a managed service account; that is,
            an Active Directory object of type msDS-ManagerdServiceAccount and
            is derived from ADAccount. This class is not supported by AD LDS.
            An ADServiceAccount may contain the following properties in
            addition to those inherited from its parent.
            - HostComputers - A property of type System.String, derived from
              the directory attribute: msDS-HostServiceAccountBL
          - ADUser - Represents a user (or iNetOrgPerson) and is derived from
            ADAccount. An ADUser may contain the following properties in
            addition to those inherited from its parent.
            - City - A property of type System.String, derived from the
              directory attribute: l
            - Company - A property of type System.String, derived from the
              directory attribute: company
            - Country - A property of type System.String, derived from the
              directory attribute: c
            - Department - A property of type System.String, derived from the
              directory attribute: department
            - Division - A property of type System.String, derived from the
              directory attribute: division
            - EmailAddress - A property of type System.String, derived from the
              directory attribute: mail
            - EmployeeID - A property of type System.String, derived from the
              directory attribute: employeeID
            - EmployeeNumber - A property of type System.String, derived from
              the directory attribute: employeeNumber
            - Fax - A property of type System.String, derived from the
              directory attribute: facsimileTelephoneNumber
            - GivenName - A property of type System.String, derived from the
              directory attribute: givenName
            - HomeDirectory - A property of type System.String, derived from
              the directory attribute: homeDirectory. This property is not
              supported by AD LDS.
            - HomeDrive - A property of type System.String, derived from the
              directory attribute: homeDrive. This property is not supported by
              AD LDS.
            - HomePhone - A property of type System.String, derived from the
              directory attribute: homePhone
            - Initials - A property of type System.String, derived from the
              directory attribute: initials
            - LogonWorkstations - A property of type System.String, derived
              from the directory attribute: userWorkstations. This property is
              not supported by AD LDS.
            - Manager - A property of type System.String, derived from the
              directory attribute: manager
            - MobilePhone - A property of type System.String, derived from the
              directory attribute: mobile
            - Office - A property of type System.String, derived from the
              directory attribute: physicalDeliveryOfficeName
            - OfficePhone - A property of type System.String, derived from the
              directory attribute: telephoneNumber
            - Organization - A property of type System.String, derived from the
              directory attribute: o
            - OtherName - A property of type System.String, derived from the
              directory attribute: middleName
            - POBox - A property of type System.String, derived from the
              directory attribute: postOfficeBox
            - PostalCode - A property of type System.String, derived from the
              directory attribute: postalCode
            - ProfilePath - A property of type System.String, derived from the
              directory attribute: profilePath. This property is not supported
              by AD LDS.
            - ScriptPath - A property of type System.String, derived from the
              directory attribute: scriptPath. This property is not supported
              by AD LDS.
            - SmartcardLogonRequired - A property of type System.Boolean,
              derived from the directory attributes: userAccountControl,
              msDS-User-Account-Control-Computed. This property is not
              supported by AD LDS.
            - State - A property of type System.String, derived from the
              directory attribute: st
            - StreetAddress - A property of type System.String, derived from
              the directory attribute: streetAddress
            - Surname - A property of type System.String, derived from the
              directory attribute: sn
            - Title - A property of type System.String, derived from the
              directory attribute: title
        - ADGroup -Represents a group and is derived from ADPrincipal. An
          ADGroup may contain the following properties in addition to those
          inherited from its parent.
          - GroupCategory - A property of type
            Microsoft.ActiveDirectory.Management.ADGroupCategory, derived from
            the directory attribute: groupType
          - GroupScope - A property of type
            Microsoft.ActiveDirectory.Management.ADGroupScope, derived from the
            directory attribute: groupType
          - ManagedBy - A property of type System.String, derived from the
            directory attribute: managedBy
          - Members - A property of type System.String, derived from the
            directory attribute: member
  - ADDefaultDomainPasswordPolicy - Represents the domain-wide password policy
    of an Active Directory domain and is derived from ADEntity. This class is
    not supported by AD LDS. An ADDefaultDomainPasswordPolicy may contain the
    following properties in addition to those inherited from its parent.
    - ComplexityEnabled - A property of type System.Boolean, derived from the
      directory attribute: pwdProperties
    - DistinguishedName - A property of type System.String, derived from the
      directory attribute: distinguishedName
    - LockoutDuration - A property of type System.TimeSpan, derived from the
      directory attribute: lockoutDuration
    - LockoutObservationWindow - A property of type System.TimeSpan, derived
      from the directory attribute: lockoutObservationWindow
    - LockoutThreshold - A property of type System.Int32, derived from the
      directory attribute: lockoutThreshold
    - MaxPasswordAge - A property of type System.TimeSpan, derived from the
      directory attribute: maxPwdAge
    - MinPasswordAge - A property of type System.TimeSpan, derived from the
      directory attribute: minPwdAge
    - MinPasswordLength - A property of type System.Int32, derived from the
      directory attribute: minPwdLength
    - PasswordHistoryCount - A property of type System.Int32, derived from the
      directory attribute: pwdHistoryLength
    - ReversibleEncryptionEnabled - A property of type System.Boolean, derived
      from the directory attribute: pwdProperties
  - ADForest - Represents a Active Directory forest in AD DS or a Configuration
    Set in AD LDS and is derived from ADEntity. This class is not supported by
    AD LDS. An ADForest may contain the following properties in addition to
    those inherited from its parent.
    - ApplicationPartitions - A property of type System.String, derived from
      the directory attribute: ApplicationPartitions
    - CrossForestReferences - A property of type System.String, derived from
      the directory attribute: CrossForestReferences
    - DomainNamingMaster - A property of type System.String, derived from the
      directory attribute: DomainNamingMaster
    - Domains - A property of type System.String, derived from the directory
      attribute: Domains
    - ForestMode - A property of type System.Int32, derived from the directory
      attribute: msDS-Behavior-Version
    - GlobalCatalogs - A property of type System.String, derived from the
      directory attribute: GlobalCatalogs
    - Name - A property of type System.String, derived from the directory
      attribute: name
    - PartitionContainerName - A property of type System.String, derived from
      the directory attribute: distinguishedName
    - RootDomain - A property of type System.String, derived from the directory
      attribute: RootDomain
    - SchemaMaster - A property of type System.String, derived from the
      directory attribute: SchemaMaster
    - Sites - A property of type System.String, derived from the directory
      attribute: Sites
    - SPNSuffixes - A property of type System.String, derived from the
      directory attribute: msDS-SPNSuffixes
    - UPNSuffixes - A property of type System.String, derived from the
      directory attribute: uPNSuffixes
  - ADDirectoryServer - Represents a directory server used as either a domain
    controller or an AD LDS instance and is derived from ADEntity. An
    ADDirectoryServer may contain the following properties in addition to those
    inherited from its parent.
    - DefaultPartition - A property of type System.String, derived from the
      directory attribute: DefaultPartition
    - HostName - A property of type System.String, derived from the directory
      attribute: HostName
    - InvocationId - A property of type System.Guid, derived from the directory
      attribute: InvocationId
    - IPv4Address - A property of type System.String, derived from the
      directory attribute: HostName
    - IPv6Address - A property of type System.String, derived from the
      directory attribute: HostName
    - LdapPort - A property of type System.Int32, derived from the directory
      attribute: LdapPort
    - Name - A property of type System.String, derived from the directory
      attribute: Name
    - NTDSSettingsObjectDN - A property of type System.String, derived from the
      directory attribute: NTDSSettingsObjectDN
    - OperationMasterRoles - A property of type
      Microsoft.ActiveDirectory.Management.ADOperationMasterRole, derived from
      the directory attribute: OperationMasterRole
    - Partitions - A property of type System.String, derived from the directory
      attribute: Partitions
    - ServerObjectDN - A property of type System.String, derived from the
      directory attribute: ServerObjectDN
    - ServerObjectGuid - A property of type System.Guid, derived from the
      directory attribute: ServerObjectGuid
    - Site - A property of type System.String, derived from the directory
      attribute: Site
    - SslPort - A property of type System.Int32, derived from the directory
      attribute: SslPort
    - ADDomainController - Represents a domain controller in AD DS and is
      derived from ADDirectoryServer. An ADDomainController may contain the
      following properties in addition to those inherited from its parent.
      - ComputerObjectDN - A property of type System.String, derived from the
        directory attribute: ComputerDN
      - Domain - A property of type System.String, derived from the directory
        attribute: Domain
      - Enabled - A property of type System.Boolean, derived from the directory
        attribute: Enabled
      - Forest - A property of type System.String, derived from the directory
        attribute: Forest
      - IsGlobalCatalog - A property of type System.Boolean, derived from the
        directory attribute: IsGlobalCatalog
      - IsReadOnly - A property of type System.Boolean, derived from the
        directory attribute: IsReadOnly
      - OperatingSystem - A property of type System.String, derived from the
        directory attribute: OSName
      - OperatingSystemHotfix - A property of type System.String, derived from
        the directory attribute: OSHotFix
      - OperatingSystemServicePack - A property of type System.String, derived
        from the directory attribute: OSServicepack
      - OperatingSystemVersion - A property of type System.String, derived from
        the directory attribute: OSVersion
