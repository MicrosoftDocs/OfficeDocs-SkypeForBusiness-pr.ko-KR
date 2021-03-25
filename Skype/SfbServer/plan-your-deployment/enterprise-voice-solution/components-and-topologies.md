---
title: 비즈니스용 Skype의 통화 입장 제어에 대한 구성 요소 및 토폴로지
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
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX가 있는 경우 CAC(통화 제어)에 대한 계획 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109194"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>비즈니스용 Skype의 통화 입장 제어에 대한 구성 요소 및 토폴로지

MPLS 네트워크, SIP 트렁크 또는 타사 PSTN 게이트웨이 또는 PBX가 있는 경우 CAC(통화 제어)에 대한 계획 비즈니스용 Skype 서버 Enterprise Voice.

이 섹션의 항목에서는 다양한 네트워크 토폴로지 유형으로 CAC(통화 허용 제어)를 배포할 때의 특별 고려 사항에 대한 정보를 제공합니다.

## <a name="call-admission-control-on-an-mpls-network"></a>MPLS 네트워크의 통화 입장 제어

MPLS(Multiprotocol Label Switching) 네트워크에서는 모든 사이트가 풀 메쉬로 연결됩니다. 즉, 모든 사이트가 인터넷 서비스 공급자의 MPLS 백본에 직접 연결되며 각 사이트에는 MPLS 클라우드에 대한 WAN 링크에 사용할 대역폭이 프로비전됩니다. IP 라우팅을 제어하는 네트워크 허브 또는 중앙 사이트는 없습니다. 다음 그림에서는 MPLS 기술을 기반으로 하는 간단한 네트워크를 보여 줍니다.

**예제 MPLS 네트워크**

![MPLS가 있는 CAC](../../media/CAC_MPLS_1.jpg)

MPLS 네트워크에서 CAC(통화 허용 제어)를 배포하려면 MPLS 클라우드를 나타내는 네트워크 지역을 만든 다음 각 MPLS 위성 사이트를 나타내는 네트워크 사이트를 만듭니다. 다음 그림에서는 위 그림의 예제 MPLS 네트워크를 나타내도록 네트워크 지역 및 네트워크 사이트를 구성하는 방법을 보여 줍니다. 전체 대역폭 제한 및 대역폭 세션 제한은 각 네트워크 사이트에서 MPLS 클라우드를 나타내는 네트워크 지역으로의 WAN 링크 용량을 기반으로 합니다.

**MPLS 네트워크의 네트워크 지역 및 네트워크 사이트**

