---
title: 네트워크 설정 구성 - 위치 기반 라우팅
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅에 대한 Location-Based 네트워크 지역, 사이트 및 서브넷을 만들고 설정하는 방법을 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822948"
---
# <a name="configure-network-settings-for-location-based-routing"></a>위치 기반 라우팅의 네트워크 설정 구성

아직 수행하지 않은 경우 직접 [](location-based-routing-plan.md) 라우팅에 대한 Location-Based 계획 및 라우팅을 참조하여 라우팅에 대한 네트워크 설정을 구성하기 전에 필요한 다른 단계를 Location-Based 합니다.

이 문서에서는 라우팅에 대한 네트워크 설정을 구성하는 Location-Based 설명하고 있습니다. 조직에서 전화 시스템 직접 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정하는 것입니다.

## <a name="define-network-regions"></a>네트워크 지역 정의

네트워크 지역은 네트워크 사이트 모음을 포함하며 여러 지리적 영역에 걸쳐 네트워크의 다양한 부분을 상호 연결합니다. 네트워크 지역을 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리로 이동하세요.](manage-your-network-topology.md)

## <a name="define-network-sites"></a>네트워크 사이트 정의

네트워크 사이트는 사무실, 건물 집합 또는 캠퍼스와 같은 물리적 장소가 있는 조직을 나타내는 위치입니다. 토폴로지의 각 네트워크 사이트를 네트워크 지역과 연결해야 합니다. 네트워크 사이트를 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리를 참조하세요.](manage-your-network-topology.md)

라우팅에 대한 Location-Based 방법은 고유한 PSTN 연결이 있는 각 위치에 대해 별도의 사이트를 만드는 것입니다. Location-Based 라우팅에 사용할 수 있는 사이트 또는 Location-Based 사용할 수 없는 사이트를 만들 수 있습니다. 예를 들어 Location-Based 라우팅을 사용하도록 설정되지 않은 사이트를 만들어 Location-Based 라우팅을 사용하도록 설정된 사용자가 해당 사이트로 로밍할 때 PSTN 통화를 걸 수 있도록 할 수 있습니다.

## <a name="define-network-subnets"></a>네트워크 서브넷 정의

각 서브넷은 특정 네트워크 사이트와 연결되어야 합니다. 여러 서브넷을 동일한 네트워크 사이트와 연결하지만 여러 사이트를 동일한 서브넷에 연결하지는 못합니다. 네트워크 서브넷을 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리로 이동하세요.](manage-your-network-topology.md)

Location-Based 라우팅의 경우 Teams 엔드포인트가 네트워크에 연결할 수 있는 위치에 있는 IP 서브넷을 정의하고 정의된 네트워크에 연결하여 전화 우회를 적용해야 합니다. 이렇게 서브넷을 연결하면 라우팅이 Location-Based 엔드포인트를 지리적으로 찾아서 특정 PSTN 호출을 허용해야 하는지 여부를 결정할 수 있습니다. IPv6 및 IPv4 서브넷이 모두 지원됩니다. Teams 엔드포인트가 사이트에 있는지 여부를 결정할 때 Location-Based 일치하는 IPv6 주소를 먼저 확인할 수 있습니다. IPv6 주소가 없는 경우 Location-Based 라우팅에서 IPv4 주소를 검사합니다.

## <a name="define-trusted-ip-addresses-external-subnets"></a>신뢰할 수 있는 IP 주소(외부 서브넷) 정의

신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소로, 사용자의 엔드포인트가 회사 네트워크 내부에 있는지 확인하는 데 사용됩니다. 신뢰할 수 있는 IP 주소를 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리로 이동하세요.](manage-your-network-topology.md)

사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 Location-Based 라우팅을 확인하여 사용자의 엔드포인트가 있는 내부 서브넷을 확인할 수 있습니다. 사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 정의된 IP 주소와 일치하지 않는 경우 엔드포인트는 알 수 없는 위치에 있는 것으로 분류되고 Location-Based 라우팅을 사용하도록 설정된 사용자의 PSTN 호출은 차단됩니다.

## <a name="next-steps"></a>다음 단계

직접 [라우팅에 Location-Based](location-based-routing-enable.md)라우팅 사용으로 이동

## <a name="related-topics"></a>관련 항목

- [Teams의 클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)
