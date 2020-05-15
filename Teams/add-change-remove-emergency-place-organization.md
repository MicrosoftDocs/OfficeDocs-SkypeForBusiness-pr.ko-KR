---
title: 응급 위치에 대 한 위치 추가, 변경, 제거
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
description: Microsoft 팀 관리 센터에서 조직의 긴급 위치를 추가, 변경 또는 제거 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232499"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>조직의 응급 위치에 대한 장소 추가, 변경 또는 제거

조직의 실제 위치 수에 따라 건물, 바닥, 사무실 위치를 추가 하 여 보다 구체적인 비상 위치를 만들 수 있습니다. 자세한 내용은 [비상 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md) 를 참조 하세요.
  
통화 요금제와 비용을 가져오는 방법을 알아보려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.

Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 조직의 긴급 위치를 관리할 수 있습니다.
  
## <a name="add-a-place-to-an-emergency-location"></a>비상 위치에 위치 추가

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.
2. 목록에서 위치를 추가 하려는 위치의 이름을 클릭 합니다.
3. **위치** 탭에서 **위치 추가**를 클릭 합니다.
4. 위치 이름을 입력 한 다음 **적용**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[새로운 CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)을 참조 하세요.
    
## <a name="change-a-place-for-an-emergency-location"></a>비상 연락망 위치 변경

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.
2. 목록에서 위치를 변경 하려는 위치의 이름을 클릭 합니다.
3. **위치** 탭에서 변경 하려는 위치를 선택 하 고 **편집**을 클릭 합니다.
4. 위치 정보를 업데이트 한 다음 **적용**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)를 참조 하세요.
    
## <a name="remove-a-place-from-an-emergency-location"></a>비상 위치에서 위치 제거

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.
2. 목록에서 위치를 제거 하려는 위치의 이름을 클릭 합니다.
3. **위치** 탭에서 제거 하려는 위치를 선택 하 고 **삭제**를 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[제거-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)을 참조 하세요.
    
## <a name="related-topics"></a>관련 항목

- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)
