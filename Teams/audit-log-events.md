---
title: Microsoft 팀에서 이벤트 감사 로그 검색
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Office 365 감사 로그에서 Microsoft 팀 데이터를 검색 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341626"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Microsoft 팀에서 이벤트 감사 로그 검색

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

감사 로그는 Office 365 서비스에서 특정 작업을 조사 하는 데 도움이 될 수 있습니다. 팀의 경우 감사 되는 작업은 다음과 같습니다.

- 팀 만들기

- 팀 삭제

- 채널 추가 됨

- 설정 변경 됨

> [!NOTE]
> 개인 채널의 감사 이벤트도 팀 및 표준 채널의 경우에도 기록 됩니다.

Office 365에서 감사 되는 활동의 전체 목록을 보려면 [office 365 보안 & 준수 센터에서 감사 로그 검색](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)을 읽어보십시오.

## <a name="turn-on-auditing-in-teams"></a>팀에서 감사 설정

감사 데이터를 보려면 먼저 [보안 & 준수 센터](https://protection.office.com)에서 감사를 설정 해야 합니다. 감사를 설정 하려면 [Office 365 감사 로그 검색 설정 또는 해제](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)를 참조 하세요.

> [!IMPORTANT]
> 감사 데이터는 감사를 설정한 지점 에서만 사용할 수 있습니다.

## <a name="retrieve-teams-data-from-the-audit-log"></a>감사 로그에서 팀 데이터 검색

1. 감사 로그를 검색 하려면 [보안 & 준수 센터로](https://go.microsoft.com/fwlink/?linkid=855775)이동 합니다. **검색**에서 **감사 로그 검색**을 선택 합니다.
1. **검색** 을 사용 하 여 감사 하려는 활동, 날짜 및 사용자를 기준으로 필터링 합니다.
1. 추가 분석을 위해 결과를 Excel로 내보냅니다.

> [!IMPORTANT]
> 감사 데이터는 감사가 설정 된 경우 감사 로그에만 표시 됩니다.

## <a name="external-user-scenario"></a>외부 사용자 시나리오

비즈니스 측면에서 눈을 지속적으로 유지할 수 있는 한 가지 시나리오는 외부 사용자를 팀 환경에 추가 하는 것입니다. 외부 사용자가 사용 하도록 설정 된 경우에는 현재 상태 모니터링이 좋습니다.

![대량 삭제에 의해 트리거되는 이벤트 목록의 스크린샷](media/TeamsExternalUserAddPolicy.png)

이 정책을 통해 외부 사용자 추가를 모니터링 하 고, 비즈니스 요구에 따라 심각도를 설정 하 고, (이 경우에는) 단일 활동으로 설정한 다음, 구체적 으로만 모니터링 하는 매개 변수를 설정 하는 것을 허용 합니다. 비 내부 사용자의 경우이 활동을 Microsoft 팀으로 제한 합니다.

그런 다음 활동 로그에서이 정책의 결과를 볼 수 있습니다.

![대량 삭제에 의해 트리거되는 이벤트 목록의 스크린샷](media/TeamsExternalUserList.png)

여기서 설정한 정책과 일치 하는 항목을 검토 하 고 필요에 따라 조정을 수행 하거나 결과를 내보내 다른 곳에서 사용할 수 있습니다.

## <a name="mass-delete-scenario"></a>대량 삭제 시나리오

위에서 설명한 대로 삭제 시나리오를 모니터링할 수 있습니다. 팀 사이트의 대량 삭제를 모니터링 하는 정책을 만들 수 있습니다.

![대량 팀 삭제 검색에 대 한 정책의 설정을 보여 주는 정책 만들기 페이지 스크린샷](media/TeamsMassDeletePolicy.png)

화면에 표시 되는 것 처럼이 정책에 대해 다양 한 매개 변수를 설정 하 여 심각도, 단일 또는 반복 작업을 비롯 한 팀 삭제를 모니터링할 수 있으며,이를 팀 및 사이트 삭제로 제한 하는 매개 변수 이 작업은 서식 파일과 관계 없이 수행할 수 있으며 조직의 요구 사항에 따라이 정책을 기반으로 만든 서식 파일이 있을 수 있습니다.

비즈니스에 사용할 정책을 설정한 후에는 이벤트가 트리거될 때 활동 로그에서 결과를 검토 하면 됩니다.

![대량 삭제에 의해 트리거되는 이벤트 목록의 스크린샷](media/TeamsMassDeleteList.png)

설정한 정책에 맞게 필터링 하 여 해당 정책의 결과를 볼 수 있습니다. 활동 로그에서 발생 하는 결과가 만족 스 럽 지 않은 경우 (결과가 많은 경우 또는 아무것도 표시 되지 않는 경우)에는 필요한 사항에 맞게 쿼리를 세부적으로 조정 하는 데 도움이 될 수 있습니다.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>비디오: TechTip: 팀에서 감사 로그 검색 사용

Office 365 보안 & 준수 센터에서 팀에 대 한 감사 로그 검색을 수행 하는 방법을 보여 주는 팀을 위한 프로그램 관리자 인 a Ansuman에 참가 합니다.

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
