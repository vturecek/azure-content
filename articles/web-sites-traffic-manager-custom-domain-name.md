<properties 
	pageTitle="Configure a custom domain name for an Azure website that uses Traffic Manager" 
	description="" 
	services="web-sites" 
	documentationCenter="" 
	authors="wpickett" 
	manager="wpickett" 
	editor=""/>

<tags 
	ms.service="web-sites" 
	ms.workload="web" 
	ms.tgt_pltfrm="na" 
	ms.devlang="na" 
	ms.topic="article" 
	ms.date="2/18/2015" 
	ms.author="wpickett"/>

#Configuring a custom domain name for an Azure Website using Traffic Manager

[AZURE.INCLUDE [web-selector](../includes/websites-custom-domain-selector.md)]


[AZURE.INCLUDE [websites-cloud-services-css-guided-walkthrough](../includes/websites-cloud-services-css-guided-walkthrough.md)]

[AZURE.INCLUDE [intro](../includes/custom-dns-web-site-intro-traffic-manager.md)]

This article provides generic instructions for using a custom domain name with Azure Websites that use Traffic Manager for load balancing.

[AZURE.INCLUDE [tmwebsitefooter](../includes/custom-dns-web-site-traffic-manager-notes.md)]

[AZURE.INCLUDE [introfooter](../includes/custom-dns-web-site-intro-notes.md)]

In this article:

-   [Understanding DNS records](#understanding-records)
-   [Configure your web sites for standard mode](#bkmk_configsharedmode)
-   [Add a DNS record for your custom domain](#bkmk_configurecname)
-   [Enable Traffic Manager for your web site](#enabledomain)

<h2><a name="understanding-records"></a>Understanding DNS records</h2>

[AZURE.INCLUDE [understandingdns](../includes/custom-dns-web-site-understanding-dns-traffic-manager.md)]

<h2><a name="bkmk_configsharedmode"></a>Configure your websites for standard mode</h2>

[AZURE.INCLUDE [modes](../includes/custom-dns-web-site-modes-traffic-manager.md)]

<a name="bkmk_configurecname"></a><h2>Add a DNS record for your custom domain</h2>

To associate your custom domain with an Azure Website, you must add a new entry in the DNS table for your custom domain by using tools provided by the domain registrar that you purchased your domain name from. Use the following steps to locate and use the DNS tools.

1. Log on to your account at your domain registrar, and look for a page for managing DNS records. Look for links or areas of the site labeled as **Domain Name**, **DNS**, or **Name Server Management**. Often a link to this page can be found be viewing your account information, and then looking for a link such as **My domains**.

4. Once you have found the management page for your domain name, look for a link that allows you to edit the DNS records. This might be listed as a **Zone file**, **DNS Records**, or as an **Advanced** configuration link.

	* The page will most likely have a few records already created, such as an entry associating '**@**' or '\*' with a 'domain parking' page. It may also contain records for common sub-domains such as **www**.
	* The page will mention **CNAME records**, or provide a drop-down to select a record type. It may also mention other records such as **A records** and **MX records**. In some cases, CNAME records will be called by other names such as an **Alias Record**.
	* The page will also have fields that allow you to **map** from a **Host name** or **Domain name** to another domain name.

5. While the specifics of each registrar vary, in general you map *from* your custom domain name (such as **contoso.com**,) *to* the Traffic Manager domain name (**contoso.trafficmanager.net**) that is used for your Azure Website.

6. Once you have finished adding or modifying DNS records at your registrar, save the changes.

<h2><a name="enabledomain"></a>Enable Traffic Manager website</h2>

[AZURE.INCLUDE [modes](../includes/custom-dns-web-site-enable-on-traffic-manager.md)]
