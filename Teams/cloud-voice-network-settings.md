---
title: 클라우드 음성 기능에 대한 네트워크 설정
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 직접 라우팅 및 향상된 응급 서비스에 대한 Location-Based 라우팅에 대해 구성해야 하는 네트워크 설정에 대해 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 327dbcef98e62d86f814f8e1fadc1c26673d0928
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584009"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft Teams의 클라우드 음성 기능에 대한 네트워크 설정

네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대해 알아봅니다. 이러한 용어와 개념은 직접 라우팅 및 [동적 긴급 통화](configure-dynamic-emergency-calling.md)에 대한 [위치 기반 라우팅에 대한](location-based-routing-plan.md) 클라우드 음성 설명서 전체에서 사용됩니다. 조직에서 이러한 클라우드 기능을 배포하는 경우 Microsoft Teams에서 이러한 기능에 사용할 네트워크 설정을 구성해야 합니다.

이 문서에서는 Location-Based 라우팅 및 동적 긴급 통화에 공통적인 네트워크 설정에 대한 개요를 제공합니다. 배포하는 클라우드 음성 기능 및 기능에 따라 이러한 설정의 일부 또는 전부를 구성합니다. 이러한 설정을 구성하는 방법에 대한 단계는 [Teams에서 클라우드 기능에 대한 네트워크 토폴로지 관리를 참조하세요](manage-your-network-topology.md).

> [!NOTE]
> 네트워크 설정에 대한 기능별 요구 사항은 해당 기능에 대한 구성 항목에 설명되어 있습니다.

## <a name="network-region"></a>네트워크 지역

네트워크 지역에는 네트워크 사이트 컬렉션이 포함되어 있습니다. 여러 지리적 영역에 걸쳐 네트워크의 다양한 부분을 상호 연결합니다. 예를 들어 조직에 인도에 많은 사이트가 있는 경우 "인도"를 네트워크 지역으로 지정하도록 선택할 수 있습니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.

동일한 네트워크 지역은 직접 라우팅 및 향상된 응급 서비스에 대한 Location-Based 라우팅에서 공유됩니다. 한 기능에 대한 네트워크 지역을 이미 만든 경우 다른 기능에 대한 새 네트워크 지역을 만들 필요가 없습니다.

## <a name="network-site"></a>네트워크 사이트

네트워크 사이트는 조직에 사무실, 건물 세트 또는 캠퍼스와 같은 물리적 장소가 있는 위치를 나타냅니다. 네트워크 사이트는 IP 서브넷의 컬렉션으로 정의됩니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.

네트워크 사이트를 사용하여 긴급 통화를 사용하도록 설정하고 구성할 수도 있습니다.

## <a name="network-subnet"></a>네트워크 서브넷

각 서브넷은 특정 네트워크 사이트와 연결되어야 합니다. 클라이언트의 위치는 네트워크 서브넷 및 연결된 네트워크 사이트에 따라 결정됩니다. 여러 서브넷을 동일한 네트워크 사이트에 연결할 수 있지만 여러 사이트를 동일한 서브넷에 연결할 수는 없습니다.

서브넷 정보는 새 세션이 시작될 때 엔드포인트가 있는 네트워크 사이트를 결정하는 데 사용됩니다. 세션에서 각 당사자의 위치를 알 수 있는 경우 클라우드 음성 기능은 해당 정보를 적용하여 통화 설정 또는 라우팅을 처리하는 방법을 결정할 수 있습니다.

각 네트워크 사이트에 대해 네트워크 관리자와 협력하여 각 네트워크 사이트에 할당된 IP 서브넷을 확인합니다. 예를 들어 북아메리카 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24 IP 서브넷이 할당될 수 있습니다. 일반적으로 디트로이트에서 일하는 Bob이 교육을 위해 뉴욕 사무실로 이동하고 컴퓨터를 켜고 네트워크에 연결하면 컴퓨터에 뉴욕에 할당된 4가지 범위 중 하나인 172.29.80.103과 같은 IP 주소가 제공됩니다.

## <a name="trusted-ip-address"></a>신뢰할 수 있는 IP 주소

신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소입니다. 특정 사이트 일치를 확인하기 전에 사용자의 엔드포인트가 회사 네트워크 내에 있는지 여부를 확인합니다.

사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치하는 경우 클라우드 음성 기능은 사용자의 엔드포인트가 있는 내부 서브넷을 확인합니다. IPv4 또는 IPv6 IP 주소에 대해 일치시킬 수 있으며 네트워크 설정으로 전송되는 IP 패킷의 형식에 따라 달라집니다. (공용 IP 주소에 IPv4 및 IPv6가 모두 있는 경우 둘 다 신뢰할 수 있는 IP 주소로 추가해야 합니다.)

사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치하지 않는 경우 엔드포인트는 알 수 없는 위치에 있는 것으로 분류됩니다.

> [!Important]
> Teams 클라이언트에서 원본 IP 주소를 수정하는 클라우드 프록시 서비스 배포에서는 네트워크 구성 설정 조회가 지원되지 않습니다.
