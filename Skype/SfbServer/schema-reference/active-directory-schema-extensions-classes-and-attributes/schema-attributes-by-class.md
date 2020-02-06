---
title: 비즈니스용 Skype 서버에서 클래스별 스키마 특성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
description: 이 섹션에서는 각 비즈니스용 Skype Server 클래스에 포함 될 수 있는 스키마 특성과 다른 클래스에 포함 될 수 있는 클래스를 나열 합니다. 모든 수업 목록과 해당 설명은 비즈니스용 Skype 서버의 스키마 클래스 및 설명을 참조 하세요. 모든 특성 및 해당 설명 목록은 비즈니스용 Skype 서버의 스키마 특성 및 설명을 참조 하세요.
ms.openlocfilehash: 93598f1cc54ec76ccc59649ec97fd7ac57cd39f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815496"
---
# <a name="schema-attributes-by-class-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 클래스별 스키마 특성
 
이 섹션에서는 각 비즈니스용 Skype Server 클래스에 포함 될 수 있는 스키마 특성과 다른 클래스에 포함 될 수 있는 클래스를 나열 합니다. 모든 수업 목록과 해당 설명은 [비즈니스용 Skype 서버의 스키마 클래스 및 설명을](schema-classes-and-descriptions.md)참조 하세요. 모든 특성 및 해당 설명 목록은 [비즈니스용 Skype 서버의 스키마 특성 및 설명을](schema-attributes-and-descriptions.md)참조 하세요.
  
## <a name="attributes-by-class"></a>클래스별 특성

