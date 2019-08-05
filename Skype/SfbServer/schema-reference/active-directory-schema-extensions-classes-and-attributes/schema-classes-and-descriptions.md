---
title: 비즈니스용 Skype 서버의 스키마 클래스 및 설명
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 이 섹션에서는 비즈니스용 Skype 서버에서 사용 되는 모든 스키마 클래스에 대해 설명 합니다.
ms.openlocfilehash: 6d27ff464bcd4613f12180b8f263686c9cc04bcd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196802"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 스키마 클래스 및 설명
 
이 섹션에서는 비즈니스용 Skype 서버에서 사용 되는 모든 스키마 클래스에 대해 설명 합니다. 
  
## <a name="schema-classes-and-descriptions"></a>스키마 클래스 및 설명

|**클래스만**|**설명**|**메모**|
|:-----|:-----|:-----|
|메일 받는 사람  <br/> |Exchange UM (통합 메시징) 전자 메일 받는 사람입니다.  <br/> |이 보조 클래스는 Exchange UM과 공유 됩니다.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |이 클래스는 여러 응용 프로그램 대화 상대에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.  <br/> |Microsoft Office Communications Server 2007 R2의 새로운 방법입니다.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |이 클래스는 통합 커뮤니케이션 응용 프로그램 서비스 (c)의 인스턴스에 대 한 서비스 제어 지점의 항목을 보유 합니다.  <br/> |Office Communications Server 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |이 클래스는 특정 풀과 해당 응용 프로그램 서비스의 연결을 제공 합니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |이 보조 클래스에는 응용 프로그램 서비스의 인스턴스에 대 한 설정을 나타내는 특성이 msRTCSIP-ApplicationServer에 포함 됩니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-보관 (구식)  <br/> |이 보조 클래스를 msRTCSIP-GlobalContainer에는 보관에 관련 된 모든 설정이 포함 되어 있습니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-ArchivingServer (구식)  <br/> |이 클래스는 단일 인스턴트 메시징 보관 서버를 나타냅니다. 이 클래스의 인스턴스는 메신저 대화 서비스가 설치 된 컴퓨터와 같은 인스턴트 메시징 보관 서버로 컴퓨터가 활성화 될 때 만들어집니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |이 클래스는 회의 디렉터리의 여러 인스턴스에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |이 클래스는 특정 회의 디렉터리에 대 한 설정을 나타내는 특성을 보유 합니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |컴퓨터를 비즈니스용 Skype 서버를 실행 하는 서버로 지정 하는 SCP (일반 서비스 제어 지점)  <br/> |Lync 2010의 새로운 방법.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |이 보조 클래스에는 비즈니스용 Skype Web App 은행에 대 한 설정이 포함 되어 있습니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-도메인  <br/> |이 클래스에는 SIP 등록자의 구성 된 도메인을 정의 하는 특성이 포함 됩니다.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |이 클래스 컨테이너는 단일 액세스에 지 서비스를 나타냅니다. 경계 네트워크에 액세스에 지 서비스가 배포 되 고 일반적으로 경계 네트워크에서 Active Directory 도메인 서비스 액세스를 허용 하지 않기 때문에 액세스에 지 서비스 인스턴스가 인트라넷의 Active Directory 네트워크에 가입 되어 있지 않습니다. 따라서 Access 프록시는 AD DS에 자동으로 등록 되지 않습니다. 관리자는 AD DS에 각 액세스에 지 서비스 인스턴스의 존재를 수동으로 구성 해야 합니다.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |MsRTCSIP-MCU에 대 한이 보조 클래스는 회의 서버의 설정을 나타내는 특성을 보유 합니다.  <br/> |Microsoft Office 통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |MsRTCSIP-MediationServer에 대 한이 보조 클래스는 중재 서버의 설정을 나타내는 특성을 보유 합니다.  <br/> |Office Communications Server 2007의 새로운 방법.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |MsRTCSIP에 대 한이 보조 클래스는 SIP 서버 설정을 나타내는 특성을 보유 합니다.  <br/> |-  <br/> |
|msRTCSIP-페더레이션  <br/> |MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 페더레이션과 관련 된 모든 설정을 저장 합니다.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |이 클래스에는 비즈니스용 Skype 서버 배포 전체에 적용 되는 모든 설정이 포함 되어 있습니다.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (구식)  <br/> |이 클래스는 단일 Office 커뮤니케이션 서버 모임 정책을 나타냅니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |로컬 전역 토폴로지 설정 개체입니다.  <br/> |Lync Server 2010의 새로운 방법.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |전역 토폴로지 설정 개체를 보관할 컨테이너입니다.  <br/> |Lync Server 2010의 새로운 방법.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |이 클래스는 위치 정규화 규칙의 인스턴스를 나타내는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-Location연락처 매핑  <br/> |이 클래스는 회의 수행자 응용 프로그램에서 생성 되며 전화 회의 전화 번호를 지역별로 분류 하는 데 사용 되는 특성을 보유 합니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-Location연락처 매핑  <br/> |이 클래스는 위치 대화 매핑의 여러 인스턴스에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-LocationProfile  <br/> |이 클래스는 특정 위치 프로필을 나타내는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (구식)  <br/> |이 클래스는 여러 위치 프로필에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-LocalNormalizations (구식)  <br/> |이 클래스는 여러 로컬 정규화 규칙에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-MCU  <br/> |이 클래스는 단일 회의 서버를 나타냅니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-MCUFactories  <br/> |이 클래스는 여러 msRTCSIP MCUFactory 클래스를 보유 하 고 있으며 특성 자체를 포함 하지 않습니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-MCUFactory  <br/> |이 클래스는 단일 미디어 형식에 대 한 회의 서버 팩토리를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는이 특정 유형 및 공급 업체에 대 한 첫 번째 회의 서버가 활성화 될 때 만들어집니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |이 클래스는 특정 풀과 해당 하는 회의 서버 팩터리에 대 한 연결을 제공 합니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-MediationServer  <br/> |이 클래스는 중재 서버에 대 한 서비스 제어 지점의 항목을 보유 합니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-모임 (구식)  <br/> |MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 구성 가능한 모임 설정을 나타내는 특성을 보유 합니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-이동성  <br/> |전역 이동성 설정을 저장 하는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |이 클래스에는 단일 모니터링 서버의 설정을 나타내는 특성이 포함 됩니다.  <br/> |통신 서버 2007 R2의 새로운 방법  <br/> |
|msRTCSIP-PhoneRoute (구식)  <br/> |이 클래스는 게이트웨이 또는 게이트웨이 집합에 대 한 최소 순위의 경로의 인스턴스를 나타내는 컨테이너입니다. 이 정보는 모든 엔터프라이즈 풀 또는 표준 버전을 실행 하는 서버에서 가장 비용 효율적인 방법으로 PSTN (공개 통신 네트워크)로 나가는 호출을 라우팅하는 데 사용 됩니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-PhoneRoutes (구식)  <br/> |이 클래스는 최소 순위의 여러 경로에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-정책 (구식)  <br/> |이 클래스는 여러 Lync Server 정책 클래스를 보유 하며 특성 자체는 없습니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-풀  <br/> |이 클래스는 비즈니스용 Skype 서버 풀 하나를 나타냅니다.  <br/> |-  <br/> |
|msRTCSIP-풀  <br/> |이 클래스는 비즈니스용 Skype 서버 풀을 여러 개 보유 하 고 있지만 특성 자체를 포함 하지 않습니다.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |이 클래스는 풀의 서비스 제어 포인트 서비스 제어점을 나타냅니다. 풀에 호스팅되는 사용자의 msRTCSIP-PrimaryHomeServer 특성 점이이 클래스의 인스턴스에 해당 합니다.  <br/> |-  <br/> |
|msRTCSIP-현재 상태  <br/> |전역 현재 상태 설정을 저장 하는 컨테이너입니다.  <br/> |-  <br/> |
|msRTCSIP-등록자  <br/> |MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 SIP 등록자 서버에서 유지 관리 하는 사용자 설정을 나타내는 특성을 보유 합니다.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (구식)  <br/> |이 클래스는 전화 경로 사용의 인스턴스를 나타내는 컨테이너입니다. 전화 경로 사용 클래스는 특성 필드와 설명 필드로 구성 됩니다. 특성 필드는 사용 유형을 정의 합니다. 관리자는 설명 필드를 사용 하 여 전화 라우트에이 특성에 대 한 사용량을 설명할 수 있습니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-RouteUsages (구식)  <br/> |이 클래스는 msRTCSIP-RouteUsage 클래스의 여러 인스턴스를 포함 하며 특성 자체는 포함 하지 않습니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-검색  <br/> |MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 검색 결과 범위를 제한 하 고 제어 하는 특성을 보유 합니다.  <br/> |-  <br/> |
|msRTCSIP-서버  <br/> |이 클래스는 비즈니스용 Skype 서버를 실행 하는 단일 서버를 나타냅니다.  <br/> |-  <br/> |
|msRTCSIP-서비스  <br/> |이 클래스에는 전역 설정 컨테이너 및 msRTCSIP 도메인 개체가 포함 됩니다.  <br/> |-  <br/> |
|msRTCSIP 된 Mcu  <br/> |이 클래스에는 신뢰할 수 있는 회의 서버의 설정을 나타내는 특성이 포함 됩니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |이 클래스에는 msRTCSIP로 거는 Mcu 클래스의 여러 인스턴스가 저장 되며 특성 자체는 없습니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP 프록시  <br/> |이 클래스는 여러 msRTCSIP 프록시 클래스를 보유 하며 특성 자체를 포함 하지 않습니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP 프록시  <br/> |이 클래스는 프록시 서버를 실행 하는 서버를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는 AD DS에 연결 된 컴퓨터에서 새 프록시 서버를 활성화할 때 만들어집니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP 서버  <br/> |이 클래스는 신뢰할 수 있는 서버에 대 한 설정을 나타내는 특성을 보유 합니다.  <br/> |-  <br/> |
|msRTCSIP 서비스  <br/> |이 클래스는 전역적으로 라우팅할 수 있는 GRUU (사용자 에이전트 URI) 주소를 사용 하 여 라우팅할 수 있는 서비스를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는 비즈니스용 Skype 서버에서 신뢰 하는 새 서버가 활성화 될 때 만들어집니다. 이 신뢰할 수 있는 서버는 Active Directory 도메인에 가입 되어 있어야 합니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP 서비스  <br/> |이 클래스는 여러 GRUU 서버에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |이 클래스에는 신뢰할 수 있는 웹 구성 요소에 대 한 설정을 나타내는 특성이 포함 됩니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |이 클래스는 msRTCSIP Webcomponentserver 클래스의 여러 인스턴스를 보유 하며 특성 자체를 포함 하지 않습니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-UnifiedCommunications (구식)  <br/> |MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 통합 커뮤니케이션 관련 특성을 유지 합니다.  <br/> |Lync Server 2010에서 더 이상 사용 되지 않습니다.  <br/> |
|msRTCSIP-WebComponents  <br/> |이 클래스는 IIS (Internet Information Server)에 대 한 서비스 제어 포인트 서비스 제어 지점을 보유 합니다. 서버를 웹 구성 요소 서버로 식별 합니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |이 클래스는 특정 풀과 풀에서 사용할 웹 구성 요소에 대 한 연결을 제공 합니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |MsRTCSIP 구성 요소에 대 한이 보조 클래스는 웹 구성 요소 설정을 나타내는 특성을 보유 합니다.  <br/> |통신 서버 2007의 새로운 방법.  <br/> |
   

