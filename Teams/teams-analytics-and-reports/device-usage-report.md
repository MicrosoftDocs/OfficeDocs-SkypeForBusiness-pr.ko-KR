---
title: Microsoft Teams 디바이스 사용 현황 보고서
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 디바이스 사용 현황 보고서를 사용하여 조직의 사용자가 Teams에 연결하는 방법을 확인합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478358"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 디바이스 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 디바이스 사용 현황 보고서는 사용자가 Teams에 연결하는 방법에 대한 정보를 제공합니다. 보고서를 사용하여 이동 중 모바일 장치에서 Teams를 사용하는 수를 포함하여 조직 전체에서 사용되는 디바이스를 볼 수 있습니다.  

## <a name="view-the-device-usage-report"></a>디바이스 사용 보고서 보기

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 분석 & **보고서**  >  **를 클릭합니다.** 보고서 보기 **탭의** **보고서에서** **Teams 디바이스 사용 을 선택합니다.**
2. **날짜 범위에서** 범위를 선택한 다음 보고서 실행 **을 클릭합니다.**

    ![콜아웃이 있는 Teams 관리 센터의 Teams 디바이스 사용 보고서 스크린샷](../media/teams-reports-device-usage-with-callouts.png "콜아웃이 있는 Teams 관리 센터의 Teams 디바이스 사용 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|콜아웃 |설명  |
|--------|-------------|
|**1**   |Teams 디바이스 사용 현황 보고서는 지난 7일 또는 30일 동안의 추세를 볼 수 있습니다.  |
|**2**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24시간의 대기 시간을 반영합니다. |
|**3**   |<ul><li>차트의 X 축은 Teams에 연결하는 데 사용되는 다양한 **디바이스(Windows,** **Mac,** **Linux,** **iOS,** **Android Phone,** **Web)를** 나타냅니다. </li><li>Y축은 선택한 기간 동안 디바이스를 사용하는 사용자 수입니다.</li> </ul>디바이스를 나타내는 막대 위에 마우스를 대고 디바이스를 사용하여 Teams에 연결하는 사용자 수를 확인합니다.|
|**4**   |이 표에서는 사용자별 디바이스 사용량을 분석할 수 있습니다. <ul><li>**사용자** 이름은 사용자의 표시 이름입니다. 표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다. </li><li>**사용자가 Windows** 기반 컴퓨터에서 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Windows가 선택됩니다.</li><li>**사용자가** macOS 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Mac이 선택됩니다. </li> <li>**사용자가** Linux 컴퓨터에서 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Linux가 선택됩니다. </li> <li>**사용자가 iOS용** Teams 모바일 클라이언트에서 활성 상태인 경우 iOS가 선택됩니다.</li><li>**사용자가** Android용 Teams 모바일 클라이언트에서 활성 상태인 경우 Android 휴대폰이 선택됩니다. <li><li>**사용자가** Teams 웹 클라이언트에서 활성 상태인 경우 웹이 선택됩니다. <li>**마지막 활동은** 사용자가 Teams 활동에 참여한 마지막 날짜(UTC)입니다.</li> </ul> Azure AD에 사용자 계정이 더 이상 없는 경우 사용자 이름이 표에 "--"로 표시됩니다. <br><br>표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다. |
|**5**   |열 **편집을 선택하여** 표에 열을 추가하거나 제거합니다. |
|**6**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. Excel로 **내보내기를** 클릭한  다음 다운로드 탭에서 다운로드를 클릭하여 준비가되면 보고서를 다운로드합니다. <br><br>![내보낼 보고서를 보여주는 다운로드 탭 스크린샷](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>사용자 특정 데이터를 익명으로 지정

Teams 디바이스 사용 보고서의 데이터를 익명으로 만들하려면 전역 관리자로 설정해야 합니다. 그러면 보고서 및 내보내기에서 표시 이름, 전자 메일 및 AAD ID와 같은 식별 가능한 정보가 숨겨지게 됩니다.

1. Microsoft 365 관리 센터에서  설정 구성 설정으로 이동하고 서비스 탭에서 \> 보고서를 **선택합니다.** 
    
2. 보고서를 **선택한** 다음 익명 식별자 **표시를 선택합니다.** 이 설정은 Microsoft 365 관리 센터 및 Teams 관리 센터의 사용 보고서에 모두 적용됩니다.
  
3. 변경 **내용 저장 을 선택합니다.**

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
