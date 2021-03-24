---
title: 비즈니스용 Skype 서버의 직접 SIP 연결
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: 비즈니스용 Skype 서버와 비즈니스용 Skype 서버의 PSTN 게이트웨이와 IP-PBX 간에 직접 SIP 연결이 Enterprise Voice.
ms.openlocfilehash: 7a70a6f3afd303ef5847993240b26b47d1b4ceac
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096418"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 직접 SIP 연결

비즈니스용 Skype 서버와 비즈니스용 Skype 서버의 PSTN 게이트웨이와 IP-PBX 간에 직접 SIP 연결이 Enterprise Voice.

직접 SIP 연결을 사용하여 비즈니스용 Skype 서버를 다음 중 하나에 연결할 수 있습니다.

- IP-PBX

- PSTN 게이트웨이

직접 SIP 연결을 구현하려면 기본적으로 SIP 트렁크를 구현할 때와 동일한 배포 단계를 따릅니다. 두 경우 모두 중재 서버의 외부 인터페이스를 사용하여 연결을 구현합니다. 단, SIP 트렁크는 ITSP 게이트웨이와 같은 외부 엔터티에 연결하고 직접 SIP 연결은 IP-PBX, 공중 전화망(PSTN) 게이트웨이 등 로컬 네트워크의 내부 엔터티에 연결한다는 점이 다릅니다.

## <a name="direct-sip-deployment-options"></a>직접 SIP 배포 옵션

### <a name="skype-for-business-server-stand-alone"></a>비즈니스용 Skype 서버 Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

조직에서 이 섹션에 설명된 배포 중 하나를 사용하는 경우 비즈니스용 Skype 서버를 조직의 일부 또는 전체에 대한 유일한 전화 통신 솔루션으로 사용할 수 있습니다. 이 섹션에서는 다음 배포에 대해 자세히 설명합니다.

- **증분 배포:** 이 옵션은 기존 PBX(Private Branch Exchange) 인프라가 있으며 조직 내의 소규모 그룹이나 팀에 Enterprise Voice 증분적으로 사용하려는 것으로 가정합니다.

- **VoIP 전용 배포:** 이 옵션은 기존 전화 통신 인프라가 Enterprise Voice 사이트에 배포하는 것이 좋습니다.

#### <a name="incremental-deployment"></a>증분 배포

증분 배포에서 비즈니스용 Skype 서버는 개별 팀 또는 부서를 위한 유일한 전화 통신 솔루션인 반면 조직의 나머지 사용자는 계속 PBX를 사용하게 됩니다. 이 증분 배포 전략은 제어된 파일럿 프로그램을 통해 엔터프라이즈에 IP 전화 통신을 도입하는 한 가지 방법을 제공합니다. Microsoft Unified Communications에서 통신 요구 사항을 가장 잘 충족하는 작업 Enterprise Voice 기존 PBX에 남아 있는 사용자도 있습니다. 필요한 경우 추가 작업 Enterprise Voice 마이그레이션할 수 있습니다.

통신 요구 사항이 공통적으로 있으며 중앙 집중식 관리에 사용되는 사용자 그룹을 명확하게 정의한 경우 증분 옵션을 사용하는 것이 좋습니다. 이 옵션은 장거리 요금을 절약할 수 있는 다양한 지역에 분산된 팀이나 부서가 있는 경우도 효과적입니다. 실제로 이 옵션은 구성원이 전 세계에 분산될 수 있는 가상 팀을 만드는 데 유용합니다. 변화하는 비즈니스 요구 사항에 빠르게 대응하여 이러한 팀을 만들거나 수정하거나 해지할 수 있습니다.

다음 그림에서는 PBX 뒤에서 배포하기 위한 Enterprise Voice 토폴로지입니다. 증분 배포에 권장되는 토폴로지입니다.

**증분 배포 옵션**

