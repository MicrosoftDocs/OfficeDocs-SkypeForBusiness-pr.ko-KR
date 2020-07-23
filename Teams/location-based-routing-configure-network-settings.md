---
title: 네트워크 설정 구성-위치 기반 라우팅
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅에 대 한 위치 기반 라우팅에 대 한 네트워크 지역, 사이트 및 서브넷을 만들고 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8025467a0581c95a40551244948a8e6b7c0ecbc8
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372063"
---
# <a name="configure-network-settings-for-location-based-routing"></a>위치 기반 라우팅의 네트워크 설정 구성

아직 수행 하지 않은 경우 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하기 전에 수행 해야 하는 다른 단계를 검토 하도록 [직접 라우팅 계획 위치 기반 라우팅을](location-based-routing-plan.md) 읽어 보세요.

이 문서에서는 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하는 방법을 설명 합니다. 조직에 직접 전화 시스템 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정 하는 것입니다.

## <a name="define-network-regions"></a>네트워크 지역 정의

네트워크 지역에는 네트워크 사이트 컬렉션이 포함 되며 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다. 네트워크 지역을 구성 하는 방법에 대 한 단계는 [팀의 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.

## <a name="define-network-sites"></a>네트워크 사이트 정의

네트워크 사이트는 사무실, 건물 집합 또는 캠퍼스와 같이 조직이 실제 장소를 보유 하 고 있는 위치를 나타냅니다. 토폴로지의 각 네트워크 사이트를 네트워크 영역과 연결 해야 합니다. 네트워크 사이트를 구성 하는 방법에 대 한 단계는 [팀에서 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.

위치 기반 라우팅에 대 한 모범 사례는 고유한 PSTN 연결이 있는 각 위치에 대해 별도의 사이트를 만드는 것입니다. 위치 기반 라우팅이나 위치 기반 라우팅에 사용할 수 없는 사이트를 만들 수 있습니다. 예를 들어 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 사이트를 만들어 해당 사이트로 로밍할 때 PSTN 통화를 할 수 있도록 위치 기반 회람을 사용 하도록 설정 하는 것이 좋습니다.

## <a name="define-network-subnets"></a>네트워크 서브넷 정의

각 서브넷은 특정 네트워크 사이트에 연결 되어 있어야 합니다. 여러 서브넷을 동일한 네트워크 사이트에 연결할 수 있지만 여러 사이트를 동일한 서브넷에 연결할 수는 없습니다. 네트워크 서브넷을 구성 하는 방법에 대 한 단계는 [팀의 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.

위치 기반 라우팅의 경우 팀 끝점이 네트워크에 연결 될 수 있는 위치에 있는 IP 서브넷을 정의 하 고 정의 된 네트워크에 연결 해야 수신자의 부담을 피할 수 있습니다. 서브넷 연결을 사용 하면 위치 기반 라우팅이 끝점을 찾아 지리적으로 지정 된 PSTN 통화를 허용 해야 하는지 여부를 결정할 수 있습니다. IPv6 및 IPv4 서브넷이 모두 지원 됩니다. 팀 종단점이 사이트에 있는지 여부를 결정할 때 위치 기반 라우팅은 먼저 일치 하는 IPv6 주소를 확인 합니다. IPv6 주소가 없으면 위치 기반 라우팅이 IPv4 주소를 확인 합니다.

## <a name="define-trusted-ip-addresses-external-subnets"></a>신뢰할 수 있는 IP 주소 정의 (외부 서브넷)

신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 이며 사용자의 끝점이 회사 네트워크 내에 있는지 여부를 확인 하는 데 사용 됩니다. 신뢰할 수 있는 IP 주소를 구성 하는 방법에 대 한 단계는 [팀의 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.

사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치 하는 경우 위치 기반 라우팅에서 사용자의 끝점이 있는 내부 서브넷을 확인 합니다. 사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 정의 된 IP 주소와 일치 하지 않는 경우 끝점은 알 수 없는 위치에 있는 것으로 분류 되며 위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자에 대 한 PSTN 호출이 차단 됩니다.

## <a name="next-steps"></a>다음 단계

[직접 라우팅에 대해 위치 기반 라우팅 사용](location-based-routing-enable.md)으로 이동 합니다.

## <a name="related-topics"></a>관련 항목

- [팀의 클라우드 음성 기능에 대 한 네트워크 설정](cloud-voice-network-settings.md)
