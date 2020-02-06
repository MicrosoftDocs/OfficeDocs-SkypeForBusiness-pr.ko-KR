---
title: 비즈니스용 Skype의 통화 허용 제어에 대 한 구성 요소 및 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX를 사용 하는 경우에는 호출 허용 제어 (CAC) 계획을 수립 합니다. 비즈니스용 Skype Server Enterprise Voice에 적용 됩니다.
ms.openlocfilehash: 7fcbc3e8c7fc7b4139fd9c83718db59af099f47f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803118"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>비즈니스용 Skype의 통화 허용 제어에 대 한 구성 요소 및 토폴로지

MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX를 사용 하는 경우에는 호출 허용 제어 (CAC) 계획을 수립 합니다. 비즈니스용 Skype Server Enterprise Voice에 적용 됩니다.

이 섹션의 항목은 다양 한 유형의 네트워크 토폴로지에 대해 CAC (call 허용 제어) 배포에 대 한 특별 고려 사항에 대 한 정보를 제공 합니다.

## <a name="call-admission-control-on-an-mpls-network"></a>MPLS 네트워크의 통화 허용 제어

멀티 프로토콜 레이블 전환 (MPLS) 네트워크에서 모든 사이트는 풀 메시로 연결 됩니다. 즉, 모든 사이트가 인터넷 서비스 공급자의 MPLS 백본으로 직접 연결 되며, 각 사이트는 MPLS 클라우드의 WAN 링크에서 사용할 수 있도록 프로 비전 된 대역폭을 제공 합니다. IP 라우팅을 제어 하는 네트워크 허브나 중앙 사이트는 없습니다. 다음 그림은 MPLS 기술을 기반으로 하는 간단한 네트워크를 보여줍니다.

**예제 MPLS 네트워크**

![MPLS를 사용하는 CAC](../../media/CAC_MPLS_1.jpg)

MPLS 네트워크에 CAC (call 허용 제어)를 배포 하려면 MPLS 클라우드를 나타내는 네트워크 영역을 만들고 각 MPLS 위성 사이트를 나타내는 네트워크 사이트를 만듭니다. 다음 그림에서는 네트워크 지역과 네트워크 사이트를 구성 하 여 이전 그림의 예제 MPLS 네트워크를 표시 하는 방법을 보여 줍니다. 각 네트워크 사이트에서 MPLS 클라우드를 나타내는 네트워크 지역으로의 WAN 링크 용량을 기준으로 전체 대역폭 한도와 대역폭 세션 한도가 적용 됩니다.

**MPLS 네트워크에 대 한 네트워크 지역 및 네트워크 사이트**

