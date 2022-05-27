---
title: MICROSOFT 365 및 Office 365 URL 및 IP 주소 범위
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Microsoft 365 또는 Office 365 URL 및 IP 주소 범위를 올바르게 구성하고 Microsoft Teams 서비스와의 연결에 대해 가능하면 전달 프록시를 우회하는 방법을 알아봅니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: 1ebcf7c6595da3e1774571be4c65a796838115b3
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675720"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>MICROSOFT 365 및 Office 365 URL 및 IP 주소 범위

[url, IP 주소, 포트 및 Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 대해 올바르게 구성해야 하는 프로토콜의 상세하고 최신 목록을 보려면 Microsoft 365 및 Office 365 URL 및 IP 주소 범위로 이동합니다. Microsoft는 계속해서 Microsoft 365 및 Office 365 서비스를 개선하고 새 기능을 추가하고 있으며 이는 필수 포트, URL, IP 주소가 시간이 지나면서 변경됨을 의미합니다. 이 정보가 업데이트되거나 변경될 때 [RSS를 통해](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 알림을 수신하도록 구독하는 것이 좋습니다.

Teams 통화 및 모임 환경은 Skype 및 비즈니스용 Skype 사용하는 차세대 클라우드 기반 인프라를 기반으로 합니다. 이러한 기술 투자에는 미디어 처리 및 신호를 위한 Azure 기반 클라우드 서비스, H.264 비디오 코덱, SILK 및 Opus 오디오 코덱, 네트워크 복원력, 원격 분석 및 품질 진단이 포함됩니다. 따라서 Skype 및 비즈니스용 Skype 모두 연결할 수 있는 필수 URL 및 IP가 있습니다.

모든 Microsoft 365 및 Office 365 워크로드의 경우 Teams 서비스에 권장되는 연결 방법은 가능한 경우 정방향 프록시를 우회하는 것입니다. 프록시 서버가 클라이언트와 Office 365 데이터 센터 사이에 있는 경우 미디어 품질에 영향을 미치는 UDP 대신 TCP를 통해 미디어를 강제 적용할 수 있습니다. [Microsoft 365 및 Office 365 엔드포인트 관리](/office365/enterprise/managing-office-365-endpoints)에서 트래픽 바이패스를 구성하는 데 사용할 수 있는 샘플 프록시 PAC 파일을 다운로드합니다.

네트워킹 및 보안 정책에서 프록시 서버를 통해 흐르는 Microsoft 365 또는 Office 365 트래픽이 필요한 경우 프로덕션에 Teams 배포하기 전에 위의 요구 사항이 이미 충족되었는지 확인합니다. 자세한 내용은 [Teams 또는 비즈니스용 Skype Online용 프록시 서버를 참조하세요](proxy-servers-for-skype-for-business-online.md).