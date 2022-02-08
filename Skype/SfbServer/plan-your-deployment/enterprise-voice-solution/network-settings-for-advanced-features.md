---
title: Enterprise Voice 고급 보안 기능에 대한 네트워크 비즈니스용 Skype 서버
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
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: 네트워크 지역, 네트워크 사이트 및 IP 서브넷에 대해 자세히 알아보습니다. 이러한 모든 구성은 비즈니스용 Skype, 비즈니스용 Skype 서버의 통화 비즈니스용 Skype 서버 계획 또는 2016년 8월의 응급 서비스에 대한 계획을 배포하도록 비즈니스용 Skype 서버 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 77472a77f26139f7a15f0a3820e6fb90a798a5b7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391880"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Enterprise Voice 고급 보안 기능에 대한 네트워크 비즈니스용 Skype 서버

네트워크 지역, 네트워크 사이트 및 IP 서브넷에 대해 자세히 알아보습니다. 이러한 모든 구성은 [비즈니스용 Skype, 비즈니스용 Skype 서버](media-bypass.md)의 통화 비즈니스용 Skype 서버 제어 계획 또는 2016년 8[](call-admission-control.md)월의 응급 서비스 계획에서 비즈니스용 Skype 서버 배포하도록 비즈니스용 Skype 서버 [](emergency-services.md) Enterprise Voice.

비즈니스용 Skype 서버 고급 Enterprise Voice 기능인 비즈니스용 Skype 서버, 비즈니스용 Skype 서버 응급 서비스 계획 및 미디어 우회 계획의 세 가지 고급 서비스 기능이 있습니다[](emergency-services.md)[.](call-admission-control.md)[ 비즈니스용 Skype](media-bypass.md). 이러한 기능은 네트워크 지역, 네트워크 사이트 및 네트워크 사이트와 네트워크 사이트와의 비즈니스용 Skype 서버 각 서브넷의 연결에 대한 특정 구성 요구 사항을 공유합니다.

이 항목에서는 이러한 세 가지 고급 구성 기능 모두에 공통된 구성 요구 사항에 Enterprise Voice 제공합니다.

## <a name="network-regions"></a>네트워크 지역

네트워크 지역은 CAC(통화 허용 제어), E9-1-1 및 미디어 바이패스 구성에만 사용되는 네트워크 허브 또는 네트워크 백본입니다.

> [!NOTE]
> 네트워크 지역은 비즈니스용 Skype 서버 전화 접속 회의 액세스 번호를 하나 이상의 전화 접속 다이얼 플랜과 연결해야 하는 비즈니스용 Skype 서버 동일하지 않습니다. 전화 접속 회의 지역에 대한 자세한 내용은 [Planning for Dial-In Conferencing을 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements).

CAC를 사용하려면 모든 네트워크 지역에 지역 내의 미디어 트래픽을 관리하는 연결된 비즈니스용 Skype 서버 중앙 사이트가 필요합니다(즉, 실시간 오디오 또는 비디오 세션을 설정할 수 있는지 여부에 대해 구성한 정책에 따라 의사 결정을 내릴 수 있습니다). 비즈니스용 Skype 서버 중앙 사이트는 지리적 위치를 나타내는 것이 아니라 풀 또는 풀 집합으로 구성된 논리적 서버 그룹을 나타내지 않습니다.

네트워크 지역을 구성하려면 비즈니스용 Skype 서버 제어판의 네트워크 구성 섹션  에 있는 지역 탭을  사용하여 **New-CsNetworkRegion 또는 Set-CsNetworkRegion** cmdlet을  비즈니스용 Skype 서버 수 있습니다. 자세한 내용은 배포 설명서에서 [Deploy network regions, sites and subnets in 비즈니스용 Skype](../../deploy/deploy-enterprise-voice/deploy-network.md), or see the 비즈니스용 Skype 서버 Management Shell 설명서를 참조하십시오.

세 가지 고급 보안 기능 모두에서 동일한 네트워크 지역 정의를 Enterprise Voice 있습니다. 따라서 하나의 기능에 대한 네트워크 지역을 이미 만든 경우 다른 기능에 대한 새 네트워크 지역을 만들 필요가 없습니다. 그러나 기능별 설정을 적용하기 위해 기존 네트워크 지역 정의를 수정해야 하는 경우가 있을 수 있습니다. 예를 들어 E9-1-1(연결된 중앙 사이트 필요 없음)에 대한 네트워크 지역을 만들고 나중에 통화 허용 제어를 배포한 경우 각 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다.

비즈니스용 Skype 서버 중앙 사이트를 네트워크 지역과 연결하려면 비즈니스용 Skype 서버 제어판의 네트워크 구성 섹션을 사용하여 또는 **New-CsNetworkRegion 또는 Set-CsNetworkRegion** cmdlet을 실행하여 중앙 사이트 이름을 지정합니다.  자세한 내용은 배포 설명서에서 [Deploy network regions, sites and subnets in 비즈니스용 Skype](../../deploy/deploy-enterprise-voice/deploy-network.md), or see the 비즈니스용 Skype 서버 Management Shell 설명서를 참조하십시오.

