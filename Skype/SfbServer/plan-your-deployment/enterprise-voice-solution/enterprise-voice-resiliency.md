---
title: 비즈니스용 Skype 서버 Enterprise Voice 복원력 계획
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: 중앙 사이트와 분기 사이트 모두에서 비즈니스용 Skype 서버 Enterprise Voice 음성 복원력을 지원하는 방법을 알아봅니다. 분기 사이트 옵션에는 Survivable Branch Appliance 또는 Survivable Branch Server 배포가 포함됩니다.
ms.openlocfilehash: 493f599f7fbec2a67efaaf59851fd7c2f3b2d144
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675480"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>비즈니스용 Skype 서버 Enterprise Voice 복원력 계획

중앙 사이트와 분기 사이트 모두에서 비즈니스용 Skype 서버 Enterprise Voice 음성 복원력을 지원하는 방법을 알아봅니다. 분기 사이트 옵션에는 Survivable Branch Appliance 또는 Survivable Branch Server 배포가 포함됩니다.

음성 복원력은 WAN(광역 네트워크) 오류 또는 다른 원인을 통해 비즈니스용 Skype 서버 호스트하는 중앙 사이트를 사용할 수 없게 되면 사용자가 계속 전화를 걸고 받을 수 있는 기능을 나타냅니다. 중앙 사이트가 실패할 경우에는 Enterprise Voice 서비스에서 백업 사이트에 대해 원활한 장애 조치를 수행하여 중단 없이 작업을 계속 수행하도록 해야 합니다. WAN 실패의 경우 분기 사이트 통화가 로컬 PSTN 게이트웨이로 리디렉션되어야 합니다. 이 섹션에서는 중앙 사이트 또는 WAN 실패 시 음성 복구 기능 계획에 대해 설명합니다.

## <a name="central-site-resiliency"></a>중앙 사이트 복원력

점점 많은 기업에서 전 세계에 여러 사이트를 확산시키고 있습니다. 응급 서비스 유지 관리, 지원 센터 액세스 및 중앙 사이트가 서비스가 중단된 경우 중요한 비즈니스 작업을 수행할 수 있는 기능은 모든 Enterprise Voice 복원력 솔루션에 필수적입니다. 중앙 사이트가 사용할 수 없게 된 경우 다음 조건을 충족해야 합니다.

- 음성 장애 조치가 제공되어야 합니다.

- 일반적으로 중앙 사이트의 프런트 엔드 풀에 등록하는 사용자는 대체 프런트 엔드 풀에 등록할 수 있어야 합니다. 이 작업은 여러 DNS SRV 레코드를 만들어 수행할 수 있으며, 각 레코드는 각 중앙 사이트의 디렉터 풀 또는 프런트 엔드 풀로 확인됩니다. SRV 레코드의 우선 순위와 가중치를 조정하여 해당 중앙 사이트에서 서비스를 제공하는 사용자가 다른 SRV 레코드보다 해당 디렉터 및 프런트 엔드 풀을 앞서게 할 수 있습니다.

- 다른 사이트에 있는 사용자와의 통화가 PSTN으로 다시 라우팅되어야 합니다.

이 항목에서는 중앙 사이트 음성 복구의 보안을 유지하는 권장 솔루션에 대해 설명합니다.

### <a name="architecture-and-topology"></a>아키텍처 및 토폴로지

중앙 사이트에서 음성 복원력을 계획하려면 비즈니스용 Skype 서버 등록 기관에서 음성 장애 조치(failover)를 사용하도록 설정하는 데 사용되는 중앙 역할에 대한 기본적인 이해가 필요합니다. 비즈니스용 Skype 서버 등록 기관은 클라이언트 등록 및 인증을 사용하도록 설정하고 라우팅 서비스를 제공하는 서비스입니다. 모든 Standard Edition 서버, 프런트 엔드 서버, 디렉터 또는 Survivable Branch Appliance에서 실행됩니다. 등록자 풀은 프런트 엔드 풀에서 실행되고 동일한 사이트에 상주하는 등록자 서비스로 구성됩니다. 비즈니스용 Skype 클라이언트는 다음 검색 메커니즘을 통해 프런트 엔드 풀을 검색합니다.

1. DNS SRV 레코드

2. 자동 검색 웹 서비스

3. DHCP 옵션 120

비즈니스용 Skype 클라이언트가 프런트 엔드 풀에 연결한 후 부하 분산 장치에서 풀의 프런트 엔드 서버 중 하나로 전달됩니다. 그러면 프런트 엔드 서버가 클라이언트를 풀의 기본 등록 기관으로 리디렉션합니다.

Enterprise Voice 사용하도록 설정된 각 사용자는 해당 사용자의 기본 등록자 풀이 되는 특정 등록자 풀에 할당됩니다. 지정된 사이트에서 일반적으로 수백 또는 수천 명의 사용자가 하나의 기본 등록자 풀을 공유합니다. 현재 상태, 회의 또는 장애 조치를 중앙 사이트에 의존하는 분기 사이트 사용자의 중앙 사이트 리소스 사용을 계산하려면 각 분기 사이트 사용자를 중앙 사이트에 등록된 사용자로 간주하는 것이 좋습니다. 현재는 Survivable Branch Appliance에 등록된 사용자를 포함하여 분기 사이트 사용자 수에 제한이 없습니다.

중앙 사이트 실패 시 음성 복구를 지원하려면 기본 등록자 풀의 지정된 단일 백업 등록자 풀이 다른 사이트에 있어야 합니다. 토폴로지 작성기 복원력 설정을 사용하여 백업을 구성할 수 있습니다. 두 사이트 간에 복구 가능한 WAN 링크가 있는 경우 기본 등록자 풀을 더 이상 사용할 수 없는 사용자는 자동으로 백업 등록자 풀에 연결됩니다.

다음 단계에서는 클라이언트 검색 및 등록 프로세스에 대해 설명합니다.

