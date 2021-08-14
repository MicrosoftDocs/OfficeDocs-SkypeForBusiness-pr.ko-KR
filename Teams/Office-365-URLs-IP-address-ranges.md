---
title: Microsoft 365 및 Office 365 URL 및 IP 주소 범위
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: URL 및 IP 주소 범위를 Microsoft 365 또는 Office 365 올바르게 구성하고 서비스와의 연결에 대해 가능한 경우 전달 프록시를 Microsoft Teams 방법을 알아보십시오.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d0a1270d621c61fc224bbc799f1007ef9818542
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233883"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 및 Office 365 URL 및 IP 주소 범위

[URL Microsoft 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Office 365 올바르게 구성해야 하는 URL, IP 주소, 포트 및 프로토콜에 대한 자세한 최신 목록을 확인하려면 URL 및 IP 주소 범위로 Teams. Microsoft는 계속해서 Microsoft 365 및 Office 365 서비스를 개선하고 새 기능을 추가하고 있으며 이는 필수 포트, URL, IP 주소가 시간이 지나면서 변경됨을 의미합니다. 이 정보가 업데이트되거나 변경될 때 알림을 받기 위해 [RSS를](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 통해 구독하는 것이 좋습니다.

Teams 호출 및 모임 환경은 차세대 클라우드 기반 인프라를 기반으로 Skype 비즈니스용 Skype. 이러한 기술 투자에는 미디어 처리 및 신호 처리를 위한 Azure 기반 클라우드 서비스, H.264 비디오 코덱, SILK 및 Opus 오디오 코덱, 네트워크 탄력성, 원격 분석 및 품질 진단이 포함됩니다. 따라서 URL 및 IPS가 Skype 및 비즈니스용 SKYPE.

모든 Microsoft 365 및 Office 365 경우 서비스를 Teams 권장되는 연결 방법은 가능한 경우 전달 프록시를 무시합니다. 프록시 서버가 클라이언트와 데이터 Office 365 사이에 있는 경우 미디어가 UDP 대신 TCP를 강제로 하여 미디어 품질에 영향을 줄 수 있습니다. 데이터 관리 및 엔드포인트 관리에서 트래픽 우회를 구성하는 데 사용할 수 있는 샘플 프록시 PAC [Microsoft 365 Office 365 다운로드합니다.](/office365/enterprise/managing-office-365-endpoints)

네트워킹 및 보안 정책에서 프록시 서버를 통해 Microsoft 365 Office 365 트래픽이 필요하면 프로덕션에 배포하기 전에 위의 요구 사항이 Teams 있는지 확인합니다. 자세한 내용은 온라인 또는 Teams 프록시 비즈니스용 Skype [를 참조하십시오.](proxy-servers-for-skype-for-business-online.md)