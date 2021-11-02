---
title: 긴급 위치 추가, 변경, 제거
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: '조직의 응급 위치를 추가, 변경 또는 제거하는 방법에 대해 자세히 알아보습니다. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d9c7c56b4e2b2fd14f703d51b4c07cfc173dfa3
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634857"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>조직의 응급 위치 추가, 변경 또는 제거

Microsoft 통화 요금제, 운영자 커넥트 또는 직접 라우팅 비상 위치를 선택하는 [PSTN](pstn-connectivity.md) 연결 옵션에 관계 없이 전화 번호와 연결될 &mdash; &mdash; 수 있습니다.

그러나 PSTN 연결 옵션에 따라 긴급 위치 및 위치 요구 사항을 관리하는 방법은 다를 수 있습니다. 자세한 내용은 긴급 호출 [관리를 참조하세요.](what-are-emergency-locations-addresses-and-call-routing.md)

이 문서에서는 조직의 응급 위치를 추가, 변경 또는 제거하는 방법을 설명합니다. 

이 문서는 Microsoft 통화 계획, 연산자 커넥트 및 직접 라우팅에 적용됩니다.

관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 조직의 긴급 위치를 관리합니다.

긴급 위치를 할당하려면 사용자, 전화 번호 및 긴급 위치를 모두 동일한 국가에 지정해야 합니다. 자세한 내용은 사용자의 긴급 위치 할당 또는 [변경을 참조하세요.](assign-change-emergency-location-user.md)
  
## <a name="add-an-emergency-location"></a>긴급 위치 추가

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 긴급 **주소**  >  **를 클릭합니다.**
2. **추가** 를 클릭합니다.
3. 위치에 대한 이름 및 설명을 입력합니다.
4. 국가 또는 지역을 선택한 다음 주소를 입력합니다.

   > [!NOTE]
   > 벨기에, 프랑스, 독일, 아일랜드, 네덜란드 및 스페인에서는 전화 번호를 성공적으로 활성화하려면 Microsoft 365 획득하는 데 사용되는 긴급 위치에 설정된 주소가 전화 번호의 영역 코드와 일치해야 한다는 것을 이해하는 것이 중요합니다.

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