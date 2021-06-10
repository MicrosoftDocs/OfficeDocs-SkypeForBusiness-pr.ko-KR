---
title: 클라우드 음성 기능에 대한 네트워크 설정
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 직접 라우팅 및 향상된 응급 서비스에 대한 Location-Based 위해 구성해야 하는 네트워크 설정에 대해 자세히 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834338"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>클라우드 음성 기능에 대한 네트워크 Microsoft Teams

네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대해 자세히 알아보습니다. 이러한 용어 및 개념은 직접 라우팅 [](location-based-routing-plan.md) 및 동적 긴급 통화에 대한 위치 기반 라우팅에 대한 클라우드 음성 설명서 [전반에 사용됩니다.](configure-dynamic-emergency-calling.md) 조직에서 이러한 클라우드 기능을 배포하는 경우 이러한 기능과 함께 사용하도록 네트워크 설정을 구성해야 Microsoft Teams.

이 문서에서는 라우팅 및 동적 긴급 호출에 일반적으로 사용되는 Location-Based 개요를 제공합니다. 배포하는 클라우드 음성 기능 및 기능에 따라 이러한 설정을 일부 또는 모두 구성합니다. 이러한 설정을 구성하는 방법에 대한 단계는 의 클라우드 [기능에 대한 네트워크 토폴로지 관리를 Teams.](manage-your-network-topology.md)

> [!NOTE]
> 네트워크 설정에 대한 기능별 요구 사항은 해당 기능에 대한 구성 항목에 설명되어 있습니다.

## <a name="network-region"></a>네트워크 지역

네트워크 지역에는 네트워크 사이트 모음이 포함되어 있습니다. 여러 지리적 영역에 걸쳐 네트워크의 다양한 부분을 상호 연결합니다. 예를 들어 조직에 인도에 많은 사이트가 있는 경우 "인도"를 네트워크 지역으로 지정할 수 있습니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.

동일한 네트워크 지역은 직접 라우팅 및 향상된 응급 Location-Based 라우팅을 통해 공유됩니다. 한 기능에 대해 네트워크 지역을 이미 만든 경우 다른 기능에 대한 새 네트워크 지역을 만들지 않습니다.

## <a name="network-site"></a>네트워크 사이트

네트워크 사이트는 조직에 사무실, 건물 집합 또는 캠퍼스와 같은 물리적 장소가 있는 위치를 나타내고 있습니다. 네트워크 사이트는 IP 서브넷의 컬렉션으로 정의됩니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.

또한 네트워크 사이트를 사용하여 긴급 호출을 사용하도록 설정하고 구성할 수도 있습니다.

## <a name="network-subnet"></a>네트워크 서브넷

각 서브넷은 특정 네트워크 사이트와 연결되어야 합니다. 클라이언트의 위치는 네트워크 서브넷 및 연결된 네트워크 사이트에 따라 결정됩니다. 여러 서브넷을 동일한 네트워크 사이트와 연결할 수 있지만 여러 사이트를 동일한 서브넷과 연결할 수 없습니다.

서브넷 정보는 새 세션을 시작할 때 엔드포인트가 있는 네트워크 사이트를 결정하는 데 사용됩니다. 세션의 각 파티의 위치를 알 수 있는 경우 클라우드 음성 기능은 해당 정보를 적용하여 통화 설정 또는 라우팅을 처리하는 방법을 결정할 수 있습니다.

각 네트워크 사이트에 대해 네트워크 관리자와 함께 각 네트워크 사이트에 할당된 IP 서브넷을 확인합니다. 예를 들어 북미 지역의 뉴욕 사이트는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24를 할당할 수 있습니다. 일반적으로 디트로이트에서 일하는 Bob이 교육을 위해 뉴욕 사무실로 이동하여 컴퓨터를 켜고 네트워크에 연결하면 컴퓨터에는 뉴욕에 할당된 네 가지 범위(예: 172.29.80.103)에 IP 주소가 표시됩니다.

## <a name="trusted-ip-address"></a>신뢰할 수 있는 IP 주소

신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소입니다. 특정 사이트 일치를 확인하기 전에 사용자의 엔드포인트가 회사 네트워크 내부에 있는지 여부를 확인합니다.

사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치하는 경우 클라우드 음성 기능은 사용자의 엔드포인트가 있는 내부 서브넷을 확인합니다. IPv4 또는 IPv6 IP 주소에 대해 일치할 수 있으며 네트워크 설정으로 전송되는 IP 패킷의 형식에 따라 달라집니다. 공용 IP 주소에 IPv4 및 IPv6이 모두 있는 경우 둘 다 신뢰할 수 있는 IP 주소로 추가해야 합니다.

사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치하지 않는 경우 엔드포인트는 알 수 없는 위치에 있는 것으로 분류됩니다.
