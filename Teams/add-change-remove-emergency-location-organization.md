---
title: 긴급 위치 추가, 변경, 제거
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
description: 'Microsoft 팀 관리 센터에서 조직의 긴급 위치를 추가, 변경 또는 제거 하는 방법에 대해 알아봅니다. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bed76fdfff2a6af2dabb3eef5c01dcfb39f422a
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539465"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>조직의 응급 위치 추가, 변경 또는 제거

비상 위치는 전화 번호와 연결 되어야 하지만,이 문제가 발생 하는 경우 국가와 지역에 따라 다를 수 있습니다. 예를 들어 미국에서 사용자에 게 전화 번호를 할당할 때 비상 위치를 연결 해야 합니다. 영국에서는 Office 365에서 전화 번호를 받고 현재 서비스 공급자 로부터 전화 번호를 전송 하면 비상 위치를 전화 번호에 연결 해야 합니다.

거주 국가 또는 지역에 관계 없이 긴급 위치에 위치 또는 위치를 추가 하 고 긴급 위치를 제거할 수 있습니다. 조직의 실제 위치 수에 따라 빌딩, 바닥, 사무실 등의 위치를 만들 수 있습니다. [비상 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)를 참조 하세요.
  
통화 요금제와 비용을 가져오는 방법을 알아보려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.

Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 조직의 긴급 위치를 관리할 수 있습니다.
  
## <a name="add-an-emergency-location"></a>긴급 위치 추가

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.
2. **추가**를 클릭 합니다.
3. 위치에 대 한 이름과 설명을 입력 합니다.
4. 국가 또는 지역을 선택한 다음 주소를 입력 합니다.

   > [!NOTE]
   > 벨기에, 프랑스, 독일, 아일랜드, 네덜란드, 스페인에서는 Office 365에서 전화 번호를 성공적으로 활성화 하는 것을 이해 하는 것이 중요 합니다. 번호를 구하는 데 사용 되는 비상 위치에 설정 된 주소는 전화 번호의 지역 번호와 일치 해야 합니다.
5. 주소를 찾을 수 없는 경우 수동으로 주소를 편집 하려면 **수동으로 주소 편집**을 설정 합니다.
6. **저장**을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[새로운 CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)을 참조 하세요.
    
## <a name="change-an-emergency-location"></a>긴급 위치 변경

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.
2. 목록에서 변경 하려는 위치를 선택 하 고 **편집**을 클릭 합니다.
3. 원하는 변경 작업을 수행 합니다.
4. **저장**을 클릭합니다.

> [!NOTE]
> 주소의 유효성을 검사 하지 않은 경우에만 위치에 대 한 주소 정보를 변경할 수 있습니다. 주소가 이미 확인 되었고 주소를 변경 해야 하는 경우 위치를 삭제 하 고 올바른 주소로 새 위치를 만듭니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)를 참조 하세요.
    
## <a name="remove-an-emergency-location"></a>긴급 위치 제거

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.
2. 목록에서 제거 하려는 위치를 선택 하 고 **삭제**를 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[제거-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)을 참조 하세요.

## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)
