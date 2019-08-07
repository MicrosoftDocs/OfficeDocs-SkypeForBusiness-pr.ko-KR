---
title: 위치 기반 라우팅 용어
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅에 대 한 위치 기반 라우팅과 관련 된 용어 및 개념에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: db6d6892c8a3bda8d30ac61d0458f252a6ac9281
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36185015"
---
# <a name="location-based-routing-terminology"></a>위치 기반 라우팅 용어

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

위치 기반 라우팅 설명서에서 사용 되는 몇 가지 용어와 개념은 다음과 같습니다. 설명서를 더 자세히 살펴보기 전에 이러한 용어와 개념에 대해 잘 알고 있는 것이 좋습니다.

|각기  |설명  |
|---------|---------|
|네트워크 지역     | 네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다. 예를 들어 조직에 인도에 있는 사이트가 여러 개 있는 경우 "인도"를 네트워크 지역으로 지정 하도록 선택할 수 있습니다.        |
|네트워크 사이트    | 네트워크 사이트는 사무실, 건물 집합 또는 캠퍼스와 같이 조직이 실제 장소를 보유 하 고 있는 위치를 나타냅니다. 네트워크 사이트는 IP 서브넷의 모음으로 정의 됩니다. 위치 기반 라우팅에 대 한 모범 사례는 고유한 PSTN 연결이 있는 각 위치에 대해 별도의 사이트를 만드는 것입니다.  각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다. 위치 기반 라우팅이나 위치 기반 라우팅에 사용할 수 없는 사이트를 만들 수 있습니다. 예를 들어 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 사이트를 만들어 해당 사이트로 로밍할 때 PSTN 통화를 할 수 있도록 위치 기반 회람을 사용 하도록 설정 하는 것이 좋습니다. 네트워크 사이트는 비상 전화를 사용 하 고 구성 하는 데도 사용 될 수 있습니다.        |
|네트워크 서브넷     |팀 끝점이 네트워크에 연결할 수 있는 위치의 IP 서브넷은 정의 된 네트워크와 연결 되어 수신자의 바이패스를 보장 해야 합니다. 여러 서브넷이 같은 네트워크 사이트에 연결 되어 있을 수 있지만 여러 사이트가 동일한 서브넷에 연결 되지 않을 수 있습니다. 서브넷 연결을 사용 하면 위치 기반 라우팅이 끝점을 찾아 지리적으로 지정 된 PSTN 통화를 허용 해야 하는지 여부를 결정할 수 있습니다. IPv6 및 IPv4 서브넷이 모두 지원 됩니다. 팀 종단점이 사이트에 있는지 여부를 결정할 때 위치 기반 라우팅은 먼저 일치 하는 IPv6 주소를 확인 합니다. IPv6 주소가 없으면 위치 기반 라우팅이 IPv4 주소를 확인 합니다. <br><br>
|신뢰할 수 있는 외부 IP 주소    |신뢰할 수 있는 외부 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소입니다. 특정 사이트 일치를 확인 하기 전에 사용자의 끝점이 회사 네트워크 내에 있는지 여부를 결정 합니다. 사용자의 외부 IP가 신뢰할 수 있는 목록에 정의 된 IP 주소와 일치 하는 경우 위치 기반 라우팅에서 사용자의 끝점이 있는 내부 서브넷을 확인 합니다. 사용자의 외부 IP 주소가 신뢰할 수 있는 목록에 정의 된 IP 주소와 일치 하지 않는 경우 끝점은 알 수 없는 위치에 있는 것으로 분류 되며 위치 기반 라우팅에 대해 설정 된 사용자에 대 한 PSTN 호출이 차단 됩니다.          |

### <a name="related-topics"></a>관련 항목
- [직접 라우팅에 대 한 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [위치 기반 라우팅에 대 한 네트워크 설정 구성](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
