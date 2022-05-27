---
title: Microsoft Teams 정보 보호 라이선스 보고서
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
description: Microsoft Teams 관리 센터에서 Teams Information Protection 라이선스 보고서를 사용하여 조직의 앱이 변경 알림 이벤트 구독 API를 사용하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681539"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams 정보 보호 라이선스 보고서


Teams 정보 보호 라이선스 보고서는 [라이선스 및 지불 요구 사항이 있는 Microsoft Graph API](/graph/teams-licenses)에 대한 API 사용 정보를 제공합니다. 이 보고서는 [model=A](/graph/teams-licenses#modela-requirements)에서 이러한 API를 사용하는 모든 앱을 강조 표시합니다. [모델=B](/graph/teams-licenses#modelb-requirements) 또는 [평가 모드](/graph/teams-licenses#evaluation-mode-default-requirements)에서 API를 사용하는 경우 사용량이 표시되지 않습니다. 


## <a name="view-the-information-protection-license-report"></a>정보 보호 라이선스 보고서 보기

이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](../using-admin-roles.md)을 참조하세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서****사용 현황 보고서를** >  선택합니다. **보고서 보기** 탭의 **보고서** 아래에서 **Information Protection 라이선스를** 선택합니다.
2. **날짜 범위에서 범위를** 선택합니다.
3. **앱** 에서 앱을 선택한 다음 **보고서 실행을** 선택합니다.

    ![설명선이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서 드롭다운 스크린샷](../media/teams-info-protection-license-report-dropdown-with-callouts.png "설명선이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서 드롭다운 스크린샷")

4. 각 범주에 대해 라이선스가 있는 사용자, 라이선스가 없는 사용자, 시드된 용량 및 사용 용량에 대한 메트릭을 볼 수 있습니다. 

    ![설명선이 있는 변경 알림의 Teams 관리 센터에 있는 Teams 정보 보호 라이선스 보고서의 요약 차트 스크린샷](../media/teams-info-protection-license-report-chart-with-callouts.png "설명선이 있는 변경 알림의 Teams 관리 센터에 있는 Teams 정보 보호 라이선스 보고서의 요약 차트 스크린샷")

5. 내보내기 단추를 클릭하여 데이터를 내보낼 수 있습니다. Teams 변경 알림 API, Teams 패치 API, Teams API 내보내기(채팅) 및 API(팀) 내보내기 Teams 탭을 클릭하여 테이블 데이터를 전환할 수 있습니다. 

    ![설명선이 있는 탭의 Teams 관리 센터에 있는 Teams 정보 보호 라이선스 보고서의 여러 탭 스크린샷](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "설명선이 있는 탭의 Teams 관리 센터에 있는 Teams 정보 보호 라이선스 보고서의 여러 탭 스크린샷")

    ![설명선이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 변경 알림 탭 스크린샷](../media/teams-info-protection-license-report-change-notification-with-callouts.png "설명선이 있는 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서의 변경 알림 탭 스크린샷")


## <a name="interpret-the-report"></a>보고서 해석

|설명선 |설명  |
|--------|-------------|
|**1**   |지난 3개월 동안의 추세에 대한 정보 보호 라이선스 보고서를 볼 수 있습니다. |
|**2**   |앱 이름에는 선택한 기간 동안 [라이선스 및 결제 요구 사항이 있는 Microsoft Graph API](/graph/teams-licenses) 사용한 모든 앱 목록이 표시됩니다.|
|**3**   |유효한 라이선스가 있는 사용자 [수입니다](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |유효한 [라이선스](/graph/teams-licenses#required-licenses-for-modela)가 없는 사용자 수입니다.  |
|**5**   |앱에 허용되는 총 API 호출 볼륨으로, API 호출당 소비 요금이 앱에 청구됩니다. |
|**6**   |지정된 날짜 범위에 대해 앱에서 사용하는 총 API 호출 볼륨입니다. |
|**7**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보냅니다. **내보내기를 선택하여 Excel** 다음 **다운로드 탭을** 선택합니다. **준비가 되면 다운로드** 를 선택하여 보고서를 다운로드합니다. 이 내보내기에서는 현재 선택한 탭만 내보냅니다.|
|**8**   |차트에 표시하거나 숨길 특정 레이블을 선택합니다. |
|**9**   |각 탭에는 알림 [변경](/graph/api/resources/webhooks), [API 내보내기](/microsoftteams/export-teams-content) 및 [업데이트 메시지 API](/graph/api/message-update)와 같은 특정 API 집합의 사용량이 표시됩니다. 탭을 선택하여 해당 API의 사용량 세부 정보를 봅니다. |
|**10**   |**알림 API 사용량 변경**<li>**표시 이름** - 변경 알림이 트리거된 사용자의 표시 이름입니다.</li><li>**필수 라이선스** - 지정된 사용자에게 앱에 변경 알림을 성공적으로 보내는 데 필요한 라이선스가 있는지 여부입니다.</li><li>**시도된 수** - 이 사용자로 인해 트리거된 총 변경 알림 수입니다.</li><li>**변경 알림 전송** - 앱에 전송된 총 변경 알림 수입니다. 이는 사용자에게 유효한 라이선스가 없는 경우 트리거되는 총 변경 알림보다 작습니다.</li>|
|**11**|**패치 API**<li>**표시 이름** - 메시지를 업데이트하려고 시도한 사용자의 표시 이름입니다.</li> <li>**필수 라이선스** - 지정된 사용자에게 메시지가 성공적으로 업데이트되는 데 필요한 라이선스가 있는지 여부입니다.</li><li>**시도 횟수** - 메시지를 업데이트하려는 총 시도 수입니다.</li><li>**메시지 패치** - 업데이트된 총 메시지 수입니다.</li>|
|**12**|**채팅 내보내기 API 사용**<li>**표시 이름** - 사용자의 채팅 메시지를 내보내려는 시도가 완료된 사용자의 표시 이름입니다.</li><li>**필수 라이선스** - 지정된 사용자에게 메시지를 성공적으로 내보내는 데 필요한 라이선스가 있는지 여부입니다.</li><li>**시도 횟수** - 채팅 메시지를 내보내려는 총 시도 수입니다.</li><li>**메시지 내보내기** - 채팅 메시지를 성공적으로 내보낸 총 시도 수입니다.</li> |
|**13**|**팀 내보내기 API 사용량**<li>**표시 이름** - 해당 팀의 메시지를 내보내려는 시도가 완료된 팀의 표시 이름입니다.</li><li>**시도 횟수** - 팀 메시지를 내보내려는 총 시도 수입니다.</li><li>**메시지 내보내기** - 팀 메시지를 성공적으로 내보낸 총 시도 수입니다.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>사용자별 데이터를 익명으로 만들기

Teams 사용자 활동 보고서의 데이터를 익명으로 만들려면 전역 관리자여야 합니다. 이렇게 하면 보고서 및 내보내기에서 표시 이름, 전자 메일 및 Azure AD ID와 같은 식별 가능한 정보가 숨겨질 수 있습니다.

1. Microsoft 365 관리 센터 **설정** \> **조직 설정** 이동하고 **서비스** 탭에서 **보고서를** 선택합니다.
    
2. **보고서를** 선택한 다음 **익명 식별자를 표시** 하도록 선택합니다. 이 설정은 Microsoft 365 관리 센터 사용 현황 보고서와 Teams 관리 센터에 모두 적용됩니다.
  
3. **변경 내용 저장** 을 선택합니다.