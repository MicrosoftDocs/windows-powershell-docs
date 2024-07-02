---
title: about_ActiveDirectory_Filter
ms.date: 04/22/2013
description: Describes the syntax and behavior of the search filter supported by the Active Directory module for Windows PowerShell.
Locale: en-US
schema: 2.0.0
---

# about_ActiveDirectory_Filter

## SHORT DESCRIPTION

Describes the syntax and behavior of the search filter supported by the Active
Directory module for Windows PowerShell.

## LONG DESCRIPTION

Most get-AD* Active Directory module cmdlets use the Filter parameter to search
for objects. The Filter parameter has been implemented to replace the function
of the LDAP Filter and adds support for PowerShell variables, rich data types,
improved error checking and an Active Directory extended form of the PowerShell
Expression Language.


- Support for LDAP Filter Syntax

  The LDAP filter syntax is supported through the **LDAPFilter** parameter. You
  will find LDAP filter examples along with the new Active Directory module
  filter examples in the Filter Examples section of this topic.


- Search Breadth and Depth

  The breadth and depth of your filter-driven search can be modified by two
  Active Directory module cmdlet parameters: **SearchBase** and **SearchScope**.

  When within the context of the Active Directory provider, if the
  **Searchbase** parameter is not specified, **SearchBase** will default to the
  current path. When not running under the Active Directory provider, the
  **SearchBase** will default to the server's **DefaultNamingContext**.

  The **SearchScope** parameter defaults to the value `Subtree`, of the
  enumerated type **ADSearchScope**.

  For more information, see the **SearchBase** and **SearchScope** parameter
  descriptions on any `Get-AD*` cmdlet.

- Search Result Behavior

  The behavior of the Active Directory module when returning results of a
  search is modified by two cmdlet parameters: **ResultPageSize** and
  **ResultSetSize**.

  **ResultSetSize** controls the maximum number of returned objects.

  **ResultPageSize** specifies the maximum number of objects for each returned
  page of information.

  See the **ResultPageSize** and **ResultSetSize** parameter descriptions on
  any `Get-AD*` cmdlet for more information.


- Timeout Behavior

  The following statements specify timeout conditions within the Active
  Directory module and describe what can be done about a timeout them.

  The default Active Directory module timeout for all operations is 2
  minutes.

  For search operation, the Active Directory module uses paging control
  with a 2-minute timeout for each page search.

  > [!NOTE]
  > Because a search may involve multiple server page requests the overall
  > search time may exceed 2 minutes.

  A **TimeoutException** error indicates that a timeout has occurred.

  For a search operation, you can choose to use a smaller page size, set with
  the **ResultPageSize** parameter, if you are getting a **TimeoutException**
  error.

  If after trying these changes you are still getting a **TimeoutException**
  error, consider optimizing your filter using the guidance in the
  Optimizing Filters section of this topic.


- Optimizing Filters

  You can enhance the search filter behavior by using these guidelines.

  - Avoid using the **Recursive** parameter as it intensifies resource usage of
    the search operation.
  - Avoid using bitwise AND operators and bitwise OR operators. For more
    information, see the Supported Operators section of this topic.
  - Avoid using the logical NOT operator.
  - Break down your search into multiple queries with narrower conditions.

  For a full description of filter syntax and usage, see the Filter Syntax
  section of this topic.


## Filter Examples

The following section shows many examples of filter use in common queries.

### Example 1 - Get all entries:

- LDAP Filter Equivalent: `(objectClass=*)`

```powershell
Get-ADObject -Filter 'ObjectClass -like "*"'
```

### Example 2 - Get entries containing "bob" somewhere in the common name

- LDAP Filter Equivalent: `(cn=*bob*)`

```powershell
Get-ADObject -Filter 'CN -like "*bob*"'
```

### Example 3 - Get entries with a bad password count greater than five

- LDAP Filter Equivalent: `(&(!badpwdcount<=5)(badpwdcount=*))`

```powershell
Get-ADUser -Filter 'badpwdcount -ge 5'
```

### Example 4 - Get all users with an e-mail attribute