1. 클라이언트는 DNS SRV 레코드를 통해 비즈니스용 Skype 서버 검색합니다. 비즈니스용 Skype 서버 DNS SRV 쿼리에 둘 이상의 FQDN을 반환하도록 DNS SRV 레코드를 구성할 수 있습니다. 예를 들어 Contoso라는 회사에 세 개의 중앙 사이트(북미, 유럽 및 아시아 태평양)가 있고 각 중앙 사이트에 디렉터 풀이 있는 경우 DNS SRV 레코드는 각 위치의 디렉터 풀 FQDN을 가리킬 수 있습니다. 위치 중 하나의 디렉터 풀을 사용할 수 있는 한 클라이언트는 첫 번째 홉 비즈니스용 Skype 서버 연결할 수 있습니다.

    > [!NOTE]
    > 디렉터 풀 사용은 선택 사항입니다. 프런트 엔드 풀을 대신 사용할 수 있습니다.

2. 디렉터 풀은 사용자의 기본 등록자 풀 및 백업 등록자 풀에 대해 비즈니스용 Skype 클라이언트에 알릴 수 있습니다.

3. 비즈니스용 Skype 클라이언트는 먼저 사용자의 기본 등록 기관 풀에 연결을 시도합니다. 기본 등록자 풀을 사용할 수 있는 경우 등록자가 등록을 수락합니다. 주 등록자 풀을 사용할 수 없는 경우 비즈니스용 Skype 클라이언트가 백업 등록자 풀에 연결을 시도합니다. 백업 등록자 풀을 사용할 수 있고 사용자의 기본 등록자 풀을 사용할 수 없다고 결정한 경우(지정된 장애 조치(failover) 간격에 대한 하트비트 부족을 감지하여) 백업 등록 기관 풀은 사용자의 등록을 허용합니다. 백업 등록 기관에서 주 등록자를 다시 사용할 수 있음을 감지한 후 백업 등록자 풀은 장애 조치(failover) 클라이언트를 기본 풀로 리디렉션합니다.

### <a name="requirements-and-recommendations"></a>요구 사항 및 권장 사항

다음은 대부분의 조직에 적절한 중앙 사이트 음성 복구 구현에 대한 요구 사항 및 권장 사항입니다.

- 사이트의 기본 및 백업 등록자 풀이 복구 가능한 WAN 링크로 연결되어야 합니다.

- 각 중앙 사이트에 하나 이상의 등록자로 구성된 등록자 풀이 있어야 합니다.

- 각 등록자 풀은 DNS 부하 분산, 하드웨어 부하 분산 또는 둘 다를 사용하여 부하 분산되어야 합니다. 부하 분산 구성 계획에 대한 자세한 내용은 [비즈니스용 Skype 대한 부하 분산 요구 사항을](../../plan-your-deployment/network-requirements/load-balancing.md) 참조하세요.

- 각 사용자는 비즈니스용 Skype 서버 Management Shell **set-CsUser** cmdlet 또는 비즈니스용 Skype 서버 제어판 사용하여 주 등록자 풀에 할당되어야 합니다.

- 기본 등록자 풀의 단일 백업 등록자 풀이 다른 중앙 사이트에 있어야 합니다.

- 기본 등록자 풀이 백업 등록자 풀로 장애 조치되도록 구성되어야 합니다. 기본적으로 기본 등록자는 300초 간격 후 백업 등록자 풀로 장애 조치되도록 설정됩니다. 비즈니스용 Skype 서버 토폴로지 작성기를 사용하여 이 간격을 변경할 수 있습니다.

- 장애 조치(failover) 경로를 구성합니다. 경로를 구성할 때 기본 경로에 지정된 게이트웨이에서 다른 사이트에 있는 게이트웨이를 지정합니다.

- 중앙 사이트에 기본 관리 서버가 포함되어 있고 사이트가 장기간 중단될 가능성이 있는 경우 백업 사이트에 관리 도구를 다시 설치해야 합니다. 그렇지 않으면 관리 설정을 변경할 수 없습니다.

### <a name="dependencies"></a>의존 관계

비즈니스용 Skype 서버 음성 복원력을 보장하기 위해 다음 인프라 및 소프트웨어 구성 요소에 따라 달라집니다.

|**구성 요소** <br/> |**기능** <br/> |
|:-----|:-----|
|DNS  <br/> |SRV 레코드 및 A 레코드에서 서버 간 연결 및 서버와 클라이언트 간 연결 확인  <br/> |
|Exchange와 EWV(Exchange 웹 서비스)  <br/> |대화 상대 저장, 일정 데이터  <br/> |
|Exchange 통합 메시징과 Exchange 웹 서비스  <br/> |통화 기록, 음성 메일 목록, 음성 메일  <br/> |
|DHCP 옵션 120  <br/> |DNS SRV를 사용할 수 없는 경우 클라이언트에서는 DHCP 옵션 120을 사용하여 등록자를 검색합니다. 이렇게 하려면 DHCP 서버를 구성하거나 DHCP를 사용하도록 설정해야 비즈니스용 Skype 서버.  <br/> |

### <a name="survivable-voice-features"></a>지속 가능한 음성 기능

위의 요구 사항 및 권장 사항이 구현된 경우 백업 등록자 풀에서 다음 음성 기능을 제공합니다.

- 아웃바운드 PSTN 통화

- 인바운드 PSTN 통화(전화 통신 서비스 공급자가 백업 사이트로의 장애 조치 기능을 지원하는 경우)

- 같은 사이트에 있는 사용자 및 서로 다른 두 사이트 간의 엔터프라이즈 통화

- 통화 보류, 검색 및 전송을 포함한 기본적인 통화 처리

- 같은 사이트에 있는 사용자 간의 오디오/비디오 공유 및 양자 간 인스턴트 메시징

- 착신 전환, 동시 끝점 신호 울림, 통화 위임 및 팀 통화 서비스(통화 위임의 두 당사자 또는 모든 팀 구성원이 같은 사이트에 구성된 경우에만)

