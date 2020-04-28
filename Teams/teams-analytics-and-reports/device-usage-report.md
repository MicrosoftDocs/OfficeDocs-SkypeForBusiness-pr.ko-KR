---
title: Microsoft 팀 장치 사용 보고서
author: LanaChin
ms.author: v-lanac
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
description: Microsoft 팀 관리 센터에서 팀 디바이스 사용 보고서를 사용 하 여 조직의 사용자가 팀에 연결 되는 방식을 확인 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 128a9e816249dd918a5bf5fb380fde78d3ed9ce2
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904920"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft 팀 장치 사용 보고서

Microsoft 팀 관리 센터의 팀 장치 사용 보고서에서 사용자가 팀에 연결 하는 방법에 대 한 정보를 제공 합니다. 이 보고서를 사용 하 여 이동 중에 모바일 장치에서 사용 하는 팀의 수를 포함 하 여 조직에서 사용 하는 장치를 확인할 수 있습니다.  

## <a name="view-the-device-usage-report"></a>장치 사용 현황 보고서 보기

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **분석 & 보고서** > **사용 현황 보고서**를 클릭 합니다. 보고서 **보기** 탭의 **보고서**에서 **팀 디바이스 사용**을 선택 합니다.
2. **날짜 범위**아래에서 범위를 선택 하 고 **보고서 실행**을 클릭 합니다.

    ![팀 관리 센터에서 설명선이 포함 된 팀 디바이스 사용 보고서 스크린샷](../media/teams-reports-device-usage-with-callouts.png "팀 관리 센터에서 설명선이 포함 된 팀 디바이스 사용 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|호출 |설명  |
|--------|-------------|
|**1**   |팀 디바이스 사용 보고서는 지난 7 일 또는 28 일 동안의 추세에 대해 볼 수 있습니다.  |
|**2**   |각 보고서에는 보고서가 생성 된 날짜를 포함 합니다. 일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다. |
|**3**   |<ul><li>차트의 X 축은 팀에 연결 하는 데 사용 되는 여러 장치 (**Windows**, **Mac**, **Linux**, **iOS**, **Android 휴대폰**)를 나타냅니다. </li><li>Y 축은 선택한 기간 동안 디바이스를 사용 하는 사용자 수입니다.</li> </ul>장치를 나타내는 막대 위에 마우스를 놓아 장치를 사용 하 여 팀에 연결 하는 사용자 수를 확인 합니다.|
|**4(tcp/ipv4)**   |이 표는 사용자 별 장치 사용을 분석 하는 방법을 보여 줍니다. <ul><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭 하 여 Microsoft 팀 관리 센터의 사용자 설정 페이지로 이동할 수 있습니다. </li><li>**Windows는** 사용자가 windows 기반 컴퓨터의 팀 데스크톱 클라이언트에서 활성 상태 였던 경우 선택 됩니다.</li><li>**Mac** 은 사용자가 macos 컴퓨터의 팀 데스크톱 클라이언트에서 활성 상태 였던 경우 선택 됩니다. </li> <li>**Linux는** 사용자가 linux 컴퓨터의 팀 데스크톱 클라이언트에서 활성 상태 였던 경우 선택 됩니다. </li> <li>사용자가 iOS 용 팀 모바일 클라이언트에서 활성 상태 였던 경우 **ios** 가 선택 됩니다.</li><li>Android 용 팀 모바일 클라이언트에서 사용자가 활성 상태 였던 경우 **android 전화** 를 선택 합니다. <li>**마지막 활동** 은 사용자가 팀 활동에 참여 한 마지막 날짜 (UTC)입니다.</li> </ul> 사용자 계정이 더 이상 Azure AD에 존재 하지 않는 경우에는 테이블에 사용자 이름이 "--"로 표시 됨을 참고 하세요. <br><br>표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다. |
|**5mb**   |**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다. |
|**26**   |오프 라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를**클릭 한 다음 **다운로드** 탭에서 **다운로드** 를 클릭 하 여 준비 된 보고서를 다운로드 합니다.<br><br>![내보낸 보고서를 보여 주는 다운로드 탭의 스크린샷](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>관련 항목

- [팀 분석 및 보고](teams-reporting-reference.md)