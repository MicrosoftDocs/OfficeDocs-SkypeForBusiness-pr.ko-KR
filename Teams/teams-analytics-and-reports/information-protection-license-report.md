---
title: Microsoft Teams 보호 라이선스 보고서
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: 관리 센터의 Teams 정보 보호 라이선스 보고서를 Microsoft Teams 조직의 앱이 변경 알림 이벤트 구독 API를 사용하는 방법을 알아보는 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435862"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams 보호 라이선스 보고서


Teams 정보 보호 라이선스 보고서는 라이선스 및 결제 요구 사항이 Graph Api에 대한 API 사용 [현황을 제공합니다](/graph/teams-licenses). 이 보고서는 model=A에서 이러한 API를 사용하는 모든 [앱을 강조 표시합니다](/graph/teams-licenses#modela-requirements). MODEL= [B](/graph/teams-licenses#modelb-requirements) 또는 평가 모드에서 API를 사용하는 경우 사용량이 [표시되지 않습니다](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>정보 보호 라이선스 보고서 보기

이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](../using-admin-roles.md)을 참조하세요.

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **보고서 & 선택합니다** > . 보고서 **보기 탭** 의 **보고서에서** **정보 보호 라이선스를 선택합니다**.
2. 날짜 **범위에서** 범위를 선택합니다.
3. **앱에서** 앱을 선택한 다음 보고서 실행 **을 선택합니다**.

    ![콜아웃이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 드롭다운 스크린샷.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "콜아웃이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 드롭다운 스크린샷.")

4. 각 범주에 대해 라이선스가 있는 사용자, 라이선스가 없는 사용자, 시드 용량 및 사용 용량에 대한 메트릭을 볼 수 있습니다. 

    ![콜아웃을 사용하여 변경 알림의 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 요약 차트 스크린샷.](../media/teams-info-protection-license-report-chart-with-callouts.png "콜아웃을 사용하여 변경 알림의 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 요약 차트 스크린샷.")

5. 내보내기 단추를 클릭하여 데이터를 내보낼 수 있습니다. 테이블 데이터는 변경 알림 API, Teams 패치 API, Teams API(채팅) 및 내보내기 API(팀)Teams 탭을 클릭하여 전환할 Teams 수 있습니다. 

    ![설명선이 있는 탭의 Teams 관리 센터에 있는 Teams 다른 탭의 스크린샷입니다.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "설명선이 있는 탭의 Teams 관리 센터에 있는 Teams 다른 탭의 스크린샷입니다.")

    ![콜아웃이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 변경 알림 탭 스크린샷.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "콜아웃이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 변경 알림 탭 스크린샷.")


## <a name="interpret-the-report"></a>보고서 해석

|콜아웃 |설명  |
|--------|-------------|
|**1**   |정보 보호 라이선스 보고서는 지난 3개월 동안의 추세를 볼 수 있습니다. |
|**2**   |앱 이름은 선택한 기간 동안 라이선스 및 결제 요구 사항이 Graph [Microsoft Graph API](/graph/teams-licenses)를 사용한 모든 앱 목록을 표시합니다.|
|**3**   |유효한 라이선스가 있는 [사용자 수입니다](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |유효한 라이선스가 없는 사용자 [수입니다](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |API 호출당 소비 요금이 앱에 청구되는 앱에 허용되는 총 API 호출 볼륨입니다. |
|**6**   |앱에서 주어진 날짜 범위에 사용되는 총 API 호출 볼륨입니다. |
|**7**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내 **기를 Excel** 다음 다운로드 탭을 선택합니다 **. 다운로드를** 선택하여 준비가되면 보고서를 다운로드합니다. 이 내보내기에서는 현재 선택한 탭만 내보낼 수 있습니다.|
|**8**   |차트에 표시하거나 숨길 특정 레이블을 선택합니다. |
|**9**   |각 탭에는 특정 API 집합의 사용량, 즉 변경 [알림,](/graph/api/resources/webhooks) [내보내기 API](/microsoftteams/export-teams-content) 및 업데이트 [메시지 API가 표시됩니다](/graph/api/message-update). 탭을 선택하여 해당 API의 사용 현황 정보를 볼 수 있습니다. |
|**10**   |**알림 API 사용량 변경**<li>**표시 이름** - 변경 알림이 트리거된 사용자의 이름을 표시합니다.</li><li>**필수 라이선스** - 주어진 사용자가 앱에 변경 알림을 성공적으로 전송하는 데 필요한 라이선스가 있는지 여부입니다.</li><li>**시도된 개수** - 이 사용자로 인하여 트리거된 변경 알림의 총 수입니다.</li><li>**알림 전송 변경** - 앱에 전송된 총 변경 알림 수입니다. 사용자에게 유효한 라이선스가 없는 경우 트리거된 총 변경 알림보다 작습니다.</li>|
|**11**|**패치 API**<li>**표시 이름** - 메시지를 업데이트하려는 시도가 완료된 사용자의 이름을 표시합니다.</li> <li>**필수 라이선스** - 메시지가 성공적으로 업데이트되는 데 필요한 라이선스가 있는지 여부입니다.</li><li>**시도된 개수** - 메시지를 업데이트하려는 총 시도입니다.</li><li>**메시지 패치** - 성공적으로 업데이트된 총 메시지입니다.</li>|
|**12**|**채팅 내보내기 API 사용량**<li>**표시 이름** - 사용자의 채팅 메시지를 내보내기 시도가 완료된 사용자의 이름 표시입니다.</li><li>**필수 라이선스** - 주어진 사용자가 성공적으로 내보낼 메시지에 필요한 라이선스가 있는지 여부입니다.</li><li>**시도된 개수** - 채팅 메시지를 내보내는 총 시도입니다.</li><li>**메시지 내보내기** - 채팅 메시지가 성공적으로 내보낼 수 있는 총 시도입니다.</li> |
|**13**|**팀 내보내기 API 사용량**<li>**표시 이름** - 해당 팀의 메시지를 내보낼 시도가 완료된 팀의 이름을 표시합니다.</li><li>**시도된 개수** - 팀 메시지를 내보내는 총 시도입니다.</li><li>**내보낼 메시지** - 팀 메시지를 성공적으로 내보낼 수 있는 총 시도입니다.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>사용자별 데이터를 익명으로 지정합니다.

사용자 활동 보고서의 데이터를 익명으로 Teams 경우 전역 관리자로 설정해야 합니다. 그러면 보고서 및 내보내기에서 표시 이름, 전자 메일 및 Azure AD ID와 같은 식별 가능한 정보가 숨겨지게 됩니다.

1. 이 Microsoft 365 관리 센터 또는  \> 설정 설정 서비스 탭에서 보고서를 **선택합니다**.
    
2. 보고서를 **선택한** 다음 익명 식별자 **표시를 선택합니다**. 이 설정은 Microsoft 365 관리 센터 관리 센터의 Teams 적용됩니다.
  
3. 변경 **내용 저장을 선택합니다**.