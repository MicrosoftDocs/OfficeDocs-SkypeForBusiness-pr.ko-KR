---
title: 지정, 사용자의 긴급 위치에 대 한 위치 변경
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 이 문서에서는 조직의 사용자에 대 한 긴급 위치를 할당 하거나 변경 하는 방법을 설명 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5b13cf5d4b4a0cf22077318e3c2c2196840f66e
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232469"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>사용자에 대 한 긴급 위치 지정 또는 변경

사용자에 게 전화 번호를 할당할 때 각 활성 전화 번호에는 비상 위치가 연결 되어 있어야 합니다. (Office 365에서 전화 번호를 받을 때 주소를 연결 하거나 전화 번호를 전송 하는 경우) 비상 위치와 번호를 연결 하는 경우 실제 위치 내에서 더 정확한 위치를 제공 하는 위치를 추가할 수도 있습니다. 장소는 바닥, 건물 날개 또는 사용자가 위치한 사무실 번호 일 수 있습니다. 지정 된 비상 위치에 대해 무제한의 장소를 가질 수 있으며 사용자가 다른 사무실 이나 건물으로 이동 하는 경우에는 위치를 변경할 수 있습니다. 예를 들어 사용자가 밑면 34에서 floor 35로 이동 합니다.
  
통화 계획을 가져오는 방법과 비용을 파악 하려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.
  
Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 사용자에 대 한 긴급 위치를 지정 하거나 위치를 변경할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **전화 번호**를 클릭 합니다.

2. **전화 번호** 페이지의 목록에서 사용자 번호를 선택 하 고 **편집**을 클릭 합니다.

3. **편집** 창의 **응급 위치**에서 다음 중 하나를 수행 합니다.

    - 장소를 할당 하려면 위치를 검색 한 다음 검색 결과에서 위치를 선택 합니다.

    - 사용자에 게 이미 할당 된 위치를 변경 하려면 **X** 를 클릭 하 여 기존 위치를 제거 하 고을 검색 한 후 할당할 위치를 선택 합니다.

4. **저장**을 클릭합니다.

## <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)를 참조 하세요.
    
## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [사용자의 응급 위치 할당 또는 변경](assign-change-emergency-location-user.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)
