---
title: 네트워크 설정 구성 - 위치 기반 라우팅
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅을 위한 Location-Based 라우팅을 위해 네트워크 지역, 사이트 및 서브넷을 만들고 설정하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9a7c02a7299029ec267011f962880884d1d9f4d7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999333"
---
# <a name="configure-network-settings-for-location-based-routing"></a>위치 기반 라우팅의 네트워크 설정 구성

이 문서에서는 Location-Based 라우팅에 대한 네트워크 설정을 구성하는 방법을 설명합니다. 아직 수행하지 않은 경우 [직접 라우팅에 대한 계획 Location-Based 라우팅](location-based-routing-plan.md) 을 읽고 네트워크 설정을 구성하기 전에 수행해야 하는 다른 단계를 검토합니다.

조직에서 직접 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정하는 것입니다.

## <a name="define-network-regions"></a>네트워크 지역 정의

네트워크 지역은 네트워크 사이트의 컬렉션을 포함하고 여러 지리적 영역에 걸쳐 네트워크의 다양한 부분을 상호 연결합니다. 네트워크 지역을 구성하는 방법에 대한 단계는 [Teams에서 클라우드 기능에 대한 네트워크 토폴로지 관리로 이동하세요](manage-your-network-topology.md).

## <a name="define-network-sites"></a>네트워크 사이트 정의

네트워크 사이트는 조직에 사무실, 건물 세트 또는 캠퍼스와 같은 물리적 장소가 있는 위치를 나타냅니다. 토폴로지의 각 네트워크 사이트를 네트워크 지역과 연결해야 합니다. 네트워크 사이트를 구성하는 방법에 대한 단계는 [Teams에서 클라우드 기능에 대한 네트워크 토폴로지 관리를 참조하세요](manage-your-network-topology.md).

Location-Based 라우팅의 모범 사례는 고유한 PSTN(공중 전화망) 연결이 있는 각 위치에 대해 별도의 사이트를 만드는 것입니다. Location-Based 라우팅에 사용하도록 설정된 사이트 또는 Location-Based 라우팅에 사용하도록 설정되지 않은 사이트를 만들 수 있습니다. 예를 들어 Location-Based 라우팅을 사용하도록 설정된 사용자가 해당 사이트로 로밍할 때 PSTN 호출을 수행할 수 있도록 Location-Based 라우팅에 사용할 수 없는 사이트를 만들 수 있습니다.

## <a name="define-network-subnets"></a>네트워크 서브넷 정의

각 서브넷은 특정 네트워크 사이트와 연결되어야 합니다. 여러 서브넷을 동일한 네트워크 사이트에 연결할 수 있지만 여러 사이트를 동일한 서브넷에 연결할 수는 없습니다. 네트워크 서브넷을 구성하는 방법에 대한 단계는  [Teams에서 클라우드 기능에 대한 네트워크 토폴로지 관리를 참조하세요](manage-your-network-topology.md).

Location-Based 라우팅의 경우 Teams 엔드포인트가 네트워크에 연결할 수 있는 위치의 IP 서브넷을 정의하고 정의된 네트워크에 연결하여 통행료 우회를 적용해야 합니다. 이 서브넷 연결을 사용하면 Location-Based 라우팅에서 지정된 PSTN 호출을 허용할지 여부를 결정하기 위해 지리적으로 엔드포인트를 찾을 수 있습니다. IPv6 및 IPv4 서브넷이 모두 지원됩니다. Teams 엔드포인트가 사이트에 있는지 여부를 결정할 때 Location-Based 라우팅은 먼저 일치하는 IPv6 주소를 확인합니다. IPv6 주소가 없는 경우 Location-Based 라우팅은 IPv4 주소를 확인합니다.

## <a name="define-trusted-ip-addresses-external-subnets"></a>신뢰할 수 있는 IP 주소 정의(외부 서브넷)

신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소이며 사용자의 엔드포인트가 회사 네트워크 내에 있는지 여부를 확인하는 데 사용됩니다. 신뢰할 수 있는 IP 주소를 구성하는 방법에 대한 단계는 [Teams에서 클라우드 기능에 대한 네트워크 토폴로지 관리를 참조하세요](manage-your-network-topology.md).

사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치하는 경우 라우팅을 Location-Based 사용자의 엔드포인트가 있는 내부 서브넷을 확인합니다. 사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 정의된 IP 주소와 일치하지 않는 경우 엔드포인트는 알 수 없는 위치에 있는 것으로 분류되고 Location-Based 라우팅을 사용하도록 설정된 사용자에 대한 PSTN 호출은 차단됩니다.

## <a name="next-steps"></a>다음 단계

[직접 라우팅에 Location-Based 라우팅 사용으로](location-based-routing-enable.md) 이동합니다.

## <a name="related-topics"></a>관련 주제

- [Teams의 클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)