- 기존 전화 및 클라이언트는 계속 작동합니다.

- CDR(통화 정보 기록)

- 인증 및 권한 부여

다음 음성 기능은 기본 중앙 사이트의 서비스가 중단된 경우 구성 방법에 따라 작동하거나 작동하지 않을 수 있습니다.

- 음성 메일 보관 및 검색

    기본 중앙 사이트의 서비스가 중단된 경우 Exchange UM을 사용하려면 다음 중 하나를 수행해야 합니다.

  - 중앙 사이트의 Exchange UM 서버가 다른 사이트에 있는 백업 Exchange UM 서버를 가리키도록 DNS SRV 레코드를 변경합니다.

  - 각 사용자의 Exchange UM 다이얼 플랜을 구성하여 중앙 사이트와 백업 사이트 모두에 Exchange UM 서버를 포함하지만 백업 Exchange UM 서버를 사용하지 않도록 지정합니다. 기본 사이트를 사용할 수 없게 되면 Exchange 관리자가 백업 사이트의 Exchange UM 서버를 사용하도록 표시해야 합니다.

    위의 솔루션 중 어느 것도 가능하지 않은 경우 중앙 사이트를 사용할 수 없는 경우 Exchange UM을 사용할 수 없습니다.

- 모든 유형의 회의

    백업 사이트로 장애 조치된 사용자는 풀을 사용할 수 있는 이끌이가 만들거나 호스팅하는 전화 회의에 참가할 수 있지만 더 이상 사용할 수 없는 자신의 기본 풀에서 전화 회의를 만들거나 호스팅할 수는 없습니다. 마찬가지로 다른 사용자는 영향을 받는 사용자의 기본 풀에서 호스트되는 회의에 참가할 수 없습니다.

다음 음성 기능은 기본 중앙 사이트의 서비스가 중단된 경우 작동하지 않습니다.

- 회의 자동 길잡이

- 현재 상태 및 DND 기반 라우팅

- 착신 전환 설정 업데이트

- 응답 그룹 서비스 및 통화 대기

- 새 전화 및 클라이언트 프로비전

- 주소록 웹 검색

## <a name="branch-site-resiliency"></a>분기 사이트 복원력

분기 사이트 복원력, 즉 고가용성 Enterprise Voice 서비스를 제공하려는 경우 다음 세 가지 옵션을 사용할 수 있습니다.

- Survivable Branch Appliance

- Survivable Branch Server

- 분기 사이트의 전체 비즈니스용 Skype 서버 배포

이 가이드를 참조하여 조직에 가장 적합한 복구 솔루션을 평가하고, 해당 복구 솔루션을 기반으로 하여 사용할 PSTN 연결 솔루션을 평가할 수 있습니다. 또한 이 가이드에 나와 있는 필수 구성 요소 및 기타 계획 고려 사항에 대한 설명을 참조하여 선택한 솔루션의 배포를 준비할 수 있습니다.

### <a name="branch-site-resiliency-features"></a>분기 사이트 복원 기능

분기 사이트 복원력을 제공하는 경우 중앙 사이트에 대한 분기 사이트의 WAN 연결이 실패하거나 중앙 사이트에 연결할 수 없는 경우 다음 음성 기능을 계속 사용할 수 있어야 합니다.

- 인바운드 및 아웃바운드 PSTN(공중 전화망) 통화

- 같은 사이트에 있는 사용자 및 서로 다른 두 사이트 간의 엔터프라이즈 통화

- 통화 보류, 검색 및 전송을 포함한 기본적인 통화 처리

- 두 사용자 간 인스턴트 메시징

- 호출 전달, 엔드포인트 동시 울림, 통화 위임 및 팀 호출 서비스이지만 위임자 및 대리인(예: 관리자 및 관리자 관리자) 또는 모든 팀 구성원이 동일한 사이트에서 구성된 경우에만

- CDR(통화 정보 기록)

- 회의 자동 전화 교환을 사용한 PSTN 전화 접속 회의

- 음성 메일 기능: 음성 메일 다시 라우팅 설정을 구성한 경우.

- 사용자 인증 및 권한 부여

복원력 솔루션이 분기 사이트에서 본격적인 비즈니스용 Skype 서버 배포인 경우에만 다음 기능을 사용할 수 있습니다.

- IM, 웹 및 A/V 회의

- 현재 상태 및 DND(방해 금지) 기반 라우팅(DND가 활성화된 내선의 경우 통화의 벨울림이 방지됨)

- 착신 전환 설정 업데이트

- 응답 그룹 애플리케이션 및 통화 대기 애플리케이션

- 새 휴대폰 및 클라이언트를 프로비전하지만 Active Directory Domain Services 분기 사이트에 있는 경우에만 프로비전합니다.

- E9-1-1(고급 9-1-1)

    E9-1-1이 배포되고 WAN 링크가 다운되어 중앙 사이트의 SIP 트렁크를 사용할 수 없는 경우 Survivable Branch Appliance는 E9-1-1 호출을 로컬 분기 게이트웨이로 라우팅합니다. 이 기능을 사용하도록 설정하려면 분기 사이트 사용자의 음성 정책은 WAN 오류가 발생할 경우 로컬 게이트웨이에 호출을 라우팅해야 합니다.

> [!NOTE]
> SBA(생존 가능한 지점)는 XMPP에서 지원되지 않습니다. SBA 구성에 있는 사용자는 IM을 보내거나 XMPP 연락처를 사용하여 현재 상태를 볼 수 없습니다.

### <a name="branch-site-resiliency-solutions"></a>분기 사이트 복원력 솔루션

조직에 분기 사이트 복원력을 제공하는 데는 명백한 이점이 있습니다. 특히 중앙 사이트에 대한 연결이 끊어지면 분기 사이트 사용자는 계속해서 Enterprise Voice 서비스 및 음성 메일을 갖게 됩니다(음성 메일 경로 변경 설정을 구성하는 경우). 그러나 사용자가 25명 미만인 사이트의 경우 복원력 솔루션이 충분한 투자 수익을 제공하지 못할 수 있습니다.