![MPLS 다이어그램을 사용하는 CAC(통화 입장 제어)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP 트렁크의 통화 입장 제어

SIP 트렁크에 CAC(통화 허용 제어)를 배포하려면 ITSP(인터넷 전화 통신 서비스 공급자)를 나타내는 네트워크 사이트를 만듭니다. SIP 트렁크에 대역폭 정책 값을 적용하려면 엔터프라이즈의 네트워크 사이트와 ITSP를 나타내기 위해 만든 네트워크 사이트 간의 사이트 간 정책을 만듭니다.

다음 그림에서는 SIP 트렁크에 대한 예제 CAC 배포를 보여 줍니다.

**SIP 트렁크에 대한 CAC 구성**

![통화 입장 제어 SIP 트렁크 다이어그램](../../media/CAC_SIP_trunk_1.jpg)

SIP 트렁크에 CAC를 구성하려면 CAC 배포 중에 다음 작업을 수행해야 합니다.

1. ITSP를 나타내는 네트워크 사이트를 만듭니다. 네트워크 사이트를 적절한 네트워크 지역에 연결하고 이 네트워크 사이트에 오디오 및 비디오 대역폭으로 0을 할당합니다. 자세한 내용은 배포 설명서의 [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac)을 참조하십시오.

    > [!NOTE]
    > ITSP에 대해서는 이 네트워크 사이트 구성이 작동하지 않습니다. 대역폭 정책 값은 2단계에서 실제로 적용됩니다.

2. 1단계에서 만든 사이트에 대한 관련 매개 변수 값을 사용하여 SIP 트렁크에 대한 사이트 간 링크를 만듭니다. 예를 들어 엔터프라이즈의 네트워크 사이트 이름을 NetworkSiteID1 매개 변수 값으로 사용하고 ITSP 네트워크 사이트를 NetworkSiteID2 매개 변수 값으로 사용합니다. 자세한 내용은 배포 설명서에서 [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) 및 [New-CsNetworkInterSitePolicy를 참조하십시오.](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)

3. ITSP에서 SCB(Session Border Controller)의 미디어 종료 지점의 IP 주소를 얻습니다. 해당 IP 주소(서브넷 마스크 32 포함)를 ITSP를 나타내는 네트워크 사이트에 추가합니다. 자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>타사 PSTN 게이트웨이 또는 PBX를 사용하여 통화할 수 있는 제어

이 항목에서는 중재 서버의 게이트웨이 인터페이스와 타사 PSTN(Public Switched Telephone Network) 게이트웨이 또는 PBX(Private Branch Exchange) 간의 링크에 CAC(통화 제어)를 배포할 수 있는 방법의 예를 설명합니다.

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC

CAC는 중재 서버의 게이트웨이 인터페이스에서 타사 PBX 또는 PSTN 게이트웨이로의 WAN 링크에 배포할 수 있습니다.

**사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC**

![사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC](../../media/CAC_gateways_1.jpg)

이 예에서 CAC는 중재 서버와 PSTN 게이트웨이 간에 적용됩니다. 네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2의 PSTN 게이트웨이를 통해 PSTN 통화를 걸면 미디어가 WAN 링크를 통해 흐르게 됩니다. 따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.

- 비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간

- 중재 서버와 PSTN 게이트웨이 간

이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트 응용 프로그램에서 거는 발신 PSTN 전화 모두에 적용됩니다.

> [!NOTE]
> PSTN 게이트웨이가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.

> [!NOTE]
> 중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.

> [!NOTE]
> 자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>사례 2: 중재 서버와 미디어 종료 지점이 있는 타사 PBX 간의 CAC

이 구성은 사례 1과 유사합니다. 두 사례 모두 중재 서버에서 장치가 WAN 링크의 반대쪽 끝에서 미디어를 종료함을 인식하며, MTP(미디어 종료 지점)가 있는 PBX 또는 PSTN 게이트웨이의 IP 주소가 중재 서버에 다음 홉으로 구성됩니다.

**사례 2: 중재 서버와 MTP가 있는 타사 PBX 간의 CAC**

![사례 2: MTP를 통해 중재 서버 PBX 간의 CAC](../../media/CAC_gateways_2.jpg)

이 예에서 CAC는 중재 서버와 PBX/MTP 간에 적용됩니다. 네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 네트워크 사이트 2에 있는 PBX/MTP를 통해 PSTN 통화를 걸면 미디어가 WAN 링크를 통해 흐르게 됩니다. 따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.

- 비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간

- 중재 서버와 PBX/MTP 간

이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트에서 거는 발신 PSTN 전화 모두에 적용됩니다.

> [!NOTE]
> MTP가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.

> [!NOTE]
> 중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.

> [!NOTE]
> 자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>사례 3: 중재 서버와 미디어 종료 지점이 없는 타사 PBX 간의 CAC

사례 3은 처음 두 사례와 약간 다릅니다. 타사 PBX에 MTP가 없는 경우 타사 PBX에 대한 발신 세션 요청에 대해 중재 서버에서 미디어가 종료되는 PBX 경계 내 위치를 알지 못합니다. 이 경우 미디어가 중재 서버와 타사 끝점 장치 간에 직접 전송됩니다.

**사례 3: 중재 서버와 MTP가 없는 타사 PBX 간의 CAC**

![사례 3: 중재 서버 PBX MTP 없음 간의 CAC](../../media/CAC_gateways_3.jpg)

이 예에서 네트워크 사이트 1의 비즈니스용 Skype 클라이언트 사용자가 PBX를 통해 사용자에게 전화를 걸면 중재 서버는 프록시 레그(비즈니스용 Skype 클라이언트 응용 프로그램과 중재 서버 간)에서만 CAC 확인을 수행할 수 있습니다. 세션이 요청되는 동안 중재 서버에 끝점 장치에 대한 정보가 없으므로 통화가 연결되기 전에 WAN 링크(중재 서버와 타사 끝점 간)에서 CAC 확인을 수행할 수 없습니다. 그러나 세션이 설정된 후에는 중재 서버가 트렁크에서 사용되는 대역폭 관리를 지원합니다.

타사 끝점에서 발신된 전화의 경우에는 세션 요청 시 해당 끝점 장치에 대한 정보를 사용할 수 있으므로 중재 서버의 양쪽에서 CAC 확인을 수행할 수 있습니다.

> [!NOTE]
> 끝점 장치가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.

> [!NOTE]
> 중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.

> [!NOTE]
> 자세한 내용은 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하십시오.