- LDAP Filter Equivalent: `(&(objectClass=user)(email=*))`

```powershell
Get-ADUser -filter 'email -like "*"'
```

-or-

```powershell
Get-ADObject -filter 'email -like "*" -and ObjectClass -eq "user"'
```

### Example 5 - Get all user entries with an e-mail attribute and a surname equal to "smith":

- LDAP Filter Equivalent: `(&(sn=smith)(objectClass=user)(email=*))`

```powershell
Get-ADUser -Filter 'Email -like "*" -and SurName -eq "smith"'
```

-or-

```powershell
Get-ADUser -Filter 'Email -like "*" -and sn -eq "smith"'
```


### Example 6 - Get all user entries with a common name that starts with "andy" and users with a common name of "steve" or "margaret"

- LDAP Filter Equivalent: `(&(objectClass=user) | (cn=andy*)(cn=steve)(cn=margaret))`

```powershell
Get-ADUser -Filter 'CN -like "andy*" -or CN -eq "steve" -or CN -eq "margaret"'
```


This example demonstrates a more complex logic and the use of precedence
control via parenthesis.

```powershell
Get-ADObject -Filter 'objectClass -eq "user" -and (CN -like "andy*" -or CN -eq "steve" -or CN -eq "margaret")'
```

### Example 7 - Get all entries without an e-mail attribute

- LDAP Filter Equivalent: `(!(email=*))`

```powershell
Get-ADUser -Filter '-not Email -like "*"'
```

-or-

```powershell
Get-ADUser -Filter 'Email -notlike "*"'
```

### Example 8 - Get all users who did not logon since January 1, 2007

- LDAP Filter Equivalent: `(&(lastlogon<=X)(objectClass=user))` where X is
  number of 100-nanosecond slices since Jan 1st 1601

```powershell
$date = new-object System.DateTime -ArgumentList @(2007,1,1,0,0,0)
Get-ADUser -Filter '-not LastLogon -le $date'
```

### Example 9 - Get all users who have logged on in the last 5 days

- LDAP Filter Equivalent:

  ```
  (&(lastLogon>=128812906535515110)
    (objectClass=user)(!(objectClass=computer)))
  ```

```powershell
$date = (get-date) - (new-timespan -days 5)
Get-ADUser -Filter 'lastLogon -gt $date'
```

### Example 10 - Search for group objects that have the ADS_GROUP_TYPE_SECURITY_ENABLED flag set

- LDAP Filter Equivalent:
  `(&(objectCategory=group)(groupType:1.2.840.113556.1.4.803:=2147483648))`

The following example query string searches for group objects that have the
ADS_GROUP_TYPE_SECURITY_ENABLED flag set. Be aware that the decimal value of
ADS_GROUP_TYPE_SECURITY_ENABLED (0x80000000 = 2147483648) is used for the
comparison value.

```powershell
Get-ADGroup -filter 'groupType -band 0x80000000'
```

### Example 11 - Search the ancestry of an object

- LDAP Filter Equivalent:
  `(memberof:1.2.840.113556.1.4.1941:=(cn=Group1,OU=groupsOU,DC=x)))`

The LDAP_MATCHING_RULE_IN_CHAIN is a matching rule OID that is designed to
provide a method to look up the ancestry of an object. Many applications using
Active Directory and AD LDS usually work with hierarchical data, which is
ordered by parent-child relationships. Previously, applications performed
transitive group expansion to figure out group membership, which used a lot of
network bandwidth. Applications made multiple round-trips to figure out if an
object fell "in the chain" if a link were traversed through to the end.

An example of such a query is one designed to check if a user, "user1" is a
member of group "group1". "user1" may not be a direct member of group1. It
could be a member of some other group, which is a member of "group1".

You would set the base to the user DN and the scope to base, and use the query:

```powershell
Get-ADUser -Filter 'memberOf -RecursiveMatch "CN=Administrators, CN=Builtin,DC=Fabrikam,DC=com"' -SearchBase "CN=Administrator,CN=Users,DC=Fabrikam,DC=com"
```

## Filter Syntax

The following syntax descriptions use Backus-Naur form to show the PowerShell
Expression Language for the Filter parameter.