![MPLS를 사용하는 CAC(통화 허용 제어) 다이어그램](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP 트렁크에 대한 통화 허용 제어 서비스

SIP 트렁크에 CAC (call 허용 제어)를 배포 하려면 네트워크 사이트를 만들어 인터넷 통신 서비스 공급자 (ITSP)를 나타냅니다. SIP 트렁크에 대역폭 정책 값을 적용 하려면 엔터프라이즈의 네트워크 사이트와 ITSP를 나타내기 위해 만드는 네트워크 사이트 간에 사이트 간 정책을 만듭니다.

다음 그림에서는 SIP 트렁크에 대 한 CAC 배포의 예를 보여 줍니다.

**SIP 트렁크의 CAC 구성**

![통화 허용 제어 SIP 트렁크 다이어그램](../../media/CAC_SIP_trunk_1.jpg)

SIP 트렁크에서 CAC를 구성 하려면 CAC 배포 중에 다음 작업을 수행 해야 합니다.

1. ITSP를 나타내는 네트워크 사이트를 만듭니다. 네트워크 사이트를 적절 한 네트워크 영역에 연결 하 고이 네트워크 사이트의 오디오 및 비디오에 대 한 대역폭을 0으로 할당 합니다. 자세한 내용은 배포 설명서에서 [CAC에 대 한 네트워크 사이트 구성을](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) 참조 하세요.

    > [!NOTE]
    > ITSP의 경우이 네트워크 사이트 구성은 작동 하지 않습니다. 대역폭 정책 값은 2 단계에서 실제로 적용 됩니다.

2. 1 단계에서 만든 사이트의 관련 매개 변수 값을 사용 하 여 SIP 트렁크에 대 한 사이트 간 링크를 만듭니다. 예를 들어 엔터프라이즈의 네트워크 사이트 이름을 NetworkSiteID1 매개 변수 값으로 사용 하 고 ITSP 네트워크 사이트의 NetworkSiteID2 매개 변수 값으로 사용할 것입니다. 자세한 내용은 배포 설명서 및 [새 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)의 비즈니스용 [Skype 서버에서 네트워크 사이트 간 정책 만들기](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) 를 참조 하세요.

3. ITSP에서 SCB (세션 경계 컨트롤러) 미디어 종료 지점의 IP 주소를 가져옵니다. ITSP를 나타내는 네트워크 사이트에 32의 서브넷 마스크를 사용 하 여 해당 IP 주소를 추가 합니다. 자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>타사 PSTN 게이트웨이 또는 PBX에 대한 통화 허용 제어 서비스

이 항목에서는 중재 서버의 게이트웨이 인터페이스와 타사의 PSTN (공개 교환 통신 네트워크) 게이트웨이 또는 PBX (개인 분기 교환) 간의 링크에 CAC (call 허용 제어)를 배포 하는 방법의 예를 설명 합니다.

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC

CAC는 중재 서버의 게이트웨이 인터페이스에서 타사 PBX 또는 PSTN 게이트웨이로의 WAN 링크에 배포할 수 있습니다.

**사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC**

![사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC](../../media/CAC_gateways_1.jpg)

이 예제에서는 중재 서버와 PSTN 게이트웨이 간에 CAC가 적용 됩니다. 네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2의 PSTN 게이트웨이를 통해 PSTN 통화를 하는 경우 미디어는 WAN 링크를 통해 흐릅니다. 따라서 각 PSTN 세션에 대해 다음 두 가지 CAC 검사를 수행 합니다.

- 비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간

- 중재 서버와 PSTN 게이트웨이 간의 관계

이는 네트워크 사이트 1의 클라이언트로 들어오는 PSTN 통화와 네트워크 사이트 1의 클라이언트 응용 프로그램에서 보내는 PSTN 통화에 대해 모두 작동 합니다.

> [!NOTE]
> PSTN 게이트웨이가 속한 IP 서브넷이 구성 되어 있고 네트워크 사이트 2에 연결 되어 있는지 확인 합니다.

> [!NOTE]
> 중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.

> [!NOTE]
> 자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>사례 2: 중재 서버와 미디어 종료 지점이 있는 타사 PBX 간의 CAC

이 구성은 사례 1과 유사 합니다. 두 경우 모두 중재 서버는 WAN 링크의 반대편에 있는 장치가 미디어를 종료 하는 것을 인식 하 고 MTP (미디어 종료 지점)를 사용 하는 PSTN 게이트웨이 또는 PBX의 IP 주소는 조정 서버에서 다음 홉으로 구성 됩니다.

**사례 2: 중재 서버와 MTP를 사용 하 여 타사 PBX 간의 CAC**

![사례 2: 중재 서버 PBX(MTP 포함) 간의 CAC](../../media/CAC_gateways_2.jpg)

이 예제에서는 중재 서버와 PBX/MTP 사이에 CAC가 적용 됩니다. 네트워크 사이트 1에 있는 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2에 있는 PBX/MTP를 통해 PSTN 통화를 하는 경우 미디어는 WAN 링크를 통해 흐릅니다. 따라서 각 PSTN 세션에 대해 다음 두 CAC 검사를 수행 합니다.

- 비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간

- 중재 서버와 PBX/MTP 사이

네트워크 사이트 1의 클라이언트로 들어오는 PSTN 통화와 네트워크 사이트 1의 클라이언트에서 보내는 PSTN 통화를 모두 사용할 수 있습니다.

> [!NOTE]
> MTP가 속해 있는 IP 서브넷이 구성 되어 있고 네트워크 사이트 2에 연결 되어 있는지 확인 합니다.

> [!NOTE]
> 중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.

> [!NOTE]
> 자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>사례 3: 중재 서버와 미디어 종료 지점이 없는 타사 PBX 간의 CAC

사례 3은 처음 두 경우와 약간 다릅니다. 타사 PBX에 MTP가 없는 경우, 타사 PBX로 보내는 세션 요청에 대해 중재 서버는 PBX 경계에서 미디어가 종료 되는 위치를 알 수 없습니다. 이 경우 미디어는 중재 서버와 타사 끝점 디바이스 간에 직접 흐릅니다.

**사례 3: 중재 서버와 MTP 없이 타사 PBX 간의 CAC**

![사례 3: 중재 서버 PBX(MTP 미포함) 간의 CAC](../../media/CAC_gateways_3.jpg)

이 예제에서는 네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 PBX를 통해 사용자에 게 전화를 거는 경우 중재 서버는 프록시 레그 에서만 CAC 확인을 수행할 수 있습니다 (비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간). 중재 서버는 세션을 요청 하는 동안 끝점 장치에 대 한 정보를 포함 하지 않으므로 호출 설정 전에 중재 서버와 타사 끝점 간의 WAN 링크에서 CAC 검사를 수행할 수 없습니다. 그러나 세션이 설정 된 후에는 중재 서버에서 트렁크에 사용 되는 대역폭에 대 한 계정을 쉽게 관리할 수 있습니다.

타사 끝점에서 시작 되는 통화의 경우 해당 끝점 장치에 대 한 정보는 세션 요청 시 사용할 수 있으며 CAC 검사는 중재 서버의 양쪽에서 수행할 수 있습니다.

> [!NOTE]
> 끝점 디바이스가 속한 IP 서브넷이 네트워크 사이트 2와 연결 되어 있는지 확인 합니다.

> [!NOTE]
> 중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.

> [!NOTE]
> 자세한 내용은 [네트워크 사이트와 서브넷 연결](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)을 참조 하세요.


