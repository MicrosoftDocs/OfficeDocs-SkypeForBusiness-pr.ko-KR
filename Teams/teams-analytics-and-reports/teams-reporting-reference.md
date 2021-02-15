---
title: Microsoft Teams 분석 및 보고
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 이 문서에서는 Microsoft Teams 관리 센터에서 사용할 수 있는 Teams 보고서에 대해 배워보게 됩니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 684afe6e001ecb7b897a8574813eaed42108bb82
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196832"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 분석 및 보고

Microsoft Teams에 대한 새로운 분석 및 보고 환경은 Microsoft Teams 관리 센터에서 사용할 수 있습니다. 다양한 보고서를 실행하여 조직의 사용자가 Teams를 사용하는 방법에 대한 정보를 얻을 수 있습니다. 예를 들어 채널 및 채팅 메시지를 통해 통신하는 사용자 수와 Teams에 연결하는 데 사용하는 장치 종류를 볼 수 있습니다. 조직은 보고서의 정보를 사용하여 사용 패턴을 더 잘 이해하고, 비즈니스 의사 결정을 내리고, 교육 및 통신 노력을 알릴 수 있습니다.

## <a name="how-to-access-the-reports"></a>보고서에 액세스하는 방법

보고서에 액세스하려면 Microsoft 365 또는 Office 365, Teams 서비스 관리자 또는 비즈니스용 Skype 관리자의 전역 관리자일 수 있습니다. Teams 관리자 역할 및 각 관리자 역할이 액세스할 수 있는 보고서에 대한 자세한 내용은 Teams 관리자 역할을 사용하여 [Teams를 관리하세요.](../using-admin-roles.md)

Microsoft Teams 관리 센터로 이동하여 왼쪽 탐색 창에서 **Analytics**& 보고서를 선택한 다음 보고서 아래에서 실행하려는 보고서를 선택합니다.

> [!NOTE]
> Microsoft Teams 관리 센터의 보고서는 Microsoft 365 관리 센터의 Microsoft 365 보고서에 있는 Teams의 활동 보고서와 별개입니다. Microsoft 365 관리 센터의 활동 보고서에 대한 자세한 내용은 [Microsoft 365](../teams-activity-reports.md) 관리 센터의 Teams 활동 보고서를 참조하세요.

## <a name="teams-reporting-reference"></a>Teams 보고 참조

다음은 Microsoft Teams 관리 센터에서 사용할 수 있는 Teams 보고서 목록과 각 보고서에서 사용할 수 있는 일부 정보의 개요입니다.

Teams 보고 환경을 지속적으로 개선하고 기능 및 기능을 추가하고 있습니다. 시간이 지날 때 보고서에 추가 기능을 구축하고 Microsoft Teams 관리 센터에 새 보고서를 추가할 것입니다.

|보고서  |무엇을 측정하나요? |
|---------|---------|
|[Teams 사용 현황 보고서](teams-usage-report.md)  |  활성 사용자<br/>팀 및 채널의 활성 사용자<br/>활성 채널<br/>메시지<br/>팀의 개인 정보 설정<br/>팀의 게스트   |
|[Teams 사용자 작업 보고서](user-activity-report.md)  | 사용자가 팀 채팅에 게시한 메시지<br/>사용자가 비공개 채팅에 게시한 메시지<br/>  1:1 호출에 참여한 사용자<br/> 구성한 모임 사용자 수 <br/>참가한 모임 사용자 수<br/>모임 오디오, 비디오 및 화면 공유 시간<br/>   사용자의 마지막 활동 날짜     |
|[Teams 장치 사용 현황 보고서](device-usage-report.md)   |  Windows 사용자<br/>Mac 사용자<br/>iOS 사용자<br/>Android 휴대폰 사용자     |
|[Teams 라이브 이벤트 사용 현황 보고서](teams-live-event-usage-report.md)   |  총 보기<br>시작 시간<br>이벤트 상태<br>이끌이<br>발표자<br>생산자<br>녹음/녹화 설정<br>프로덕션 유형    |
|[Teams PSTN 차단된 사용자 보고서](pstn-blocked-users-report.md)   |  표시 이름<br>전화 번호<br>이유<br>작업 유형<br>작업 날짜 및 시간   |
|[Teams PSTN 분 풀 보고서](pstn-minute-pools-report.md) |  국가 또는 지역<br>기능(라이선스) <br>총 시간(분)<br>사용된 시간(분)<br>사용 가능한 시간(분)|
|[Teams PSTN 사용 현황 보고서 - 통화 계획](pstn-usage-report.md#calling-plans)|  타임스탬프<br>사용자 이름<br>전화 번호<br>통화 유형 <br>호출자<br>국가 또는 지역으로 <br>호출자 <br>국가 또는 지역에서<br>요금<br>통화<br>기간<br>국내/국제<br>통화 ID<br>숫자 형식<br>국가 또는 지역<br>회의 ID<br>기능(라이선스)|
|[Teams PSTN 사용 보고서 - 직접 라우팅](pstn-usage-report.md#direct-routing)  |  타임스탬프<br>표시 이름<br>SIP 주소<br>전화 번호 <br>통화 유형<br>호출자<br>시작 시간<br>초대 시간<br>실패 시간<br>종료 시간<br>기간<br>숫자 형식<br>미디어 바이패스<br>SBC FQDN<br>Azure 지역<br>이벤트 유형<br>최종 SIP 코드<br>최종 Microsoft 하위 코드<br>최종 SIP 구<br>상관 관계 ID  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]