|**클래스만**|**이러한 특성이 포함 될 수 있습니다.**|
|:-----|:-----|
|Contact  <br/> |msDS-SourceObjectDN  <br/> msRTCSIP-AcpInfo  <br/> msRTCSIP-ApplicationDestination  <br/> msRTCSIP-ApplicationOptions  <br/> msRTCSIP-ApplicationPrimaryLanguage  <br/> msRTCSIP-ApplicationSecondaryLanguages  <br/> msRTCSIP-ArchivingEnabled  <br/> msRTCSIP-DeploymentLocator  <br/> msRTCSIP-FederationEnabled  <br/> msRTCSIP-GroupingID  <br/> msRTCSIP-InternetAccessEnabled  <br/> msRTCSIP 선  <br/> msRTCSIP-LineServer  <br/> msRTCSIP 플래그  <br/> msRTCSIP-OriginatorSid  <br/> msRTCSIP-소유자 Urn  <br/> msRTCSIP-PrimaryHomeServer  <br/> msRTCSIP-PrimaryUserAddress  <br/> msRTCSIP-PrivateLine  <br/> msRTCSIP-ProxyAddresses  <br/> msRTCSIP-SourceObjectType  <br/> msRTCSIP-TargetHomeServer  <br/> msRTCSIP-TargetUserPolicies  <br/> msRTCSIP-TenantId  <br/> msRTCSIP-UserEnabled  <br/> UserExtension msRTCSIP  <br/> msRTCSIP-UserLocationProfile  <br/> msRTCSIP-UserPolicies  <br/> msRTCSIP-UserPolicy  <br/> msRTCSIP-UserRoutingGroupId  <br/> ProxyAddresses  <br/> |
|메일 받는 사람  <br/> |msExchUCVoiceMailSettings  <br/> msExchUserHoldPolicies  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |msRTCSIP-ApplicationServerBL  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |msRTCSIP-ApplicationList  <br/> msRTCSIP-ApplicationServerPoolLink  <br/> msRTCSIP-ExtensionData  <br/> msRTCSIP-ServerVersion  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |msRTCSIP-ConferenceDirectoryHomePool  <br/> msRTCSIP-ConferenceDirectoryId  <br/> msRTCSIP-ConferenceDirectoryTargetPool  <br/> msRTCSIP-ExtensionData  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |msRTCSIP-DefaultCWAExternalURL  <br/> msRTCSIP-DefaultCWAInternalURL  <br/> |
|msRTCSIP-도메인  <br/> |msRTCSIP-기본값  <br/> msRTCSIP-도메인 데이터  <br/> msRTCSIP-DomainName  <br/> |
|msRTCSIP-EdgeProxy  <br/> |msRTCSIP-EdgeProxyData  <br/> msRTCSIP-EdgeProxyFQDN  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |msRTCSIP-MCUData  <br/> msRTCSIP-MCUFactoryAddress  <br/> msRTCSIP-ServerVersion  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |msRTCSIP-ExtensionData  <br/> msRTCSIP-ServerVersion  <br/> msRTCSIP-TrustedServiceLinks  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |msRTCSIP-EnterpriseServices  <br/> msRTCSIP-PoolAddress  <br/> msRTCSIP-ServerData  <br/> msRTCSIP-ServerVersion  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |msRTCSIP-BackEndServer  <br/> msRTCSIP-ExtensionData  <br/> msRTCSIP-MirrorBackEndServer  <br/> msRTCSIP-ServerVersion  <br/> |
|msRTCSIP-LocalNormalization  <br/> |msRTCSIP-LocalNormalizationOptions  <br/> |
|msRTCSIP-Location연락처 매핑  <br/> |msRTCSIP-ExtensionData  <br/> msRTCSIP-MappingContact  <br/> msRTCSIP-MappingLocation  <br/> |
|msRTCSIP-LocationProfile  <br/> |msRTCSIP-ExternalAccessCode  <br/> msRTCSIP-LocationProfileOptions  <br/> |
|msRTCSIP-MCUFactory  <br/> |msRTCSIP-MCUFactoryData  <br/> msRTCSIP-MCUFactoryProviderID  <br/> msRTCSIP-MCUServers  <br/> msRTCSIP-M가공선  <br/> msRTCSIP-MCUVendor 공급 업체  <br/> msRTCSIP-PoolAddresses  <br/> msRTCSIP-ServerVersion  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |msRTCSIP-MCUFactoryPath  <br/> |
|msRTCSIP-이동성  <br/> |msRTCSIP-MobilityFlags  <br/> msRTCSIP-MobilityPolicy  <br/> |
|msRTCSIP-MonitoringServer  <br/> |dnsHostName  <br/> msRTCSIP-ExtensionData  <br/> msRTCSIP-ServerVersion  <br/> |
|msRTCSIP-풀  <br/> |msRTCSIP-ApplicationList  <br/> msRTCSIP-BackEndServer  <br/> msRTCSIP-dnsHostName  <br/> msRTCSIP-PoolData  <br/> msRTCSIP-PoolDisplayName  <br/> msRTCSIP-PoolDomainFQDN  <br/> msRTCSIP-PoolFunctionality  <br/> msRTCSIP-PoolType  <br/> msRTCSIP-PoolVersion  <br/> msRTCSIP-TrustedServiceLinks  <br/> |
|msRTCSIP-PoolService  <br/> |msRTCSIP-FrontEndServers  <br/> |
|msRTCSIP-현재 상태  <br/> |msRTCSIP-PresenceFlags  <br/> msRTCSIP-PresencePolicy  <br/> |
|msRTCSIP 된 Mcu  <br/> |msRTCSIP-M가공선  <br/> msRTCSIP-MCUVendor 공급 업체  <br/> msRTCSIP-RoutingPoolDN  <br/> msRTCSIP-Trustedm데이터  <br/> msRTCSIP-Trustedm의 Fqdn  <br/> msRTCSIP Serverversion  <br/> |
|msRTCSIP 프록시  <br/> |msRTCSIP Proxydata  <br/> msRTCSIP-을 (를)로 하는 Proxyfqdn  <br/> msRTCSIP Serverversion  <br/> |
|msRTCSIP 서버  <br/> |msRTCSIP Serverdata  <br/> msRTCSIP-로 비트 하는 Serverfqdn  <br/> msRTCSIP Serverversion  <br/> |
|msRTCSIP 서비스  <br/> |msRTCSIP-ExtensionData  <br/> msRTCSIP-라우팅 가능  <br/> msRTCSIP-RoutingPoolDN  <br/> msRTCSIP-ServerBL  <br/> msRTCSIP-로 비트 하는 Serverfqdn  <br/> msRTCSIP Serverversion  <br/> msRTCSIP-(비트)로가는 플래그  <br/> msRTCSIP-(와)로 이루어진 Serviceport  <br/> msRTCSIP의로이는 Servicetype  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |msRTCSIP-TrustedWebComponentsServerData  <br/> msRTCSIP-TrustedWebComponentsServerFQDN  <br/> msRTCSIP Serverversion  <br/> |
|msRTCSIP-WebComponentsService  <br/> |msRTCSIP-WebComponentsServers  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |msRTCSIP-WebComponentsData  <br/> msRTCSIP-WebComponentsPoolAddress  <br/> msRTCSIP-ServerVersion  <br/> |
|사용자  <br/> |msRTCSIP-AcpInfo  <br/> msRTCSIP-ApplicationOptions  <br/> msRTCSIP-ArchivingEnabled  <br/> msRTCSIP-DeploymentLocator  <br/> msRTCSIP-FederationEnabled  <br/> msRTCSIP-GroupingID  <br/> msRTCSIP-InternetAccessEnabled  <br/> msRTCSIP 선  <br/> msRTCSIP-LineServer  <br/> msRTCSIP 플래그  <br/> msRTCSIP-OriginatorSid  <br/> msRTCSIP-소유자 Urn  <br/> msRTCSIP-PrimaryHomeServer  <br/> msRTCSIP-PrimaryUserAddress  <br/> msRTCSIP-PrivateLine  <br/> msRTCSIP-TargetHomeServer  <br/> msRTCSIP-TargetUserPolicies  <br/> msRTCSIP-TenantId  <br/> msRTCSIP-UserEnabled  <br/> UserExtension msRTCSIP  <br/> msRTCSIP-UserLocationProfile  <br/> msRTCSIP-UserPolicies  <br/> msRTCSIP-UserPolicy  <br/> msRTCSIP-UserRoutingGroupId  <br/> ProxyAddresses  <br/> |
   
