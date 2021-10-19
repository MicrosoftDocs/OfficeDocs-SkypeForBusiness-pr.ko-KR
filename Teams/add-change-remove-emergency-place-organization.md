---
title: 긴급 위치에 대한 장소 추가, 변경, 제거
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 관리 센터에서 조직에 대한 긴급 위치를 추가, 변경 또는 제거하는 Microsoft Teams 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2bf3e2fad1ee0f0182e2b3a25f2be78f5ef68823
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465968"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>조직의 응급 위치에 대한 장소 추가, 변경 또는 제거

조직의 물리적 위치 수에 따라 건물, 바닥 및 사무실의 위치를 추가하여 보다 구체적인 응급 위치를 만들 수 있습니다. 자세한 [내용은 긴급 통화 관리를](what-are-emergency-locations-addresses-and-call-routing.md) 참조하세요.

관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 조직의 긴급 위치를 관리합니다.
  
## <a name="add-a-place-to-an-emergency-location"></a>응급 위치에 장소 추가

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 긴급 **주소**  >  **를 클릭합니다.**
2. 목록에서 장소를 추가할 위치의 이름을 클릭합니다.
3. 장소 **탭에서** 추가를 **클릭합니다.**
4. 장소 이름을 입력한 다음 적용 을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[New-CsOnlineLisLocation 을 참조합니다.](/powershell/module/skype/new-csonlinelislocation)
    
## <a name="change-a-place-for-an-emergency-location"></a>응급 위치에 대한 장소 변경

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 긴급 **주소**  >  **를 클릭합니다.**
2. 목록에서 위치를 변경할 위치의 이름을 클릭합니다.
3. 장소 **탭에서** 변경할 장소를 선택한 다음 **편집을 클릭합니다.**
4. 장소 정보를 업데이트한 다음 적용을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineLisLocation 을 참조합니다.](/powershell/module/skype/set-csonlinelislocation)
    
## <a name="remove-a-place-from-an-emergency-location"></a>응급 위치에서 장소 제거

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 긴급 **주소**  >  **를 클릭합니다.**
2. 목록에서 장소를 제거할 위치의 이름을 클릭합니다.
3. 장소 **탭에서** 제거할 장소를 선택한 다음 **삭제를 클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Remove-CsOnlineLisLocation 을 참조합니다.](/powershell/module/skype/remove-csonlinelislocation)
    
## <a name="related-topics"></a>관련 항목

- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)