---
title: Teams 클라이언트의 연결 문제 해결
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 주로 방화벽 또는 프록시 연결에서 발생하는 Microsoft Teams 클라이언트의 연결 문제 해결 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8974aa7cf54ab61cb15650b839185daad1b82cc7
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562167"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Microsoft Teams 클라이언트의 연결 문제 해결

Microsoft Teams 클라이언트에서 발견되는 대부분의 문제는 방화벽 또는 프록시 연결 문제로 추적됩니다. 방화벽 또는 프록시에서 필수 URL, IP 주소 및 포트가 열려 있는지 확인하면 불필요한 문제 해결을 최소화할 수 있습니다. Microsoft Teams에 필요한 URL 및 IP에 대한 자세한 내용은 [Microsoft 365 및 Office 365 URL 및 IP 주소](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 지원 문서를 참조하세요. 다음 시나리오는 방화벽에서 특정 URL 및 포트가 열려 있어야 합니다.

- 인증

- Microsoft Teams 클라이언트 연결

- 공동 작업

- 미디어

- 공유 서비스

- 타사 통합

- 비즈니스용 Skype 상호 운용성

- 비즈니스용 Skype 클라이언트 상호 운용성

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Teams가 오프라인 상태이거나 대역폭이 낮은 경우

좋은 소식은 오프라인 상태이거나 낮은 대역폭 조건에서 실행되는 경우에도 Teams가 계속 실행된다는 것입니다. Teams는 기존 채팅에 대해 보내지 않은 모든 메시지를 저장하고(최대 24시간 동안) 다시 온라인 상태가 되는 즉시 메시지를 보냅니다. 24시간 이상 오프라인 상태인 경우 Teams에서 전송되지 않은 메시지를 다시 보내거나 삭제하도록 선택할 수 있습니다. 새 채팅에 이 기능을 추가하기 위해 노력하고 있으며, 사용 가능한 경우 이 설명서를 업데이트할 예정입니다.

## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)