분기 사이트 탄성을 제공하려는 경우 세 가지 방법 중 하나를 사용할 수 있습니다. 다음 표를 사용하면 조직에 가장 적합한 옵션을 선택하는 데 도움이 될 수 있습니다.

|**만약 당신이...**|**다음을 사용하는 것이 좋습니다.**|
|:-----|:-----|
|분기 사이트에서 25~1000명의 사용자를 호스팅하려는 경우(ROI(투자 수익률)가 전체 배포를 지원하지 않거나 로컬 관리 지원을 사용할 수 없음)  <br/> |Survivable Branch Appliance  <br/> Survivable Branch Appliance는 Windows Server 2008 R2에서 실행되는 비즈니스용 Skype 서버 등록 기관 및 중재 서버가 있는 업계 표준 블레이드 서버입니다. Survivable Branch Appliance에는 PSTN(공중 전화망) 게이트웨이도 포함되어 있습니다. SBA(Survivable Branch Appliance) 자격 검증/인증 프로그램에서 Microsoft 파트너가 개발한 적격 타사 장치는 WAN 오류 시에도 지속적인 PSTN 연결을 제공하지만, 이러한 기능은 중앙 사이트의 프런트 엔드 서버를 기반으로 하기 때문에 이 접근 방식이 탄력적인 현재 상태 및 회의 기능을 제공하지는 못합니다.  <br/> Survivable Branch Appliance에 대한 자세한 내용은 이 항목의 뒷부분에 있는 "Survivable Branch Appliance Details"를 참조하세요.  <br/> **참고:** SIP 트렁크를 Survivable Branch Appliance와 함께 사용하기로 결정한 경우 Survivable Branch Appliance 공급업체에 문의하여 조직에 가장 적합한 서비스 공급자에 대해 알아보세요. <br/> |
|분기 사이트에서 1,000~2,000명의 사용자를 호스트하고, 복원력 있는 WAN 연결이 부족하며, 사용 가능한 비즈니스용 Skype 서버 관리자를 학습시켰습니다.  <br/> |Survivable Branch Server 또는 Survivable Branch Appliance 2개  <br/> Survivable Branch Server는 비즈니스용 Skype 서버 등록 기관 및 중재 서버 소프트웨어가 설치된 지정된 하드웨어 요구 사항을 충족하는 Windows 서버입니다. 이 서버는 전화 서비스 공급자에 대한 SIP 트렁크 또는 PSTN 게이트웨이에 연결되어야 합니다.  <br/> Survivable Branch Server에 대한 자세한 내용은 이 항목의 뒷부분에 있는 "Survivable Branch Server Details"를 참조하세요.  <br/> |
|최대 5,000명의 사용자를 위한 음성 기능 외에 현재 상태 및 회의 기능이 필요하고 사용 가능한 비즈니스용 Skype 서버 관리자를 교육한 경우  <br/> |Standard Edition 서버를 분기 사이트가 아니라 중앙 사이트로 배포합니다.  <br/> 본격적인 비즈니스용 Skype 서버 배포는 WAN 오류 발생 시 지속적인 PSTN 연결 및 복원력 있는 존재 및 회의를 제공합니다.  <br/> |

#### <a name="resiliency-topologies"></a>복구 토폴로지

다음 그림에서는 분기 사이트 복구를 지원하는 권장 토폴로지를 보여 줍니다.

**분기 사이트 복구 옵션**

