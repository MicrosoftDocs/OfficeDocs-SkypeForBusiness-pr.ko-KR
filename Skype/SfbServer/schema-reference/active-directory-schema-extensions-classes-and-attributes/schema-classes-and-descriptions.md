---
title: 2016의 Schema 클래스 및 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 이 섹션에서는 에서 사용하는 모든 schema 클래스에 대해 비즈니스용 Skype 서버.
ms.openlocfilehash: fbd3e3293cef72ba6592b86932639bd499464858
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829772"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>2016의 Schema 클래스 및 비즈니스용 Skype 서버
 
이 섹션에서는 에서 사용하는 모든 schema 클래스에 대해 비즈니스용 Skype 서버. 
  
## <a name="schema-classes-and-descriptions"></a>스키마 클래스 및 설명

|**클래스**|**설명**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange UM(통합 메시징) 전자 메일 받는 사람입니다.  <br/> |이 보조 클래스는 UM과 Exchange 공유됩니다.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |이 클래스는 여러 응용 프로그램 대화 상대에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.  <br/> |Microsoft Office Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-ApplicationServer  <br/> |이 클래스는 UCAS(통합 통신 응용 프로그램 서비스) 인스턴스의 서비스 제어 지점에 대한 항목을 포함하고 있습니다.  <br/> |Office Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |이 클래스는 특정 풀에서 응용 프로그램 서비스로의 연결 기능을 제공합니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |msRTCSIP-ApplicationServer에 대한 이 보조 클래스는 응용 프로그램 서비스의 인스턴스에 대한 설정을 나타내는 특성을 보유합니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-Archive(사용되지 않음)  <br/> |msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 보관과 관련된 모든 설정을 포함하고 있습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-ArchivingServer(사용되지 않음)  <br/> |이 클래스는 단일 인스턴트 메시징 보관 서버를 나타냅니다. 이 클래스의 인스턴스는 컴퓨터(예: 인스턴트 메시징 보관 서비스가 설치된 컴퓨터)가 인스턴트 메시징 보관 서버로 활성화될 때 만들어집니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |이 클래스는 전화 회의 디렉터리의 여러 인스턴스에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |이 클래스는 특정 전화 회의 디렉터리에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |컴퓨터를 컴퓨터의 실행 서버로 지정하는 일반 SCP(서비스 제어 지점)비즈니스용 Skype 서버.  <br/> |Lync 2010의 새로운  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |이 보조 클래스는 비즈니스용 Skype Web App 뱅크에 대한 설정을 보유합니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-Domain  <br/> |이 클래스는 SIP 등록자의 구성된 도메인을 정의하는 특성을 포함하고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |이 클래스 컨테이너는 단일 액세스 에지 서비스를 표현합니다. 액세스 에지 서비스는 경계 네트워크에 배포됩니다. 고객은 일반적으로 경계 네트워크에서 Active Directory 도메인 서비스 액세스를 허용하지 않습니다. 액세스 에지 서비스의 인스턴스는 인트라넷의 Active Directory 네트워크에 가입되지 않습니다. 따라서 액세스 프록시는 자동으로 AD DS에 등록되지 않습니다. 관리자는 AD DS에서 각 액세스 에지 서비스의 인스턴스가 존재하도록 수동으로 구성해야 합니다.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |msRTCSIP-MCU에 대한 이 보조 클래스는 회의 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |Microsoft Office Communications Server 2007의 새로운  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |msRTCSIP-MediationServer에 대한 이 보조 클래스는 중재 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |Office Communications Server 2007의 새로운 정보입니다.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |msRTCSIP-Server에 대한 이 보조 클래스는 SIP 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 페더레이션과 관련된 모든 설정을 포함하고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |이 클래스는 배포 전반에 적용되는 모든 비즈니스용 Skype 서버 있습니다.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy(사용되지 않음)  <br/> |이 클래스는 Communications Server Office 정책 하나만 나타내는 클래스입니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |로컬 전역 토폴로지 설정 개체입니다.  <br/> |Lync Server 2010의 새로운  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |전역 토폴로지 설정 개체를 포함할 컨테이너입니다.  <br/> |Lync Server 2010의 새로운  <br/> |
|msRTCSIP-LocalNormalization  <br/> |이 클래스는 위치 정규화 규칙의 인스턴스를 나타내는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |이 클래스는 회의 도우미 애플리케이션 회의 전화 번호를 지역별로 분류하는 데 사용되는 특성을 보유합니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |이 클래스는 위치 대화 상대 매핑의 여러 인스턴스에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-LocationProfile  <br/> |이 클래스는 특정 위치 프로필을 나타내는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles(사용되지 않음)  <br/> |이 클래스는 여러 위치 프로필에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-LocalNormalizations(사용되지 않음)  <br/> |이 클래스는 여러 로컬 정규화 규칙에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-MCU  <br/> |이 클래스는 단일 회의 서버를 나타냅니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-MCUFactories  <br/> |이 클래스는 여러 msRTCSIP-MCUFactory 클래스를 포함하며 자체적으로 특성을 포함하지는 않습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-MCUFactory  <br/> |이 클래스는 단일 미디어 유형에 대한 회의 서버 센터를 나타내는 컨테이너입니다. 이 특정 유형 및 공급업체에 대한 첫 번째 회의 서버가 활성화될 경우 이 클래스의 인스턴스가 만들어집니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |이 클래스는 특정 풀에서 해당 회의 서버 센터까지의 연결을 제공합니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-MediationServer  <br/> |이 클래스는 중재 서버의 서비스 제어 지점에 대한 항목을 포함하고 있습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-Meeting(사용되지 않음)  <br/> |msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 구성 가능한 모임 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-Mobility  <br/> |전역 모바일 설정을 저장하는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |이 클래스는 단일 모니터링 서버의 설정을 나타내는 특성을 보유합니다.  <br/> |Communications Server 2007 R2의 새로운  <br/> |
|msRTCSIP-PhoneRoute(사용되지 않음)  <br/> |이 클래스는 특정 게이트웨이 또는 게이트웨이 집합에 대한 최소 비용 경로의 인스턴스를 나타내는 컨테이너입니다. 모든 엔터프라이즈 풀 또는 Standard Edition을 실행하는 서버는 가장 비용 효과적인 방법으로 발신 전화를 PSTN(공중 전화망)으로 라우팅하기 위해 이 정보를 사용합니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-PhoneRoutes(사용되지 않음)  <br/> |이 클래스는 여러 최소 비용 경로에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-Policies(사용되지 않음)  <br/> |이 클래스는 여러 Lync Server 정책 클래스를 보유하며 자체적으로 특성을 가지고 있지 않습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-Pool  <br/> |이 클래스는 단일 풀을 비즈니스용 Skype 서버 있습니다.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |이 클래스는 여러 비즈니스용 Skype 서버 풀을 보유하며 자체적으로 특성이 없습니다.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |이 클래스는 풀의 서비스 제어 지점을 나타냅니다. 풀에서 호스팅되는 사용자는 이 클래스의 인스턴스를 가리키는 msRTCSIP-PrimaryHomeServer 특성을 가지고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |전역 현재 상태 설정을 저장하는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 SIP 등록자 서버에서 유지 관리하는 사용자 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage(사용되지 않음)  <br/> |이 클래스는 전화 경로 사용의 인스턴스를 나타내는 컨테이너입니다. 전화 경로 사용 클래스는 특성 필드 및 설명 필드로 구성됩니다. 특정 필드는 사용 유형을 정의합니다. 설명 필드를 사용하면 관리자는 전화 경로에서 이 특성의 사용을 설명할 수 있습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-RouteUsages(사용되지 않음)  <br/> |이 클래스는 msRTCSIP-RouteUsage 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-Search  <br/> |msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 검색 결과의 범위를 제한 및 제어하는 특성을 포함하고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |이 클래스는 서버가 실행되는 단일 서버를 비즈니스용 Skype 서버.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |이 클래스는 전역 설정 컨테이너 및 msRTCSIP-Domain 개체를 포함하고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |이 클래스는 트러스트된 회의 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-TrustedMCUS  <br/> |이 클래스는 msRTCSIP-TrustedMCU 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-TrustedProxies  <br/> |이 클래스는 여러 msRTCSIP-TrustedProxy 클래스를 포함하며 자체적으로 특성을 포함하지는 않습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-TrustedProxy  <br/> |이 클래스는 프록시 서버를 실행하는 서버를 나타내는 컨테이너입니다. AD DS에 가입된 컴퓨터에서 새 프록시 서버를 활성화할 경우 이 클래스의 인스턴스가 만들어집니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-TrustedServer  <br/> |이 클래스는 트러스트된 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |이 클래스는 GRUU(Globally Routable User Agent URI) 주소를 사용하여 라우팅할 수 있는 트러스트된 서비스를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는 사용자가 신뢰할 수 있는 새 서버를 활성화하면 비즈니스용 Skype 서버 생성됩니다. 이 트러스트된 서버는 Active Directory 도메인에 가입해야 합니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-TrustedServices  <br/> |이 클래스는 여러 GRUU 서버에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |이 클래스는 트러스트된 웹 구성 요소에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |이 클래스는 msRTCSIP-TrustedWebComponentServer 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-UnifiedCommunications(사용되지 않음)  <br/> |msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 통합 통신과 관련된 특성을 포함하고 있습니다.  <br/> |Lync Server 2010에서 사용되지 않습니다.  <br/> |
|msRTCSIP-WebComponents  <br/> |이 클래스는 IIS(Internet Information Server)의 서비스 제어 지점을 포함하고 있으며 서버를 웹 구성 요소 서버로 식별합니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-WebComponentsService  <br/> |이 클래스는 특정 풀에서 해당 풀이 사용하는 웹 구성 요소까지의 연결을 제공합니다.  <br/> |Communications Server 2007의 새로운  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |msRTCSIP-WebComponents에 대한 이 보조 클래스는 웹 구성 요소에 대한 설정을 나타내는 특성을 포함하고 있습니다.  <br/> |Communications Server 2007의 새로운  <br/> |
   