```Syntax
<filter>  ::= "{" <FilterComponentList> "}"

<FilterComponentList> ::= <FilterComponent> |
  <FilterComponent> <JoinOperator> <FilterComponent> |
  <NotOperator>  <FilterComponent>

<FilterComponent> ::= <attr> <FilterOperator> <value> |
  "(" <FilterComponent> ")"

<FilterOperator> ::= "-eq" | "-le" | "-ge" | "-ne" | "-lt" | "-gt" |
  "-approx" | "-bor" | "-band" | "-recursivematch" | "-like" |
  "-notlike"

<JoinOperator> ::= "-and" | "-or"

<NotOperator> ::= "-not"

<attr> ::= <PropertyName> | <LDAPDisplayName of the attribute>

<value>::= < this value will be compared to the object data for
  attribute <ATTR> using the specified filter operator
```


## Supported Operators

The following table shows frequently used search filter operators.

|     Operator      |              Description               |      LDAP Equivalent       |
| ----------------- | -------------------------------------- | -------------------------- |
| `-eq`             | Equal to. Wildcards not supported.     | =                          |
| `-ne`             | Not equal to. Wildcards not supported. | !x = y                     |
| `-approx`         | Approximately equal to                 | ~=                         |
| `-le`             | Lexicographically less than            | <=                         |
|                   | or equal to                            |                            |
| `-lt`             | Lexicographically less than            | !x >= y                    |
| `-ge`             | Lexicographically greater              | >=                         |
|                   | than or equal to                       |                            |
| `-gt`             | Lexicographically greater than         | !x <= y                    |
|                   |                                        |                            |
| `-and`            | AND                                    | &                          |
| `-or`             | OR                                     |                            |
| `-not`            | NOT                                    | !                          |
| `-bor`            | Bitwise OR                             | :1.2.840.113556.1.4.804:=  |
| `-band`           | Bitwise AND                            | :1.2.840.113556.1.4.803:=  |
| `-recursivematch` | Use LDAP_MATCHING_RULE_IN_CHAIN        | :1.2.840.113556.1.4.1941:= |
| `-like`           | Similar to `-eq` and supports          | =                          |
|                   | wildcard comparison. The only          |                            |
|                   | wildcard character supported is: `*`   |                            |
| `-notlike`        | Not like. Supports wild                | !x = y                     |
|                   | card comparison.                       |                            |

> [!NOTE]
> PowerShell wildcards, other than "*", such as "?" are not supported by the
> **Filter** parameter syntax.

### Operator Precedence

The following listing shows the precedence of operators for filters from
highest to lowest.

- Highest precedence: `-eq`, `-ge`, `-le`, `-approx`, `-band`, `-bor`,
  `-recursivematch`, `-ne`, `-like`, `-not`, `-and`
- Lowest precedence: `-or`

### Special Characters

The following escape sequence should be used for specifying special characters
in AD Filter STRING data, that is, data enclosed in double or single quotes.

| ASCII Character |             Escape sequence substitute              |
| --------------- | --------------------------------------------------- |
| `"`             | `` `" ``  (This escape sequence is only required if |
|                 | STRING data is enclosed in double quotes.)          |
| `'`             | `''`  (This escape sequence is only required if     |
|                 | STRING data is enclosed in single quotes.)          |
| NUL             | `\00` (This is a standard LDAP escape sequence.)    |
| `\`             | `\5c` (This is a standard LDAP escape sequence.)    |

### LDAP Special Characters

ADFilter parser will automatically convert all the below characters found in
STRING data, that is data enclosed in " " or ' ' to their LDAP escape sequence.
End users need not know about these LDAP escape sequence.

| ASCII Character |           Escape sequence substitute            |
| --------------- | ----------------------------------------------- |
| `*`             | `\2a`  (Character `*` will only be converted in |
|                 | -eq and -ne comparisons Users should use        |
|                 | -like and -notlike operators for wildcard       |
|                 | comparison.)                                    |
| `(`             | `\28`                                           |
| `)`             | `\29`                                           |
| `/`             | `\2f`                                           |
