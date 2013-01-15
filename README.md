LDAPUnit
========

**LDAPUnit** is a Java library help create unit tests for that depend on an LDAP directory server.

DirectoryServerRule
-------------------

[DirectoryServerRule](http://ldapunit.btmatthews.com/apidocs/com/btmatthews/ldapunit/DirectoryServerRule.html) is used
launch an embedded LDAP directory server so that the unit tests do not have to be dependent on an external LDAP
directory server with unpredictable state.

```java

import com.btmatthews.ldapunit.DirectoryServerConfiguration;
import com.btmatthews.ldapunit.DirectoryServerRule;
import org.junit.Rule;
import org.junit.Test;
.
.

@DirectoryServerConfiguration
public class Test {

    @Rule
    public DirectoryServerRule directoryServerRule = new DirectoryServerRule();
    .
    .

    @Test
    public void testSomething() {
        .
        .
    }
    .
    .
}
```

DirectoryTester
---------------

[DirectoryTester](http://ldapunit.btmatthews.com/apidocs/com/btmatthews/ldapunit/DirectoryServerRule.html) is used to
connect to an LDAP directory server (embedded or external) and make assertions about or verify the contents of the LDAP
directory.

Maven Central Coordinates
-------------------------
**LDAPUnit** has been published in [Maven Central](http://search.maven.org) at the following
coordinates:

```xml
<plugin>
    <groupId>com.btmatthews.ldapunit</groupId>
    <artifactId>ldapunit</artifactId>
    <version>1.0.0</version>
</plugin>
```

Credits
-------
The approach for implementing the **LDAPUnit**'s **DirectoryServerRule** is based heavily on the **OpenDJRule**
implemented in the https://github.com/ehsavoie/embedded-ldap project.

Internally **LDAPUnit** is using the [UnboundID LDAP SDK](https://www.unboundid.com/products/ldap-sdk) to run the
embedded LDAP directory server and as the API for communicating with an LDAP directory server.

License & Source Code
---------------------
The **LDAPUnit** is made available under the
[Apache License](http://www.apache.org/licenses/LICENSE-2.0.html) and the source code is hosted on
[GitHub](http://github.com) at https://github.com/bmatthews68/ldapunit.