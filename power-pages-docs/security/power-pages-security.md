---
title: Power Pages security
description: Learn how to secure your Power Pages sites.
author: nickdoelman
ms.topic: conceptual
ms.custom: 
ms.date: 10/03/2022
ms.author: ndoelman
ms.reviewer: kkendrick
contributors:
    - nickdoelman
    - ProfessorKendrick
---

# Power Pages security

An important consideration when building public-facing websites is to ensure that critical business information is only accessible by the correct stakeholders.

Power Pages has a robust security model to ensure that business information is properly protected. The following key components are used to provide and protect access in Power Pages:

- Site visibility
- Authenticated users
- Web roles
- Table permissions
- Page permissions

## Site visibility

By default, all sites created in Power Pages are only available to users internal to your organization through the site visibility setting. This way, you can benefit from an additional layer of security using Azure Active Directory authentication to prevent accidental leaks of partially developed website data and design. When your website is ready to go live, change the site visibility to public making it accessible to everyone over the internet anonymously or secured with identity providers.

More information: [Site visibility](site-visibility.md)

## Authenticated users

Users can be provided access to your site through authentication. Power Pages users are represented by Microsoft Dataverse contact records. Power Pages can be integrated with many authentication providers such as Azure Active Directory B2C, Microsoft, and LinkedIn.

Authenticated users can then be assigned to web roles that will provide specific access to information on the site.

More information: [Configure Authentication](configure-portal-authentication.md)

## Web roles

Web roles can be created to allow users to perform any special actions or access any protected content and data on the site. Web roles link to users, table permissions, and page permissions. Because contacts can be assigned multiple web roles, they can be provided cumulative access to site resources.

All authenticated users (contacts) are automatically assigned to the Authenticated Users web role.

A site can be visited by anonymous users (unauthenticated) and given access to assets through the Anonymous Users web role.

More information: [Configure web roles](create-web-roles.md)

## Table permissions

Accessing Dataverse information through [lists](../getting-started/add-list.md), [forms](../getting-started/add-form.md), [Liquid](../configure/liquid-overview.md), and the [Web API](../configure/web-api-overview.md) are by default protected by table permissions. You can configure table permissions to allow different levels of access and privileges to Dataverse records. Table permissions are associated to web roles to provide appropriate access to users.

More information: [Configure table permissions](table-permissions.md)

## Page permissions

Individual pages containing content or other components can also be protected by configuring page permissions that are associated with web roles to allow access.

More information: [Page permissions](page-security.md)

## Additional website security

Power Pages can be integrated with any web application firewall infrastructure to provide extra protection against common web application attacks. For information on how to integrate it with Azure Front Door web application firewall, see [Set up Azure Front Door with portals](/power-apps/maker/portals/azure-front-door)

## Deep dive: Architecture and security

The following white papers allow you to explore Power Pages architecture and security at a deeper level. 

| White paper | Description | Date |
| - | - | - |
| [Power Pages Architecture white paper](/power-pages/guidance/white-papers/architecture) | This white paper provides a comprehensive view of the capabilities of the Power Pages platform. It describes the architectural elements that enable Power Pages to scale, offer high reliability and availability, and protect business data to offer enterprise grade compliance and security.  | October 2022 |
| [Power Pages Security white paper](/power-pages/guidance/white-papers/security) | This white paper describes how Power Pages offers enterprise grade security and the tools and capabilities it offers for administrators and makers to harden security for their external applications. | October 2022 |

### See also
[Power Platform security](/power-platform/admin/security/)<br/>
[Azure security](/azure/security/)
