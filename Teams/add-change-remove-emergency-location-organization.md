---
title: 긴급 위치 추가, 변경, 제거
author: cichur
ms.author: v-cichur
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
description: '관리 센터에서 조직에 대한 긴급 위치를 추가, 변경 또는 제거하는 Microsoft Teams 자세히 알아보습니다. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 69ac20583d2f90b3aab4359478f067d2df7b86d2733f6452172430566781ea7d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352486"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>조직의 응급 위치 추가, 변경 또는 제거

긴급 위치는 전화 번호와 연결되어야 하지만 이 경우 국가와 지역마다 다를 수 있습니다. 예를 들어 미국에서는 사용자에게 전화 번호를 할당할 때 긴급 위치를 연결해야 합니다. 영국에서는 현재 서비스 공급자로부터 전화 번호를 Microsoft 365 또는 Office 365 경우 긴급 위치를 전화 번호에 연결해야 합니다.

어느 국가나 지역에 상관없이 비상 위치에 장소 또는 장소를 추가하고 긴급 위치를 제거할 수 있습니다. 조직의 물리적 위치 수에 따라 건물, 바닥 및 사무실에 대한 장소를 만들 수 있습니다. 긴급 [통화 관리 를 참조합니다.](what-are-emergency-locations-addresses-and-call-routing.md)
  
통화 계획 및 비용에 대한 자세한 내용은 추가 Teams [라이선스 를 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 조직의 긴급 위치를 관리합니다.
  
## <a name="add-an-emergency-location"></a>긴급 위치 추가

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 긴급 **주소**  >  **를 클릭합니다.**
2. **추가** 를 클릭합니다.
3. 위치에 대한 이름 및 설명을 입력합니다.
4. 국가 또는 지역을 선택한 다음 주소를 입력합니다.

   > [!NOTE]
   > 벨기에, 프랑스, 독일, 아일랜드, 네덜란드 및 스페인의 경우 전화 번호를 Microsoft 365 Office 365 전화 번호를 획득하는 데 사용되는 긴급 위치에 설정된 주소가 전화 번호의 영역 코드와 일치해야 합니다.

5. 주소를 찾을 수 없는 경우 주소를 수동으로 편집하려는 경우 수동으로 주소 **편집을 를 입력합니다.**
6. **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsOnlineLisCivicAddress 를 참조합니다.](/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>긴급 위치 변경

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 긴급 **주소**  >  **를 클릭합니다.**
2. 목록에서 변경할 위치를 선택한 다음 **편집을 클릭합니다.**
3. 원하는 내용을 변경합니다.
4. **저장** 을 클릭합니다.

> [!NOTE]
> 주소의 유효성이 검사되지 않은 경우 위치에 대한 주소 정보를 변경할 수 있습니다. 주소의 유효성이 이미 검사되어 있는 경우 주소를 변경하고 위치를 삭제한 다음 올바른 주소로 새 위치를 만들어야 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineLisCivicAddress 를 참조합니다.](/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>긴급 위치 제거

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 긴급 **주소**  >  **를 클릭합니다.**
2. 목록에서 제거할 위치를 선택한 다음 **삭제를 클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Remove-CsOnlineLisCivicAddress 를 참조합니다.](/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)