### <a name="classes-contained-in-other-classes"></a>다른 클래스에 포함 된 클래스

|**클래스만**|**이 클래스가 포함 될 수 있습니다.**|
|:-----|:-----|
|serviceConnectionPoint  <br/> |msRTCSIP-서버  <br/> msRTCSIP-PoolService  <br/> msRTCSIP-MCU  <br/> msRTCSIP-MCUFactoryService  <br/> msRTCSIP-WebComponents  <br/> msRTCSIP-WebComponentsService  <br/> msRTCSIP-ApplicationServerService  <br/> msRTCSIP-서비스  <br/> msRTCSIP-ConnectionPoint  <br/> msRTCSIP-MediationServer  <br/> msRTCSIP-ApplicationServer  <br/> |
|msRTCSIP-서비스  <br/> |msRTCSIP-GlobalContainer  <br/> msRTCSIP-풀  <br/> msRTCSIP-MCUFactories  <br/> msRTCSIP-TrustedMCUs  <br/> msRTCSIP-TrustedWebComponentsServers  <br/> msRTCSIP 프록시  <br/> msRTCSIP 서비스  <br/> msRTCSIP-ApplicationContacts  <br/> msRTCSIP-Location연락처 매핑  <br/> msRTCSIP-ConferenceDirectories  <br/> msRTCSIP-GlobalTopologySettings  <br/> |
|msRTCSIP-GlobalContainer  <br/> |msRTCSIP-도메인  <br/> msRTCSIP 서버  <br/> msRTCSIP-EdgeProxy  <br/> msRTCSIP-MonitoringServer  <br/> |
|msRTCSIP-풀  <br/> |msRTCSIP-풀  <br/> |
|msRTCSIP-MCUFactories  <br/> |msRTCSIP-MCUFactory  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |msRTCSIP 된 Mcu  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |msRTCSIP-TrustedWebComponentsServer  <br/> |
|msRTCSIP 프록시  <br/> |msRTCSIP 프록시  <br/> |
|msRTCSIP 서비스  <br/> |msRTCSIP 서비스  <br/> |
|msRTCSIP-Location연락처 매핑  <br/> |msRTCSIP-Location연락처 매핑  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |msRTCSIP-ConferenceDirectory  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |msRTCSIP-GlobalTopologySetting  <br/> |
   

