---
title: 'Lync Server 2013: 클래스별 스키마 특성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09978d9b0cad055b4c3b33976df838ba5543887d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a>Lync Server 2013의 클래스별 스키마 특성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-29_

이 섹션에서는 각 Lync Server 2013 클래스에 포함할 수 있는 스키마 특성과 다른 클래스에 포함 될 수 있는 클래스에 대해 설명 합니다. 모든 수업 목록과 해당 설명은 [Lync Server 2013의 스키마 클래스 및 설명을](lync-server-2013-schema-classes-and-descriptions.md)참조 하세요. 모든 특성 목록과 해당 설명에 대 한 자세한 내용은 [Lync Server 2013의 스키마 특성 및 설명을](lync-server-2013-schema-attributes-and-descriptions.md)참조 하세요.

<div>

## <a name="attributes-by-class"></a>클래스별 특성


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>클래스만</th>
<th>이러한 특성이 포함 될 수 있습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Contact</p></td>
<td><p>msDS-SourceObjectDN</p>
<p>msRTCSIP-AcpInfo</p>
<p>msRTCSIP-ApplicationDestination</p>
<p>msRTCSIP-ApplicationOptions</p>
<p>msRTCSIP-ApplicationPrimaryLanguage</p>
<p>msRTCSIP-ApplicationSecondaryLanguages</p>
<p>msRTCSIP-ArchivingEnabled</p>
<p>msRTCSIP-DeploymentLocator</p>
<p>msRTCSIP-FederationEnabled</p>
<p>msRTCSIP-GroupingID</p>
<p>msRTCSIP-InternetAccessEnabled</p>
<p>msRTCSIP 선</p>
<p>msRTCSIP-LineServer</p>
<p>msRTCSIP 플래그</p>
<p>msRTCSIP-OriginatorSid</p>
<p>msRTCSIP-소유자 Urn</p>
<p>msRTCSIP-PrimaryHomeServer</p>
<p>msRTCSIP-PrimaryUserAddress</p>
<p>msRTCSIP-PrivateLine</p>
<p>msRTCSIP-ProxyAddresses</p>
<p>msRTCSIP-SourceObjectType</p>
<p>msRTCSIP-TargetHomeServer</p>
<p>msRTCSIP-TargetUserPolicies</p>
<p>msRTCSIP-TenantId</p>
<p>msRTCSIP-UserEnabled</p>
<p>UserExtension msRTCSIP</p>
<p>msRTCSIP-UserLocationProfile</p>
<p>msRTCSIP-UserPolicies</p>
<p>msRTCSIP-UserPolicy</p>
<p>msRTCSIP-UserRoutingGroupId</p>
<p>ProxyAddresses</p></td>
</tr>
<tr class="even">
<td><p>메일 받는 사람</p></td>
<td><p>msExchUCVoiceMailSettings</p>
<p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>msRTCSIP-ApplicationServerBL</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>msRTCSIP-ApplicationList</p>
<p>msRTCSIP-ApplicationServerPoolLink</p>
<p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-ServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p>
<p>msRTCSIP-ConferenceDirectoryId</p>
<p>msRTCSIP-ConferenceDirectoryTargetPool</p>
<p>msRTCSIP-ExtensionData</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>msRTCSIP-DefaultCWAExternalURL</p>
<p>msRTCSIP-DefaultCWAInternalURL</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-도메인</p></td>
<td><p>msRTCSIP-기본값</p>
<p>msRTCSIP-도메인 데이터</p>
<p>msRTCSIP-DomainName</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>msRTCSIP-EdgeProxyData</p>
<p>msRTCSIP-EdgeProxyFQDN</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>msRTCSIP-MCUData</p>
<p>msRTCSIP-MCUFactoryAddress</p>
<p>msRTCSIP-ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-ServerVersion</p>
<p>msRTCSIP-TrustedServiceLinks</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>msRTCSIP-EnterpriseServices</p>
<p>msRTCSIP-PoolAddress</p>
<p>msRTCSIP-ServerData</p>
<p>msRTCSIP-ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>msRTCSIP-BackEndServer</p>
<p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-MirrorBackEndServer</p>
<p>msRTCSIP-ServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Location연락처 매핑</p></td>
<td><p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-MappingContact</p>
<p>msRTCSIP-MappingLocation</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>msRTCSIP-ExternalAccessCode</p>
<p>msRTCSIP-LocationProfileOptions</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>msRTCSIP-MCUFactoryData</p>
<p>msRTCSIP-MCUFactoryProviderID</p>
<p>msRTCSIP-MCUServers</p>
<p>msRTCSIP-M가공선</p>
<p>msRTCSIP-MCUVendor 공급 업체</p>
<p>msRTCSIP-PoolAddresses</p>
<p>msRTCSIP-ServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>msRTCSIP-MCUFactoryPath</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-이동성</p></td>
<td><p>msRTCSIP-MobilityFlags</p>
<p>msRTCSIP-MobilityPolicy</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>dnsHostName</p>
<p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-풀</p></td>
<td><p>msRTCSIP-ApplicationList</p>
<p>msRTCSIP-BackEndServer</p>
<p>msRTCSIP-dnsHostName</p>
<p>msRTCSIP-PoolData</p>
<p>msRTCSIP-PoolDisplayName</p>
<p>msRTCSIP-PoolDomainFQDN</p>
<p>msRTCSIP-PoolFunctionality</p>
<p>msRTCSIP-PoolType</p>
<p>msRTCSIP-PoolVersion</p>
<p>msRTCSIP-TrustedServiceLinks</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>msRTCSIP-FrontEndServers</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-현재 상태</p></td>
<td><p>msRTCSIP-PresenceFlags</p>
<p>msRTCSIP-PresencePolicy</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 된 Mcu</p></td>
<td><p>msRTCSIP-M가공선</p>
<p>msRTCSIP-MCUVendor 공급 업체</p>
<p>msRTCSIP-RoutingPoolDN</p>
<p>msRTCSIP-Trustedm데이터</p>
<p>msRTCSIP-Trustedm의 Fqdn</p>
<p>msRTCSIP Serverversion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 프록시</p></td>
<td><p>msRTCSIP Proxydata</p>
<p>msRTCSIP-을 (를)로 하는 Proxyfqdn</p>
<p>msRTCSIP Serverversion</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 서버</p></td>
<td><p>msRTCSIP Serverdata</p>
<p>msRTCSIP-로 비트 하는 Serverfqdn</p>
<p>msRTCSIP Serverversion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 서비스</p></td>
<td><p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-라우팅 가능</p>
<p>msRTCSIP-RoutingPoolDN</p>
<p>msRTCSIP-ServerBL</p>
<p>msRTCSIP-로 비트 하는 Serverfqdn</p>
<p>msRTCSIP Serverversion</p>
<p>msRTCSIP-(비트)로가는 플래그</p>
<p>msRTCSIP-(와)로 이루어진 Serviceport</p>
<p>msRTCSIP의로이는 Servicetype</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>msRTCSIP-TrustedWebComponentsServerData</p>
<p>msRTCSIP-TrustedWebComponentsServerFQDN</p>
<p>msRTCSIP Serverversion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>msRTCSIP-WebComponentsServers</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>msRTCSIP-WebComponentsData</p>
<p>msRTCSIP-WebComponentsPoolAddress</p>
<p>msRTCSIP-ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>사용자</p></td>
<td><p>msRTCSIP-AcpInfo</p>
<p>msRTCSIP-ApplicationOptions</p>
<p>msRTCSIP-ArchivingEnabled</p>
<p>msRTCSIP-DeploymentLocator</p>
<p>msRTCSIP-FederationEnabled</p>
<p>msRTCSIP-GroupingID</p>
<p>msRTCSIP-InternetAccessEnabled</p>
<p>msRTCSIP 선</p>
<p>msRTCSIP-LineServer</p>
<p>msRTCSIP 플래그</p>
<p>msRTCSIP-OriginatorSid</p>
<p>msRTCSIP-소유자 Urn</p>
<p>msRTCSIP-PrimaryHomeServer</p>
<p>msRTCSIP-PrimaryUserAddress</p>
<p>msRTCSIP-PrivateLine</p>
<p>msRTCSIP-TargetHomeServer</p>
<p>msRTCSIP-TargetUserPolicies</p>
<p>msRTCSIP-TenantId</p>
<p>msRTCSIP-UserEnabled</p>
<p>UserExtension msRTCSIP</p>
<p>msRTCSIP-UserLocationProfile</p>
<p>msRTCSIP-UserPolicies</p>
<p>msRTCSIP-UserPolicy</p>
<p>msRTCSIP-UserRoutingGroupId</p>
<p>ProxyAddresses</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a>다른 클래스에 포함 된 클래스


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>클래스만</th>
<th>이 클래스가 포함 될 수 있습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serviceConnectionPoint</p></td>
<td><p>msRTCSIP-서버</p>
<p>msRTCSIP-PoolService</p>
<p>msRTCSIP-MCU</p>
<p>msRTCSIP-MCUFactoryService</p>
<p>msRTCSIP-WebComponents</p>
<p>msRTCSIP-WebComponentsService</p>
<p>msRTCSIP-ApplicationServerService</p>
<p>msRTCSIP-서비스</p>
<p>msRTCSIP-ConnectionPoint</p>
<p>msRTCSIP-MediationServer</p>
<p>msRTCSIP-ApplicationServer</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-서비스</p></td>
<td><p>msRTCSIP-GlobalContainer</p>
<p>msRTCSIP-풀</p>
<p>msRTCSIP-MCUFactories</p>
<p>msRTCSIP-TrustedMCUs</p>
<p>msRTCSIP-TrustedWebComponentsServers</p>
<p>msRTCSIP 프록시</p>
<p>msRTCSIP 서비스</p>
<p>msRTCSIP-ApplicationContacts</p>
<p>msRTCSIP-Location연락처 매핑</p>
<p>msRTCSIP-ConferenceDirectories</p>
<p>msRTCSIP-GlobalTopologySettings</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>msRTCSIP-도메인</p>
<p>msRTCSIP 서버</p>
<p>msRTCSIP-EdgeProxy</p>
<p>msRTCSIP-MonitoringServer</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-풀</p></td>
<td><p>msRTCSIP-풀</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>msRTCSIP-MCUFactory</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>msRTCSIP 된 Mcu</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 프록시</p></td>
<td><p>msRTCSIP 프록시</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 서비스</p></td>
<td><p>msRTCSIP 서비스</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Location연락처 매핑</p></td>
<td><p>msRTCSIP-Location연락처 매핑</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>msRTCSIP-ConferenceDirectory</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

