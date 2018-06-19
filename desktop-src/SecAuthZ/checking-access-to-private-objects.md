---
Description: A protected server application must check a clients access rights before allowing the client to access a protected private object.
ms.assetid: dce4dd10-1d5f-40a3-8a7e-ec708d3123c7
title: Checking Access to Private Objects
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Checking Access to Private Objects

A protected server application must check a client's access rights before allowing the client to access a protected private object. To do this, the server passes an [*impersonation token*](https://msdn.microsoft.com/library/windows/desktop/ms721588#-security-impersonation-token-gly), a security descriptor, and a set of requested access rights to [**AccessCheck**](https://msdn.microsoft.com/en-us/library/Aa374815(v=VS.85).aspx). The [*access control entries*](https://msdn.microsoft.com/library/windows/desktop/ms721532#-security-access-control-entry-gly) (ACEs) in the [*security descriptor's*](https://msdn.microsoft.com/library/windows/desktop/ms721625#-security-security-descriptor-gly) DACL specify the access rights allowed or denied to various trustees. The **AccessCheck** function compares the trustee in each ACE to the trustees identified in the impersonation token. For a description of the algorithm used to grant or deny access, see [How DACLs Control Access to an Object](how-dacls-control-access-to-an-object.md).

The [**AccessCheckAndAuditAlarm**](/windows/desktop/api/Winbase/nf-winbase-accesscheckandauditalarma) function performs a similar access check. In addition, it generates audit records in the security event log depending on the SACL in the security descriptor.

The [**AccessCheckByType**](https://msdn.microsoft.com/en-us/library/Aa374826(v=VS.85).aspx) and [**AccessCheckByTypeAndAuditAlarm**](/windows/desktop/api/Winbase/nf-winbase-accesscheckbytypeandauditalarma) functions are similar to [**AccessCheck**](https://msdn.microsoft.com/en-us/library/Aa374815(v=VS.85).aspx) and [**AccessCheckAndAuditAlarm**](/windows/desktop/api/Winbase/nf-winbase-accesscheckandauditalarma) except that they allow you to check access to the subobjects of an object, such as property sets or properties. The [**AccessCheckByTypeResultList**](https://msdn.microsoft.com/en-us/library/Aa374836(v=VS.85).aspx) and [**AccessCheckByTypeResultListAndAuditAlarm**](/windows/desktop/api/Winbase/nf-winbase-accesscheckbytyperesultlistandauditalarma) functions are also similar to **AccessCheck** except that they provide the access check results for each subobject in a hierarchy of the object's properties and property sets. These functions use the [**OBJECT\_TYPE\_LIST**](/windows/desktop/api/Winnt/ns-winnt-_object_type_list) structure to describe the hierarchy of objects for which access is checked. The functions that generate an audit message use the [**AUDIT\_EVENT\_TYPE**](/windows/desktop/api/Winnt/ne-winnt-_audit_event_type) enumeration type to indicate whether the object being checked is a directory service object. For more information about the hierarchy of an object and its subobjects, see [ACEs to Control Access to an Object's Properties](aces-to-control-access-to-an-object-s-properties.md).

The requested access rights passed to the [**AccessCheck**](https://msdn.microsoft.com/en-us/library/Aa374815(v=VS.85).aspx) and [**AccessCheckAndAuditAlarm**](/windows/desktop/api/Winbase/nf-winbase-accesscheckandauditalarma) functions must not include any [generic access rights](generic-access-rights.md). The server can use the [**MapGenericMask**](https://msdn.microsoft.com/en-us/library/Aa379266(v=VS.85).aspx) function to convert any generic access rights to the corresponding specific and standard rights according to the mapping specified in the [**GENERIC\_MAPPING**](/windows/desktop/api/Winnt/ns-winnt-_generic_mapping) structure.

The [**AreAllAccessesGranted**](https://msdn.microsoft.com/en-us/library/Aa375351(v=VS.85).aspx) and [**AreAnyAccessesGranted**](https://msdn.microsoft.com/en-us/library/Aa375363(v=VS.85).aspx) functions compare a requested [*access mask*](https://msdn.microsoft.com/library/windows/desktop/ms721532#-security-access-mask-gly) with a granted access mask.

For sample code that uses the [**AccessCheck**](https://msdn.microsoft.com/en-us/library/Aa374815(v=VS.85).aspx) function, see [Verifying Client Access with ACLs in C++](verifying-client-access-with-acls-in-c--.md).

The [**ConvertToAutoInheritPrivateObjectSecurity**](https://msdn.microsoft.com/en-us/library/Aa376403(v=VS.85).aspx) function creates and returns a security descriptor in a format that allows the automatic propagation of inheritable ACEs. This security descriptor contains all of the ACEs, inherited and noninherited, in the current security descriptor and is in [*self-relative*](https://msdn.microsoft.com/library/windows/desktop/ms721625#-security-self-relative-security-descriptor-gly) format. The **ConvertToAutoInheritPrivateObjectSecurity** function determines whether the ACEs are inherited or noninherited by comparing all of the ACEs in the current security descriptor with all of the ACEs in its parent security descriptor. There may not be a one-to-one correspondence between the two groups of ACEs. For instance, an ACE that allows read/write permission can be equivalent to two ACEs: an ACE that allows read permission and an ACE that allows write permission. A parent security descriptor may not be supplied when the current security descriptor is the parent.

 

 


