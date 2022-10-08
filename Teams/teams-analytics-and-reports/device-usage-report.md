---
title: Microsoft Teams 디바이스 사용 현황 보고서
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 디바이스 사용 현황 보고서를 사용하여 조직의 사용자가 Teams에 연결하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033806"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 디바이스 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 디바이스 사용 현황 보고서에는 사용자가 Teams에 연결하는 방법에 대한 정보가 제공됩니다. 보고서를 사용하여 이동 중 모바일 디바이스에서 Teams를 사용하는 횟수를 포함하여 조직 전체에서 사용되는 디바이스를 볼 수 있습니다.  

## <a name="view-the-device-usage-report"></a>디바이스 사용 현황 보고서 보기


Teams 관리 센터에서 보고서를 보려면 전역 관리자, 전역 읽기 권한자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](../using-admin-roles.md)을 참조하세요.


1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서** > **사용 현황 보고서를** 클릭합니다. **보고서 보기** 탭의 **보고서** 아래에서 **Teams 디바이스 사용량을** 선택합니다.
2. **날짜 범위** 에서 범위를 선택한 다음 **보고서 실행을** 클릭합니다.

    ![설명선이 있는 Teams 관리 센터의 Teams 디바이스 사용 현황 보고서 스크린샷.](../media/teams-reports-device-usage-with-callouts.png "설명선이 있는 Teams 관리 센터의 Teams 디바이스 사용 현황 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|설명선 |설명  |
|--------|-------------|
|**1**   |Teams 디바이스 사용 현황 보고서는 지난 7일, 30일, 90일 및 180일 동안의 추세를 볼 수 있습니다.  |
|**2**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**3**   |<ul><li>차트의 X축은 Teams에 연결하는 데 사용되는 다양한 디바이스(**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**)를 나타냅니다. </li><li>Y축은 선택한 기간 동안 디바이스를 사용하는 사용자 수입니다.</li> </ul>디바이스를 나타내는 막대를 마우스로 가리키면 디바이스를 사용하여 Teams에 연결하는 사용자 수가 표시됩니다.|
|**4**   |이 표에서는 사용자별 디바이스 사용 현황을 분석합니다. <ul><li>**사용자 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다. </li><li>**사용자가 Windows** 기반 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태이면 Windows가 선택됩니다.</li><li>**사용자가 macOS** 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태이면 Mac이 선택됩니다. </li> <li>**Linux** 컴퓨터의 Teams 데스크톱 클라이언트에서 사용자가 활성 상태이면 Linux가 선택됩니다. </li> <li>**사용자가 iOS** 용 Teams 모바일 클라이언트에서 활성 상태이면 iOS가 선택됩니다.</li><li>**Android용** Teams 모바일 클라이언트에서 사용자가 활성 상태이면 Android 휴대폰이 선택됩니다.</li><li>**Chrome OS** 는 사용자가 ChromeOS 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태이면 선택됩니다.</li><li>사용자가 Teams **웹** 클라이언트에서 활성 상태이면 웹이 선택됩니다. <li>**마지막 활동** 은 사용자가 Teams 활동에 참여한 마지막 날짜(UTC)입니다.</li> </ul> 사용자 계정이 더 이상 Azure AD 없는 경우 사용자 이름은 테이블에 "--"로 표시됩니다. <br><br>테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다. |
|**5**   |**열 편집을** 선택하여 테이블에서 열을 추가하거나 제거합니다. |
|**6**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보냅니다. **Excel로 내보내기 아이콘을** 선택하면 보고서가 브라우저 내에서 다운로드됩니다.|
|**7** |위쪽 그래프에 표시되는 시계열 데이터는 전체 테넌트에 대해 집계된 다양한 사용량 메트릭을 표시합니다.|
|**8** |botton 절반에 표시되는 테이블 형식 데이터는 사용자별로 집계된 다양한 사용 메트릭을 표시합니다.|


## <a name="make-the-user-specific-data-anonymous"></a>사용자 특정 데이터를 익명으로 만들기

Teams 사용자 활동의 데이터를 익명으로 보고하려면 전역 관리자여야 합니다. 전역 관리자는 보고서 및 내보내기에서 표시 이름, 그룹 이름, 전자 메일 및 AAD ID와 같은 식별 가능한 정보(MD5 해시 사용)를 숨길 수 있습니다.

1. Microsoft 365 관리 센터 **설정** \> **조직 설정** 으로 이동하고 **서비스** 탭에서 **보고서를** 선택합니다.
    
2. **보고서를** 선택한 다음 **, 모든 보고서에서 은폐된 사용자, 그룹 및 사이트 이름 표시를** 선택합니다. 이 설정은 Microsoft 365 관리 센터 사용 현황 보고서와 Teams 관리 센터에 모두 적용됩니다.
  
3. **변경 내용 저장** 을 선택합니다.

> [!NOTE]
> 이 설정을 사용하도록 설정하면 Teams 사용자 활동 보고서, [Teams 디바이스 사용](device-usage-report.md) 현황 보고서 및 [Teams 사용](teams-usage-report.md) [보고서에서 사용자](user-activity-report.md), 그룹 및 사이트 이름 정보를 식별할 수 없습니다. 2021년 9월 1일부터 이 설정은 중요한 정보를 보호하고 회사가 현지 개인 정보 보호법을 지원할 수 있도록 지속적인 노력의 일환으로 모든 사용자가 기본적으로 사용하도록 설정됩니다. 
>
>이 설정은 Microsoft 365 관리 센터, Microsoft Graph 및 Power BI의 Microsoft 365 사용 보고서에도 적용됩니다.

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