![부서 마이그레이션 옵션 다이어그램](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> 비즈니스용 Skype 서버 배포를 인증된 직접 SIP 파트너에 연결하는 경우 중재 서버와 PBX 간에 PSTN(Public Switched Telephone Network) 게이트웨이가 필요하지 않습니다. 인증된 직접 SIP 파트너 목록은  [Microsoft Unified Communications Open Interoperability Program](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)을 참조하세요.

> [!NOTE]
> 이 그림에 표시된 미디어 경로에는 미디어 우회를 사용하도록 설정되어 있습니다(권장 구성). 미디어 우회를 사용하지 않도록 설정하면 미디어 경로가 중재 서버를 통해 라우팅됩니다.

이 토폴로지에서는 선택한 부서 또는 작업 Enterprise Voice. PSTN 게이트웨이는 VoIP(Voice over Internet Protocol) 사용 작업과 PBX를 연결합니다. 원격 작업자를 Enterprise Voice 사용하도록 설정된 사용자는 IP 네트워크를 통해 통신합니다. 사용자와 Enterprise Voice PSTN으로의 통화는 해당 PSTN 게이트웨이로 Enterprise Voice 라우팅됩니다. 여전히 PBX 시스템에 있는 동료나 PSTN의 발신자로부터의 통화는 라우팅을 위해 비즈니스용 Skype 서버로 통화를 전달하는 PSTN 게이트웨이로 라우팅됩니다.

상호 운영성을 위해 기존 PBX Enterprise Voice 연결하기 위한 권장 구성에는 PBX 뒤에서 Enterprise Voice PBX Enterprise Voice 구성이 있습니다.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice 뒤에 있는 PBX

PBX Enterprise Voice 배포하면 PSTN의 모든 통화가 PBX에 도착하여 Enterprise Voice 사용자에게 통화를 PSTN 게이트웨이로 라우팅하고 PBX 사용자에 대한 통화를 PBX로 라우팅합니다.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice 앞에 있는 PBX

PBX 앞에 Enterprise Voice 모든 통화는 PSTN 게이트웨이에 도착하여 Enterprise Voice 사용자의 통화를 비즈니스용 Skype 서버로 라우팅하고 PBX 사용자에 대한 통화를 PBX로 라우팅합니다. ENTERPRISE VOICE PBX 사용자로부터의 PSTN 호출은 IP 네트워크를 통해 비용 효율적인 PSTN 게이트웨이로 라우팅됩니다. 다음 표에서는 이 구성의 장단점을 보여줍니다.

**PBX 앞에서 배포하는 Enterprise Voice 장단점**

|**장점**|**단점**|
|:-----|:-----|
|PBX는 여전히 사용자에 대해 사용하도록 설정되지 않은 사용자를 Enterprise Voice.  <br/> |기존 게이트웨이는 원하는 기능이나 용량을 지원하지 않을 수 있습니다.  <br/> |
|PBX는 이전의 모든 장치를 처리합니다.  <br/> |게이트웨이에서 PBX로, 게이트웨이에서 중재 서버로의 트렁크가 필요합니다. 서비스 공급자의 트렁크가 더 필요할 수 있습니다.  <br/> |
|Enterprise Voice 동일한 전화 번호를 보관할 수 있습니다.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>VoIP-Only 배포

Enterprise Voice 새로운 비즈니스 및 기존 비즈니스를 위한 새 사무실 사이트를 제공합니다. 또한 PBX 통합에 대해 걱정하거나 IP-PBX 인프라의 상당한 배포 및 유지 관리 비용을 부담하지 않고도 완전한 기능을 제공하는 VoIP 솔루션을 구현할 수 있습니다. 이 솔루션은 현장 작업자와 원격 작업자를 모두 지원합니다.

이 배포에서는 모든 통화가 IP 네트워크를 통해 라우팅됩니다. PSTN에 대한 통화는 해당 PSTN 게이트웨이로 라우팅됩니다. 비즈니스용 Skype 또는 Lync Phone Edition은 소프트폰 역할을 합니다. 사용자가 제어할 수 있는 PBX 전화가 없으면 원격 통화 제어를 사용할 수 없거나 필요하지 않습니다. 음성 메일 및 자동 전화 교환 서비스는 Exchange UM(통합 메시징)의 선택적 배포를 통해 사용할 수 있습니다.

> [!NOTE]
> VoIP 전용 배포는 비즈니스용 Skype 서버를 지원하는 데 필요한 네트워크 인프라 외에도 소규모의 적격 게이트웨이를 사용하여 팩스 컴퓨터 및 아날로그 장치를 지원할 수 있습니다.

다음 그림에서는 VoIP 전용 배포의 일반적인 토폴로지입니다.

**VoIP 전용 배포 옵션**

![Greenfidle 배포 옵션](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> 이 그림에 표시된 미디어 경로에는 미디어 우회를 사용하도록 설정되어 있습니다(권장 구성). 미디어 우회를 사용하지 않도록 설정하면 미디어 경로가 중재 서버를 통해 라우팅됩니다.

## <a name="pstn-gateway-deployment-options"></a>PSTN 게이트웨이 배포 옵션

### <a name="pstn-gateways"></a>PSTN 게이트웨이

PSTN(Public Switched Telephone Network) 게이트웨이는 직접 또는 SIP 트렁크에 대한 연결을 통해 Enterprise Voice 인프라와 PSTN 간에 신호 및 미디어를 변환하는 타사 하드웨어 구성 요소입니다. 두 토폴로지에서 게이트웨이는 PSTN을 종료합니다. 게이트웨이가 자체 서브넷에 격리되어 있으며 중재 서버를 통해 엔터프라이즈 네트워크에 연결됩니다.

사이트가 여러 개 있는 엔터프라이즈는 일반적으로 각 사이트에 하나 이상의 게이트웨이를 배포합니다. 분기 사이트는 게이트웨이 또는 단일 상자에 게이트웨이와 서버를 결합하는 Survivable Branch Appliance를 통해 PSTN에 연결할 수 있습니다. 분기 사이트에서 게이트웨이를 사용하는 경우 WAN 링크가 복원되지 않는 한 등록자 및 중재 서버가 모두 사이트에 필요합니다. 프런트 엔드 서버에 함께 있는 하나 이상의 중재 서버는 각 사이트에서 하나 이상의 게이트웨이에 대한 통화를 라우팅할 수 있습니다. 사이트에 필요한 등록자, 중재 서버 및 게이트웨이를 SSS(Survivable Branch Appliance)로 배포하는 것이 좋습니다.

PSTN 게이트웨이의 수, 크기 및 위치를 결정하는 것은 Enterprise Voice 인프라를 계획할 때 가장 중요하고 비용이 많이 드는 결정일 수 있습니다.

다음은 고려해야 할 주요 질문입니다. 이러한 질문에 대한 대답은 모두 상호 독립적입니다.

- 필요한 PSTN 게이트웨이의 수 응답은 사용자 수, 예상되는 동시 통화 수(트래픽 부하) 및 사이트 수(각 사이트에는 1개가 필요)에 따라 달라 습니다.

- 게이트웨이의 크기는 어떻게 하나요? 답변은 사이트의 사용자 수와 트래픽 부하에 따라 달라 지는 것입니다.

- 게이트웨이는 어디에 위치해야 하나요? 이 대답은 토폴로지와 조직의 지리적 분포에 따라 부분적으로 달라 야 합니다.

  게이트웨이 토폴로지 옵션도 고려해야 합니다(자세한 내용은 이 항목 의 부분에 있는 게이트웨이 토폴로지 참조).

#### <a name="mn-trunk-support"></a>M:N 트렁크 지원

중재 서버는 여러 게이트웨이, 인터넷 전화 통신 서비스 공급자가 제공하는 SC(Session Border Controller) 또는 두 가지의 조합을 통해 통화를 라우팅할 수 있습니다. 또한 풀의 여러 중재 서버가 여러 게이트웨이와 상호 작용할 수 있습니다. 중재 서버와 게이트웨이 간에 정의된 논리적 경로를 트렁크라고 합니다. 내부 사용자가 PSTN 통화를 걸면 프런트 엔드 풀의 아웃바운드 라우팅 논리에서 특정 통화를 라우팅하는 데 사용할 수 있는 가능한 모든 조합에서 라우팅할 트렁크를 선택합니다. DNS 부하 분산을 사용하는 경우 풀의 특정 중재 서버와의 문제로 인해 통화가 게이트웨이에 연결되지 않으면 통화가 풀의 대체 중재 서버로 다시 시도됩니다.

여러 게이트웨이를 계획하는 데 대한 자세한 내용은 비즈니스용 [Skype 서버의 M:N 트렁크를 참조하세요.](m-n-trunk.md)

기타 아웃바운드 라우팅 기능 향상에 대한 자세한 내용은 [Call Routes을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes)

#### <a name="gateway-topologies"></a>게이트웨이 토폴로지

게이트웨이 배포에 대한 기본적인 질문을 고려할 때 다음 단계를 따르세요.

1. 웹 사이트를 사용하여 PSTN 연결을 제공할 사이트의 개수를 Enterprise Voice.

2. 각 사이트의 트래픽을 예측합니다(사용자 수 및 사용자당 평균 시간당 통화 수).

3. 예상 트래픽을 처리하기 위해 각 사이트에 하나 이상의 게이트웨이를 배포합니다.

이 토폴로지에서는 각 사이트의 작업자와 사이트 간의 통화가 모두 인트라넷을 통해 라우팅됩니다. PSTN에 대한 통화는 엔터프라이즈 IP 네트워크를 통해 대상 번호의 위치에 가장 가까운 게이트웨이로 라우팅됩니다. 그러나 조직에서 하나 이상의 대륙에 분산된 수십 또는 수백 또는 수천 개의 사이트를 지원하는 경우 많은 금융 기관 및 기타 대기업은 어떻게 하나요? 이러한 경우 각 사이트에 별도의 게이트웨이를 배포하는 것은 실용적이지 않습니다.

이 문제를 해결하기 위해 많은 대기업에서는 대규모 전화 통신 중앙 사이트를 하나 또는 몇 개 배포하는 것을 선호합니다.

이 토폴로지에서는 예상되는 사용자 부하를 수용하기에 충분한 여러 개의 큰 게이트웨이가 각 중앙 사이트에 배포됩니다. 기업의 사용자에 대한 모든 통화는 회사의 전화 서비스 공급자가 중앙 사이트로 전달합니다. 중앙 사이트의 라우팅 논리에 따라 통화를 인트라넷을 통해 라우팅할지 아니면 PSTN으로 라우팅해야 하는지가 결정됩니다.

#### <a name="gateway-location"></a>게이트웨이 위치

또한 게이트웨이 위치에 따라 선택한 게이트웨이 유형과 게이트웨이가 구성되는 방식이 결정될 수 있습니다. 수십 개의 PSTN 프로토콜이 있습니다. 이 프로토콜은 전 세계 표준에 해당하지 않습니다. 모든 게이트웨이가 단일 국가/지역에 있는 경우 이는 문제가 되지 않지만 여러 국가/지역에서 게이트웨이를 찾는 경우 해당 국가/지역의 PSTN 표준에 따라 각각을 구성해야 합니다. 또한 캐나다와 같은 작업 인증을 받은 게이트웨이는 인도, 브라질 또는 유럽 연합에서 인증되지 않을 수 있습니다.

#### <a name="gateway-size-and-number"></a>게이트웨이 크기 및 번호

대부분의 조직에서 배포를 고려하는 PSTN 게이트웨이의 크기는 2~960개 포트입니다. 훨씬 더 큰 게이트웨이가 있지만 이러한 게이트웨이는 주로 전화 서비스 공급자에서 사용됩니다. 조직에 필요한 포트 수를 예측할 때 다음 지침을 사용하세요.

- 조명 전화 통신 사용이 있는 조직(시간당 PSTN 통화 1회)은 15명마다 하나의 포트를 할당해야 합니다. 예를 들어 사용자가 20명인 경우 포트가 두 개 있는 게이트웨이가 필요합니다.

- 전화 통신 사용량이 보통인 조직(사용자당 시간당 PSTN 통화 2개)은 10명마다 하나의 포트를 할당해야 합니다. 예를 들어 사용자가 100명인 경우 하나 이상의 게이트웨이에 총 10개 포트를 할당해야 합니다.

- 전화 통신 사용량이 많은 조직(사용자당 시간당 PSTN 통화 세 개 이상)은 5명마다 하나의 포트를 할당해야 합니다. 예를 들어 사용자가 47,000명인 경우 10개 이상의 대규모 게이트웨이에 총 9,400개 포트를 할당해야 합니다.

- 사용자 수 또는 조직의 트래픽 양이 증가하면 추가 포트를 확보할 수 있습니다.

지원해야 하는 사용자 수에 대해 더 적거나 큰 게이트웨이 또는 더 작은 게이트웨이를 배포할 수 있습니다. 일반적으로 하나의 게이트웨이에 오류가 발생하면 가용성을 유지하기 위해 조직에 대해 최소 두 개의 게이트웨이가 권장됩니다.

배포하는 각 PSTN 게이트웨이에는 해당 중재 서버가 하나 이상 있어야 합니다.