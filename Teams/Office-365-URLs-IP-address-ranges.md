---
title: Office 365 URL 및 IP 주소 범위
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Office 365 Url 및 IP 주소 범위를 적절히 구성 하 고, Microsoft 팀 서비스와의 연결을 사용할 수 있는 경우 전달 프록시를 우회 하 고, 네트워킹 및 보안 정책에 대 한 요구 사항을 확인 하는 방법을 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1258138ce6f57dfb0284e030f7a813acf8b94a62
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862798"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 및 IP 주소 범위
=====================================

팀에 맞게 올바르게 구성 해야 하는 Url, IP 주소, 포트 및 프로토콜에 대 한 자세한 정보 및 최신 목록의 [Office 365 url 및 ip 주소 범위로](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 이동 합니다. Microsoft는 계속해서 Office 365 서비스를 개선 하고 새 기능을 추가하고 있으며 이는 필수 포트, URL, IP 주소가 시간이 지나면서 변경됨을 의미합니다. 이 정보를 업데이트 하거나 변경할 때 알림을 받으려면 [RSS를 통해 구독](https://go.microsoft.com/fwlink/p/?linkid=236301) 하는 것이 좋습니다.

팀 통화 및 모임 환경은 Skype 및 비즈니스용 Skype에서 함께 사용 되는 차세대 클라우드 기반 인프라에 기반을 둔 것입니다. 이러한 기술 투자에는 미디어 처리 및 신호, SILK 및 Opus audio 코덱, 네트워크 탄력성, 원격 분석, 품질 진단 등을 위한 Azure 기반 클라우드 서비스가 포함 됩니다. 따라서 Skype와 비즈니스용 Skype 모두에 연결 될 수 있는 Url과 Ip가 필요 합니다.

모든 Office 365 작업에 대해 권장 되는 팀 서비스 연결 방법은 가능한 경우 전달 프록시를 우회 하는 것입니다. 프록시 서버가 클라이언트와 Office 365 데이터 센터 사이에 있으면 UDP 대신 TCP를 통해 미디어를 강제로 사용할 수 있으므로 미디어 품질에 영향을 줄 수 있습니다. [Office 365 끝점 관리](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)에서 트래픽 바이패스를 구성 하는 데 사용할 수 있는 샘플 프록시 PAC 파일을 다운로드 합니다.

네트워킹 및 보안 정책에 프록시 서버를 통해 전송 하는 데 Office 365 트래픽이 필요한 경우 팀을 프로덕션에 배포 하기 전에 위의 요구 사항이 이미 충족 되었는지 확인 합니다. 자세한 내용은 [팀에 대 한 프록시 서버 또는 비즈니스용 Skype Online](proxy-servers-for-skype-for-business-online.md)을 참조 하세요.
