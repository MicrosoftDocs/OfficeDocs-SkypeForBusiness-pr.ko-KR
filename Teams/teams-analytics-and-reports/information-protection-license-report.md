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
description: 관리 센터의 Teams 정보 보호 라이선스 보고서를 사용하여 조직의 앱이 변경 알림 Microsoft Teams 구독 API를 사용하는 방법을 알아보는 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1fc9dd7dc39c8803a87f71f9ef80e2a5609603a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625860"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams 보호 라이선스 보고서

Teams 정보 보호 라이선스 보고서는 테넌트 [](/graph/api/resources/subscription?view=graph-rest-1.0) 수준에서 메시지 [](/graph/api/resources/webhooks?view=graph-rest-1.0) 생성, 업데이트 또는 삭제된 메시지 수신을 수신하기 위해 알림 이벤트를 변경하기 위해 구독한 앱(즉, /teams/getAllMessagesage 또는 /chats/getAllMessages)에 대한 정보를 제공합니다. 메시지에 해당하는 변경 알림은 사용자에게 필요한 라이선스가 있는 경우만 성공적으로 [전송됩니다.](/graph/teams-licenses)  특정 사용자가 트리거한 변경 알림 수를 볼 수 있습니다.


## <a name="view-the-information-protection-license-report"></a>정보 보호 라이선스 보고서 보기

이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](../using-admin-roles.md)을 참조하세요.

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 보고서 **&**  >  **분석을 선택합니다.** 보고서 보기 **탭의** **보고서에서** 정보 보호 **라이선스를 선택합니다.**
2. 날짜 **범위에서** 범위를 선택합니다.
3. **앱에서** 앱을 선택한 다음 보고서 실행 **을 선택합니다.**

    ![콜아웃이 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서 스크린샷](../media/teams-info-protection-license-report-with-callouts.png "콜아웃이 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|콜아웃 |설명  |
|--------|-------------|
|**1**   |정보 보호 라이선스 보고서는 지난 7일, 30일 또는 90일 동안의 추세를 볼 수 있습니다. |
|**2**   |앱 이름은 날짜 범위에서 선택한 지난 n일 동안 메시지의 알림 이벤트를 변경하기 위해 구독한 모든 앱의 목록을 표시합니다. |
|**3**   |이 표에서는 선택한 앱에 대한 사용자당 사용량을 분석할 수 있습니다.<ul><li>**표시 이름은** 사용자의 표시 이름입니다. 관리자 센터의 사용자 세부 정보 페이지로 이동하려면 표시 Microsoft Teams 선택합니다.</li><li>**필수 라이선스가** 있는 경우 사용자가 정의한 필수 라이선스 중 하나(여기)[ https://docs.microsoft.com/en-us/graph/teams-licenses ]가 있습니다. 사용자에게 필요한 라이선스가 없는 경우  Microsoft 관리 센터에서 사용자의 라이선스 세부 정보 페이지로 이동하는 라이선스할당 링크가 표시됩니다(사용자 활성 >  >   사용자 이름 선택).</li><li>**라이선스 보호 이벤트는** 해당 사용자가 생성, 업데이트 또는 삭제한 메시지에 대해 앱에 전송된 고유 변경 알림 이벤트의 수입니다.</li></ul> |
|**4**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내기를 **Excel** 및 **다운로드 탭을** 선택합니다. **다운로드를** 선택하여 준비가되면 보고서를 다운로드합니다. |
|**5**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내기를 **Excel** 및 **다운로드 탭을** 선택합니다. **다운로드를** 선택하여 준비가되면 보고서를 다운로드합니다. 보고서에서 보고서를 Excel 사용자의 사용자 **ID** 및 전자 메일  주소를 나타내는 ID 및 전자 메일 열도 표시됩니다. |

## <a name="make-the-user-specific-data-anonymous"></a>사용자별 데이터를 익명으로 지정합니다.

사용자 활동 보고서의 Teams 익명으로 만들기 위해 전역 관리자로 설정해야 합니다. 그러면 보고서 및 내보내기에서 표시 이름, 전자 메일 및 Azure AD ID와 같은 식별 가능한 정보가 숨겨지게 됩니다.

1. Microsoft 365 관리 센터 또는 설정 또는 설정  탭에서 보고서를 \>  **선택합니다.** 
    
2. 보고서를 **선택한** 다음 익명 식별자 **표시를 선택합니다.** 이 설정은 Microsoft 365 관리 센터 관리 센터의 Microsoft 365 관리 센터 모두 Teams 적용됩니다.
  
3. 변경 **내용 저장 을 선택합니다.**