## <a name="network-sites"></a>네트워크 사이트

네트워크 사이트는 지점, 지사 또는 본사와 같은 지리적 위치를 나타냅니다. 각 네트워크 사이트는 특정 네트워크 지역과 연결되어야 합니다.

> [!NOTE]
> 네트워크 사이트는 고급 사이트 및 Enterprise Voice 사용됩니다. 이러한 사이트는 해당 토폴로지에서 구성한 분기 사이트와 비즈니스용 Skype 서버 않습니다.

네트워크 사이트를 구성하고 네트워크 지역과 연결하려면 비즈니스용 Skype 서버 제어판의 네트워크 구성 섹션을 사용하거나 비즈니스용 Skype 서버  관리 셸 **New-CsNetworkSite 또는 Set-CsNetworkSite** cmdlet을 실행할 수 있습니다. 자세한 내용은 배포 설명서에서 [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)를 참조하십시오. 또는 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.

## <a name="identify-ip-subnets"></a>IP 서브넷 확인

각 네트워크 사이트에 대해 네트워크 관리자와 함께 각 네트워크 사이트에 지정된 IP 서브넷을 확인해야 합니다. 네트워크 관리자가 네트워크 지역 및 네트워크 사이트에 대한 IP 서브넷을 이미 구성한 경우에는 작업이 훨씬 간편합니다.

예를 들어 북미 지역의 뉴욕 사이트에 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24 IP 서브넷을 지정할 수 있습니다. 주로 디트로이트에서 근무하는 Bob이 교육을 받기 위해 뉴욕 사무실에 출장을 왔다고 가정해 보겠습니다. Bob이 컴퓨터를 켜고 네트워크에 연결하면 컴퓨터에서 뉴욕에 할당된 네 개 범위 중 하나의 IP 주소(예: 172.29.80.103)를 가져옵니다.

> [!CAUTION]
> 서버에서 네트워크를 구성하는 동안 지정된 IP 서브넷을 미디어 바이패스에 사용하려면 IP 서브넷이 클라이언트 컴퓨터에서 제공한 형식과 일치해야 합니다. 비즈니스용 Skype 클라이언트는 로컬 IP 주소를 사용하여 연결된 서브넷 마스크로 IP 주소를 마스킹합니다. 각 클라이언트에 연결된 바이패스 ID를 확인할 때 등록자는 각 네트워크 사이트에 연결된 IP 서브넷 목록이 클라이언트에서 제공한 서브넷과 정확히 일치하는지 비교합니다. 따라서 서버에서 네트워크를 구성할 때 가상 서브넷 대신 실제 서브넷을 입력해야 합니다. (미디어 우회는 배포하지만 미디어 우회는 배포하지 않는 경우 가상 서브넷을 구성한 경우에도 통화 입장 제어가 제대로 작동합니다.) 예를 들어 비즈니스용 Skype 클라이언트가 IP 주소가 172.29.81.57인 컴퓨터에 IP 서브넷 마스크가 255.255.255.0인 경우 서브넷 172.29.81.0과 연결된 우회 ID를 요청합니다. 서브넷이 172.29.0.0/16으로 정의되어 있는 경우 클라이언트가 가상 서브넷에 속해 있기는 하지만 등록자가 서브넷 172.29.81.0을 구체적으로 찾고 있기 때문에 등록자는 이 일치를 고려하지 않습니다. 따라서 관리자가 정적으로 또는 DHCP(Dynamic Host Configuration Protocol)를 사용하여 네트워크 구성 중에 서브넷으로 프로비전되는 비즈니스용 Skype 클라이언트에서 제공하는 서브넷을 입력해야 합니다.

## <a name="associating-subnets-with-network-sites"></a>서브넷과 네트워크 사이트 연결

엔터프라이즈 네트워크의 모든 서브넷은 네트워크 사이트와 연결되어야 합니다(즉, 모든 서브넷을 지리적 위치와 연결해야 합니다). 이러한 서브넷 연결은 고급 Enterprise Voice 끝점을 지리적으로 찾을 수 있도록 합니다. 예를 들어 끝점을 찾기 위해 CAC는 네트워크 사이트에서 들어오고오는 실시간 오디오 및 비디오 데이터의 흐름을 규제할 수 있습니다.

서브넷을 네트워크 사이트와 연결하려면 비즈니스용 Skype 서버 제어판의 네트워크 구성 섹션을  사용할 수도 비즈니스용 Skype 서버 있습니다. 자세한 내용은 배포 설명서에서 [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)을 참조하거나 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.

## <a name="see-also"></a>참고 항목

[2016년 8월 통화 비즈니스용 Skype 서버](call-admission-control.md)

[2016년 8월의 응급 비즈니스용 Skype 서버](emergency-services.md)

[2013의 미디어 우회 비즈니스용 Skype](media-bypass.md)