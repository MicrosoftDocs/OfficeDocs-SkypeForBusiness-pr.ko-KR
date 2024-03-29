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
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 조직의 긴급 위치를 추가, 변경 또는 제거하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 99ab0821b8ccdb14664dc0a2aa37c959499ff8ac
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774743"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>조직의 응급 위치 추가, 변경 또는 제거

[PSTN 연결 옵션](pstn-connectivity.md)&mdash;에 관계없이 Microsoft 통화 플랜, 운영자 연결, Teams 전화 모바일 또는 직접 라우팅&mdash;긴급 위치를 전화 번호와 연결할 수 있습니다.

그러나 PSTN 연결 옵션에 따라 응급 위치 및 위치 요구 사항을 관리하는 방법은 다를 수 있습니다. 자세한 내용은 [긴급 통화 관리를 참조하세요](what-are-emergency-locations-addresses-and-call-routing.md).

이 문서에서는 조직의 긴급 위치를 추가, 변경 또는 제거하는 방법을 설명합니다. 

이 문서는 Microsoft 통화 플랜, 운영자 연결, Teams 전화 모바일 및 직접 라우팅에 적용됩니다.

Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 조직의 긴급 위치를 관리합니다.

긴급 위치를 할당하려면 사용자, 전화 번호 및 응급 위치가 모두 동일한 국가에 있어야 합니다. 자세한 내용은 [사용자의 긴급 위치 할당 또는 변경을 참조하세요](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>긴급 위치 추가

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **위치** > **긴급 주소를** 클릭합니다.
2. **추가** 를 클릭합니다.
3. 위치에 대한 이름과 설명을 입력합니다.
4. 국가 또는 지역을 선택한 다음 주소를 입력합니다.

   > [!NOTE]
   > 벨기에, 프랑스, 독일, 아일랜드, 네덜란드 및 스페인에서 Microsoft 365에서 전화 번호를 성공적으로 활성화하려면 번호를 획득하는 데 사용되는 긴급 위치에 설정된 주소가 전화 번호의 지역 번호와 일치해야 한다는 것을 이해하는 것이 중요합니다.

5. 주소를 찾을 수 없고 주소를 수동으로 편집하려면 **수동으로 주소 편집을** 켭니다.
6. **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress)를 참조하세요.
    
## <a name="change-an-emergency-location"></a>긴급 위치 변경

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **위치** > **긴급 주소를** 클릭합니다.
2. 목록에서 변경할 위치를 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 대로 변경합니다.
4. **저장** 을 클릭합니다.

> [!NOTE]
> 주소의 유효성이 검사되지 않은 경우에만 위치에 대한 주소 정보를 변경할 수 있습니다. 주소의 유효성이 이미 검사되었으며 주소를 변경해야 하는 경우 위치를 삭제한 다음 올바른 주소로 새 위치를 만듭니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress)를 참조하세요.
    
## <a name="remove-an-emergency-location"></a>긴급 위치 제거

> [!NOTE]
> 사용자 또는 전화 번호가 할당되지 않은 경우에만 위치를 제거할 수 있습니다. 번호 또는 사용자가 위치에 할당된 경우 먼저 제거해야 합니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **위치** > **긴급 주소를** 클릭합니다.
2. 목록에서 제거할 위치를 선택한 다음 **삭제** 를 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress)를 참조하세요.

## <a name="related-topics"></a>관련 주제

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)