![음성 분기 복원력 옵션입니다.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>SBA(Survivable Branch Appliance) 세부 정보

비즈니스용 Skype 서버 Survivable Branch Appliance에는 다음 구성 요소가 포함됩니다.

- 사용자 인증, 등록 및 통화 라우팅을 수행하는 등록자

- 등록자와 PSTN 게이트웨이 간의 신호를 처리하는 중재 서버

- WAN 중단 시 PSTN 통화를 대체 전송으로 라우팅하는 PSTN 게이트웨이

- 로컬 사용자 데이터를 저장하는 SQL Server Express

Survivable Branch Appliance에는 PSTN 트렁크, 아날로그 포트 및 이더넷 어댑터도 포함됩니다.

중앙 사이트에 대한 분기 사이트의 WAN 연결을 사용할 수 없게 되면 내부 분기 사용자는 계속 Survivable Branch Appliance 등록 기관에 등록되고 PSTN에 대한 Survivable Branch Appliance 연결을 사용하여 중단 없는 음성 서비스를 얻습니다. 홈 또는 다른 원격 위치에서 연결하는 분기 사이트 사용자는 분기 사이트의 WAN 링크를 사용할 수 없어도 중앙 사이트의 등록자 서버에 등록할 수 있습니다. 이러한 사용자는 분기 사이트로의 인바운드 통화가 음성 메일로 이동하는 것을 제외하고는 전체 통합 통신 기능을 사용할 수 있습니다. WAN 연결이 복구되면 분기 사이트 사용자를 위한 전체 기능이 복원됩니다. Survivable Branch 어플라이언스로의 장애 조치(failover)나 서비스 복원에는 IT 관리자가 필요하지 않습니다.

비즈니스용 Skype 서버 분기 사이트에서 최대 2개의 Survivable Branch Appliance를 지원합니다.

#### <a name="survivable-branch-appliance-deployment-overview"></a>SBA(Survivable Branch Appliance) 배포 개요

Survivable Branch Appliance는 Microsoft와 협력하여 원래 장비 제조업체에서 제조되며 부가 가치 소매업체를 대신하여 배포됩니다. 이 배포는 중앙 사이트에 비즈니스용 Skype 서버 배포되고, 분기 사이트에 대한 WAN 연결이 설정되고, 분기 사이트 사용자가 Enterprise Voice 사용하도록 설정된 후에만 발생합니다.

이러한 단계에 대한 자세한 내용은 배포 설명서의 [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server)를 참조하십시오.

|**작업 단계**|**단계**|**사용자 권한**|
|:-----|:-----|:-----|
|Survivable Branch Appliance에 대한 Active Directory Domain Services 설정  <br/> |**중앙 사이트에서 다음을 수행합니다.** <br/>  분기 사이트에서 Survivable Branch Appliance를 설치하고 활성화할 기술자를 위한 도메인 사용자 계정(또는 엔터프라이즈 ID)을 만듭니다. <br/>  Active Directory Domain Services Survivable Branch Appliance에 대한 컴퓨터 계정(해당 FQDN(정규화된 도메인 이름))을 만듭니다. <br/>  토폴로지 작성기에서 Survivable Branch Appliance를 만들고 게시합니다. <br/> |기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원이어야 합니다. Survivable Branch Appliance는 토폴로지 작성기를 사용할 때 자동으로 발생하는 RTCSBAUniversalServices 그룹에 속해야 합니다.  <br/> |
|Survivable Branch Appliance를 설치하고 활성화합니다.  <br/> |**분기 사이트에서 다음을 수행합니다.** <br/>  Survivable Branch Appliance를 이더넷 포트 및 PSTN 포트에 커넥트. <br/>  Survivable Branch Appliance를 시작합니다. <br/>  중앙 사이트의 Survivable Branch Appliance에 대해 만든 도메인 사용자 계정을 사용하여 Survivable Branch Appliance를 도메인에 조인합니다. FQDN 및 IP 주소를 컴퓨터 계정에 만든 FQDN과 일치하도록 설정합니다. <br/>  OEM 사용자 인터페이스를 사용하여 Survivable Branch Appliance를 구성합니다. <br/>  PSTN 연결을 테스트합니다. <br/> |기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원이어야 합니다.  <br/> |

#### <a name="survivable-branch-server-details"></a>지속 가능 분기 서버 세부 정보

토폴로지 작성기에서 분기 사이트를 만들고 해당 사이트에 Survivable Branch Server를 추가한 다음 역할을 설치하려는 컴퓨터에서 비즈니스용 Skype 서버 배포 마법사를 실행합니다.

### <a name="branch-site-resiliency-requirements"></a>분기 사이트 복원력 요구 사항

이 항목에서는 사용자의 분기 사이트 복구 준비, 음성 메일 지속성 준비 및 관련 하드웨어/소프트웨어 요구 사항에 대한 정보를 제공합니다.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>사용자의 분기 사이트 복구 준비

등록자 풀을 SBA(Survivable Branch Appliance) 또는 Survivable Branch Server로 설정하여 사용자가 분기 사이트 복원력을 준비합니다.

#### <a name="registrar-assignments-for-branch-users"></a>분기 사용자에 대한 등록자 할당

선택한 분기 사이트 복원력 솔루션에 관계없이 각 사용자에게 기본 등록자를 할당해야 합니다. 분기 사이트 사용자는 등록 기관이 Survivable Branch Appliance, Survivable Branch Server 또는 독립 실행형 비즈니스용 Skype 서버 Standard 또는 Enterprise Edition 서버에 있는지 여부에 관계없이 항상 분기 사이트의 등록 기관에 등록해야 합니다. 클라이언트에서 해당 등록자 풀을 검색하려면 DNS(Domain Name System) SRV(서비스 리소스 레코드)가 필요합니다. Survivable Branch Appliance를 사용할 수 없게 되면 분기 사이트 클라이언트가 백업 등록자를 자동으로 검색합니다.

분기 사이트에 DNS 서버가 없는 경우 Survivable Branch Appliance 또는 Survivable Branch Server의 검색을 구성하는 두 가지 다른 방법이 있습니다.

- 분기 사이트의 DHCP(동적 호스트 구성 프로토콜) 서버에서 DHCP 옵션 120을 구성하여 Survivable Branch Appliance 또는 Survivable Branch Server의 FQDN(정규화된 도메인 이름)을 가리킵니다.

- DHCP 120 쿼리에 응답하도록 Survivable Branch Appliance 또는 Survivable Branch Server를 구성합니다.

#### <a name="voice-routing-for-branch-users"></a>분기 사용자를 위한 음성 라우팅

분기 사이트의 사용자를 위한 별도의 사용자 수준 VoIP(Voice over Internet Protocol) 정책을 만드는 것이 좋습니다. 이 정책에는 Survivable Branch Appliance 또는 분기 서버 게이트웨이를 사용하는 기본 경로와 중앙 사이트의 PSTN(공중 전화망) 게이트웨이가 있는 트렁크를 사용하는 하나 이상의 백업 경로가 포함되어야 합니다. 기본 경로를 사용할 수 없는 경우 하나 이상의 중앙 사이트 게이트웨이를 사용하는 백업 경로가 대신 사용됩니다. 이러한 방식으로 사용자가 등록된 위치(분기 사이트 등록 기관 또는 중앙 사이트의 백업 등록 기관 풀)에 관계없이 사용자의 VoIP 정책은 항상 적용됩니다. 이 방식은 장애 조치(failover) 시나리오에서 중요한 고려 사항입니다. 예를 들어 Survivable Branch Appliance의 이름을 바꾸거나 Survivable Branch Appliance를 다시 구성하여 중앙 사이트의 백업 등록 기관 풀에 연결해야 하는 경우 해당 기간 동안 분기 사이트 사용자를 중앙 사이트로 이동해야 합니다. (Survivable Branch Appliance의 이름을 바꾸거나 다시 구성하는 방법에 대한 자세한 내용은 [부록 B: 배포 설명서에서 Survivable Branch Appliance 관리](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) )를 참조하세요. 해당 사용자에게 사용자 수준 VoIP 정책 또는 사용자 수준 다이얼 플랜이 없는 경우 사용자가 다른 사이트로 이동하면 분기 사이트 수준 VoIP 정책 및 다이얼 플랜 대신 중앙 사이트의 사이트 수준 VoIP 정책 및 사이트 수준 다이얼 플랜이 기본적으로 사용자에게 적용됩니다. 이 시나리오에서는 백업 등록자 풀에서 사용되는 사이트 수준 VoIP 정책 및 사이트 수준 다이얼 플랜이 분기 사이트 사용자에게도 적용될 수 있지 않는 한 해당 통화가 실패합니다. 예를 들어 일본에 있는 분기 사이트의 사용자가 레드몬드의 중앙 사이트로 이동될 경우 모든 7자리 숫자 통화에 +1425를 추가하는 정규화 규칙의 다이얼 플랜은 해당 사용자에 대한 통화를 올바르게 변환하지 않을 수 있습니다.

> [!IMPORTANT]
> 지점 백업 경로를 만드는 경우 두 개의 PSTN 전화 사용 레코드를 지점 사용자 정책에 추가하고 각 레코드에 별도의 경로를 할당하는 것이 좋습니다. 첫 번째 또는 기본 경로는 SBA(Survivable Branch Appliance) 또는 분기 서버와 연결된 게이트웨이로 호출을 전달합니다. 두 번째 또는 백업 경로는 중앙 사이트의 게이트웨이에 대한 호출을 전달합니다. 통화를 전달할 때 SBA(fea-boa) 또는 분기 서버는 두 번째 사용 레코드를 시도하기 전에 첫 번째 PSTN 사용 레코드에 할당된 모든 경로를 시도합니다.

분기 게이트웨이 또는 Survivable Branch Appliance 사이트의 Windows 구성 요소를 사용할 수 없는 경우(예: 유지 관리를 위해 Survivable Branch Appliance 또는 분기 게이트웨이가 다운된 경우) 분기 사이트 사용자에 대한 인바운드 호출이 해당 사용자에게 전달되도록 하려면 게이트웨이에 장애 조치(failover) 경로를 만들거나 DID(Direct Inward Dialing) 공급자와 협력하여 중앙 사이트의 백업 등록자 풀로 들어오는 호출을 리디렉션합니다. 여기에서 통화는 WAN 링크를 통해 분기 사용자에게 라우팅됩니다. 경로가 PSTN 게이트웨이 또는 다른 트렁크 피어의 허용 전화 번호 형식을 준수하도록 숫자를 변환해야 합니다. 장애 조치(failover) 경로를 만드는 방법에 대한 자세한 내용은 [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route)을 참조하십시오. 또한 수신 통화를 정규화하도록 분기 사이트의 게이트웨이와 연결된 트렁크에 대한 서비스 수준의 다이얼 플랜을 만듭니다. 분기 사이트에 두 개의 Survivable Branch Appliance가 있는 경우 각각에 대해 별도의 서비스 수준 계획이 필요하지 않은 한 둘 다에 대한 사이트 수준 다이얼 플랜을 만들 수 있습니다.

> [!NOTE]
> 현재 상태, 회의 또는 장애 조치를 중앙 사이트에 의존하는 분기 사이트 사용자의 중앙 사이트 리소스 사용을 계산하려면 각 분기 사이트 사용자를 중앙 사이트에 등록된 사용자로 간주하는 것이 좋습니다. 현재는 Survivable Branch Appliance에 등록된 사용자를 포함하여 분기 사이트 사용자 수에 제한이 없습니다.

사용자 수준 다이얼 플랜 및 음성 정책을 만들어 분기 사이트 사용자에게 할당하는 것도 좋습니다. 자세한 내용은 배포 설명서[에서 비즈니스용 Skype 서버 다이얼 플랜 만들기 또는 수정](../../deploy/deploy-enterprise-voice/dial-plans.md) 및 [분기 사용자를 위한 VoIP 라우팅 정책 만들기](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users)를 참조하세요.

#### <a name="routing-extension-numbers"></a>내선 번호 라우팅

분기 사이트 사용자를 위한 다이얼 플랜 및 음성 정책을 준비할 때는 msRTCSIP 줄(또는 회선 URI) 특성에 사용되는 문자열 및 숫자 형식과 일치하는 정규화 규칙 및 번역 규칙을 포함해야 합니다. 따라서 분기 사이트 사용자와 중앙 사이트 사용자 간에 활성화된 비즈니스용 Skype 호출이 올바르게 라우팅됩니다. 특히 WAN 링크를 사용할 수 없기 때문에 호출을 PSTN을 통해 다시 라우팅해야 하는 경우. 전화 번호만 있는 것이 아니라 내선이 포함된 전화 접속 번호의 경우에는 특별한 추가 고려 사항이 있습니다.

내선 번호를 포함하는 줄 URI와 일치하는 정규화 규칙 및 변환 규칙은 배타적으로 사용되든 전체 E.164 전화 번호에 추가로 사용되든 간에 추가적인 요구 사항이 있습니다. 이 섹션에서는 내선 번호가 포함된 줄 URI에 대한 통화를 라우팅하는 몇 가지 예제 시나리오에 대해 설명합니다.

조직에 개별 사용자에 대한 DID(Direct Inward Dial) 전화 번호가 구성되어 있지 않고 각 사용자의 줄 URI에 내선 번호만 구성된 경우 내부 사용자는 내선 번호만 사용하여 서로 통화할 수 있습니다. 하지만 분기 사이트 사용자와 중앙 사이트 사용자 간의 통화에 적용되는 내선 번호와 일치하는 정규화 규칙을 구성해야 합니다.

분기 사이트와 중앙 사이트 간의 WAN 링크를 사용할 수 있는 시나리오에서는 분기 사이트 사용자로부터 중앙 사이트 사용자로의 통화에는 통화가 PSTN을 통해 라우팅되지 않으므로 번호를 변환할 일치하는 정규화 규칙이 필요하지 않습니다. 예를 들면 다음과 같습니다.

|**규칙 이름**|**설명**|**번호 패턴**|**번역**|**예**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |5자리 숫자를 변환하지 않음  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001이 변환되지 않음  <br/> |

또한 분기 사이트와 중앙 사이트 간의 WAN 링크를 사용할 수 없고 분기 사이트로부터의 통화를 PSTN을 통해 라우팅해야 하는 경우와 같은 특정 시나리오를 위한 내선 번호를 수용할 수 있어야 합니다. WAN이 중단되는 동안 분기 사이트 사용자가 중앙 사이트 사용자의 확장에만 전화를 걸어 중앙 사이트 사용자를 호출하는 경우 중앙 사이트 사용자의 전체 전화 번호를 추가하는 아웃바운드 번역 규칙이 있어야 합니다. 사용자의 회선 URI에 조직의 전체 전화 번호와 사용자에게 고유한 전체 전화 번호 대신 사용자의 고유 확장 번호가 포함된 경우 조직의 전체 전화 번호를 추가하는 아웃바운드 번역 규칙이 있어야 합니다. 예:

|**설명**|**일치 패턴**|**번역**|**예**|
|:-----|:-----|:-----|:-----|
|5자리 숫자를 사용자의 전화 번호 및 확장명으로 변환합니다.  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001이 +14255550123;ext=10001로 변환됨  <br/> |
|5자리 숫자를 조직의 전화 번호 및 사용자의 확장명으로 변환합니다.  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001이 +14255550100;ext=10001로 변환됨  <br/> |

이 시나리오에서 PSTN에 대한 재라우팅을 처리하는 트렁크 피어가 내선 번호를 지원하지 않을 경우에는 아웃바운드 변환 규칙에서도 내선 번호를 제거해야 합니다. 예를 들면 다음과 같습니다.

|**설명**|**일치 패턴**|**번역**|**예**|
|:-----|:-----|:-----|:-----|
|내선이 포함된 전화 번호에서 내선 제거  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001이 +14255550123으로 변환됨  <br/> |

WAN 링크를 사용할 수 있는지 여부, 조직에 개별 사용자에 대해 구성된 DID 번호가 없는 경우 및 사용자의 회선 URI에 조직의 전화 번호와 사용자의 고유한 확장 번호가 포함된 경우 분기 사이트의 트렁크 피어 또는 PSTN 게이트웨이에서 연결할 수 있는 번호로 조직의 전화 번호 줄 URI를 구성해야 합니다. 또한 통화가 해당 번호로 라우팅되도록 고유한 확장을 포함하도록 조직의 전화 번호 회선 URI를 구성해야 합니다.

#### <a name="preparing-for-voice-mail-survivability"></a>음성 메일 지속성 준비

Exchange UM(통합 메시징)은 일반적으로 분기 사이트가 아닌 중앙 사이트에만 설치됩니다. 발신자는 분기 사이트와 중앙 사이트 간의 WAN 링크를 사용할 수 없는 경우에도 음성 메일 메시지를 남길 수 있어야 합니다. 따라서 지점 사이트 사용자에게 음성 메일을 제공하는 Exchange UM 자동 전화 교환 전화 번호의 줄 URI를 구성하려면 해당 음성 메일 번호에 적용되는 음성 정책, 다이얼 플랜 및 정규화 규칙 외에도 특별한 고려 사항이 필요합니다.

SBA(Survivable Branch Appliance) 및 Survivable Branch Server는 WAN 중단 시 분기 사용자에게 음성 메일 생존 가능성을 제공합니다. 특히 Survivable Branch Appliance 또는 Survivable Branch Server를 사용하고 WAN을 사용할 수 없는 경우 SBA 또는 Survivable Branch Server는 PSTN을 통해 응답되지 않은 호출의 경로를 다시 지정하여 중앙 사이트의 UM을 Exchange. SBA 또는 Survivable Branch Server를 사용하면 WAN 중단 중에 PSTN을 통해 음성 메일 메시지를 검색할 수도 있습니다. 마지막으로 WAN이 중단되는 동안 Survivable Branch Appliance 또는 Survivable Branch Server는 부재 중 알림을 큐에 대기한 다음 WAN이 복원될 때 Exchange UM 서버에 업로드합니다. 음성 메일 다시 라우팅이 복원력이 있는지 확인하려면 중앙 사이트 풀의 FQDN에 대한 항목과 Edge Server FQDN에 대한 항목을 Survivable Branch Server의 호스트 파일에 추가해야 합니다. 그렇지 않으면 분기 사이트에 DNS 서버가 없는 경우 DNS 확인 시간이 초과될 수 있습니다.

분기 사이트 사용자에 대해 음성 메일 지속성을 제공하려면 다음과 같이 구성하는 것이 좋습니다.

- Microsoft Exchange 관리자는 메시지를 수락하도록 Exchange AA(자동 전화 교환)를 구성해야 합니다. 이 구성은 사용자에게 전송 또는 교환원에게 전송과 같은 다른 모든 일반 기능을 비활성화하고 메시지만 허용하도록 AA를 제한합니다. 또는 Exchange 관리자는 일반 AA를 사용하거나 통화를 교환원에게 라우팅하도록 사용자 지정된 AA를 사용할 수 있습니다.

- 비즈니스용 Skype 서버 관리자는 AA 전화 번호를 가져와서 해당 전화 번호를 Survivable Branch Appliance 또는 분기 서버의 음성 메일 경로 변경 설정에서 **exchange um 자동 전화 교환** 번호로 사용해야 합니다.

- 비즈니스용 Skype 서버 관리자는 Exchange UM 구독자 액세스 전화 번호를 가져와서 Survivable Branch Appliance 또는 Survivable Branch Server에 대한 음성 메일 경로 변경 설정에서 **해당 번호를 구독자 액세스** 번호로 사용해야 합니다.

- 비즈니스용 Skype 서버 관리자는 WAN 중단 중에 음성 메일에 액세스해야 하는 모든 분기 사용자와 하나의 다이얼 플랜만 연결되도록 Exchange UM을 구성해야 합니다.

- WAN 링크를 사용할 수 없는 경우 분기 사이트 사용자에 대한 호출을 사용자의 Exchange UM(통합 메시징) 음성 사서함으로 라우팅할 수 있지만 통화에 적용된 음성 정책이 고유하고 확장 번호를 포함하지 않는 음성 메일 전화 번호를 지정하는 경우에만 라우팅할 수 있습니다.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>분기 사이트 복구를 위한 하드웨어 및 소프트웨어 요구 사항

하드웨어 및 소프트웨어 요구 사항은 복구 솔루션에 따라 다릅니다.

#### <a name="requirements-for-survivable-branch-appliances"></a>SBA(Survivable Branch Appliance)에 대한 요구 사항

필수 하드웨어 및 소프트웨어는 Survivable Branch 어플라이언스로 기본 제공됩니다. 그러나 각 분기 사이트에서는 DHCP 서버를 배포하여 클라이언트 IP 주소를 가져오는 것이 좋습니다. 그렇지 않으면 DHCP 임대가 만료되면 클라이언트에 IP 연결이 없습니다.

엔터프라이즈 DNS 서버가 중앙 사이트에만 있는 경우 분기 사이트 사용자는 WAN 중단 중에 연결할 수 없으므로 DNS SRV(서비스) 리소스 레코드를 사용하는 비즈니스용 Skype 서버 검색이 실패합니다. WAN 중단 중에 프롬프트 재라우팅을 보장하려면 DNS 레코드가 분기 사이트에서 캐시되어야 합니다. 분기 라우터에서 지원할 경우에는 DNS 캐싱을 사용하도록 설정하십시오. 또는 분기 사이트에 DNS 서버를 배포할 수 있습니다. 독립 실행형 서버 또는 DNS 기능을 지원하는 Survivable Branch Appliance 버전일 수 있습니다. 자세한 내용은 Survivable Branch Appliance 공급자에게 문의하세요.

> [!NOTE]
> 분기 사이트에 도메인 컨트롤러가 있을 필요는 없습니다. Survivable Branch Appliance는 로그인할 때 클라이언트의 인증서 요청에 대한 응답으로 클라이언트를 보내는 특수 인증서를 사용하여 클라이언트를 인증합니다.

비즈니스용 Skype 클라이언트는 DHCP 옵션 120(SIP 등록 기관 옵션)을 사용하여 비즈니스용 Skype 서버 검색할 수 있습니다. 다음 두 가지 방법 중 하나로 구성할 수 있습니다.

- DHCP 120 쿼리에 회신하도록 분기 사이트에서 DHCP 서버를 구성합니다. 이 쿼리는 Survivable Branch Appliance 또는 Survivable Branch Server에서 등록 기관의 FQDN을 반환합니다.

- 비즈니스용 Skype 서버 DHCP를 켭니다. 이 설정이 켜지면 비즈니스용 Skype 서버 등록 기관에서 DHCP 옵션 120 쿼리에 응답합니다. 등록 기관은 DHCP 옵션 120 이외의 DHCP 쿼리에 응답하지 않습니다.

또한 서브넷이 여러 개 있는 대규모 분기 사이트의 경우 DHCP 릴레이 에이전트를 사용하여 DHCP 옵션 120 쿼리를 DHCP 서버(구성 1) 또는 등록 기관(구성 2)으로 전달해야 합니다.

마지막으로 분기 사이트 사용자를 Enterprise Voice 대해 구성하고 적절한 통합 통신 엔드포인트로 프로비전해야 합니다.

#### <a name="requirements-for-survivable-branch-servers"></a>Survivable Branch Server에 대한 요구 사항

Survivable Branch Server에 대한 요구 사항은 프런트 엔드 서버에 대한 요구 사항과 동일합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 참조하세요.

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Full-Scale 비즈니스용 Skype 서버 Branch-Site 배포에 대한 요구 사항

자세한 내용은 계획 설명서에서 [비즈니스용 Skype 서버 2015에 대한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 참조하세요.

### <a name="example-configuring-a-failover-route"></a>예: 장애 조치(failover) 경로 구성

 다음 예제에서는 관리자가 Dallas-GW1이 유지 관리를 위해 다운되거나 다른 이유로 인해 사용할 수 없는 경우 사용할 장애 조치(failover) 경로를 정의할 수 있는 방법을 보여 줍니다. 다음 표에서는 필요한 구성 변경을 보여 줍니다.

**표 1. 사용자 정책**

|**사용자 정책**|**전화 사용**|
|:-----|:-----|
|기본 통화 정책  <br/> |로컬  <br/> GlobalPSTNHopoff  <br/> |
|레드몬드 시내 정책  <br/> |RedmondLocal  <br/> |
|달라스 통화 정책  <br/> |댈러스Users  <br/> GlobalPSTNHopoff  <br/> |

**표 2. 경로**


| **경로 이름**             | **번호 패턴** | **전화 사용**         | **트렁크**                                 | **게이트웨이**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| 레드몬드 시내 경로  <br/> | ^\+1(425           | 206                     | 253)(\d{7})$  <br/>                       | 로컬  <br/> RedmondLocal  <br/>                |
| 달라스 시내 경로  <br/>  | ^\+1(972           | 214                     | 469)(\d{7})$  <br/>                       | 로컬  <br/>                                    |
| 범용 경로  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | 트렁크1  <br/> 트렁크2  <br/> 트렁크3  <br/> | Red-GW1  <br/> Red-GW2  <br/> 댈러스-GW1  <br/> |
| 달라스 사용자 경로  <br/>  | ^\+? (\d\*) $  <br/> | 댈러스Users  <br/>      | 트렁크3  <br/>                             | 댈러스-GW1  <br/>                               |

표 1에서 GlobalPSTNHopoff의 전화 사용은 달라스 통화 정책의 DallasUsers 전화 사용 뒤에 추가됩니다. 이렇게 하면 DallasUsers 전화 사용의 경로를 사용할 수 없는 경우 달라스 통화 정책의 통화가 GlobalPSTNHopoff 전화에 대해 구성된 경로를 사용할 수 있습니다.