---
title: Microsoft Teams 장치 사용 현황 보고서
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
description: Microsoft Teams 관리 센터에서 Teams 장치 사용 현황 보고서를 사용하여 조직의 사용자가 Teams에 연결하는 방법을 확인합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815648"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 장치 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 장치 사용 현황 보고서는 사용자가 Teams에 연결하는 방법에 대한 정보를 제공합니다. 이동 중 모바일 장치에서 Teams를 사용하는 수를 포함하여 보고서를 사용하여 조직 전체에서 사용되는 장치를 볼 수 있습니다.  

## <a name="view-the-device-usage-report"></a>디바이스 사용 보고서 보기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Analytics & **보고서를**  >  **클릭합니다.** 보고서 보기 **탭의** **보고서에서** Teams 장치 **사용 현황을 선택합니다.**
2. 날짜 **범위에서** 범위를 선택한 다음 보고서 **실행을 클릭합니다.**

    ![설명선이 있는 Teams 관리 센터의 Teams 장치 사용 현황 보고서 스크린샷](../media/teams-reports-device-usage-with-callouts.png "설명선이 있는 Teams 관리 센터의 Teams 장치 사용 현황 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|Callout |설명  |
|--------|-------------|
|**1**   |Teams 장치 사용 현황 보고서에서 지난 7일 또는 30일간의 추세를 볼 수 있습니다.  |
|**2**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24시간의 대기 시간을 반영합니다. |
|**3**   |<ul><li>차트의 X축은 Teams에 연결하는 데 사용되는 다양한 **장치(Windows,** **Mac,** **Linux,** **iOS,** **Android Phone,** **Web)를** 나타냅니다. </li><li>Y축은 선택한 기간 동안 디바이스를 사용하는 사용자 수입니다.</li> </ul>장치를 나타내는 막대 위에 마우스를 대면 Teams에 연결하는 장치를 사용하는 사용자 수를 볼 수 있습니다.|
|**4**   |이 표에서는 사용자별 디바이스 사용량을 분석합니다. <ul><li>**사용자** 이름은 사용자의 표시 이름입니다. 표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다. </li><li>**사용자가 Windows** 기반 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Windows가 선택됩니다.</li><li>**사용자가 macOS** 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Mac이 선택됩니다. </li> <li>**사용자가 Linux** 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 Linux가 선택됩니다. </li> <li>**사용자가 iOS용** Teams 모바일 클라이언트에서 활성 상태인 경우 iOS가 선택됩니다.</li><li>**Android용** Teams 모바일 클라이언트에서 사용자가 활성 상태인 경우 Android 휴대폰이 선택됩니다. <li><li>**사용자가** Teams 웹 클라이언트에서 활성 상태인 경우 웹이 선택됩니다. <li>**마지막 활동은** 사용자가 Teams 활동에 참여한 마지막 날짜(UTC)입니다.</li> </ul> 사용자 계정이 Azure AD에 더 이상 없는 경우 사용자 이름은 테이블에 "--"로 표시됩니다. <br><br>표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다. |
|**5**   |열 **편집을 선택하여** 표에서 열을 추가하거나 제거합니다. |
|**6**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를** 클릭한  다음 다운로드 탭에서 다운로드를 클릭하여 준비가 되면 보고서를 다운로드합니다. <br><br>![내보낼 보고서를 보여주는 다운로드 탭의 스크린샷](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
