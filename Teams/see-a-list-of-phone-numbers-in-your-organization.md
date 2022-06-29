---
title: 조직의 전화 번호 목록 보기
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Microsoft Teams 관리 센터를 사용하여 조직의 모든 전화 번호 목록과 사용자에게 할당되거나 할당되지 않은 모든 번호를 확인하는 방법을 알아봅니다.
ms.openlocfilehash: 84162b3971b1730df114482d30820dcf7e86a684
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494465"
---
# <a name="see-a-list-of-telephone-numbers"></a>전화 번호 목록 보기 

[오디오 회의](deploy-audio-conferencing-teams-landing-page.md) 또는 통화 큐와 같은 사용자 또는 음성 애플리케이션에 할당할 수 있는 다양한 유형의 전화 번호[가 있습니다](plan-auto-attendant-call-queue.md). 자세한 내용은 [조직의 전화 번호 관리를 참조하세요](/microsoftteams/manage-phone-numbers-landing-page).

이 문서는 통화 플랜 및 운영자 연결에 적용됩니다. 직접 라우팅에 대한 자세한 내용은 [전화 번호 구성 및 엔터프라이즈 음성 사용 설정을](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice) 참조하세요.
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>조직의 모든 전화 번호를 보려면

조직의 모든 전화 번호 목록을 보려면 다음을 수행합니다.

1. **Microsoft Teams 관리 센터로** 이동합니다.

2. 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동합니다.

3. 할당된 전화 번호를 보려면 **할당 상태** 열을 참조하세요. 이 열에는 번호가 할당된 서비스 유형도 표시됩니다.

4. 보기를 필터링하려면 필터 아이콘을 클릭합니다. **필터** 창에서 드롭다운 목록을 사용하여 보기를 다음과 같이 필터링할 수 있습니다.

   - 설정한 **숫자 범위** 입니다. 가장 낮은 숫자 또는 가장 높은 수로 검색할 수 있습니다.

   - 지정한 숫자로 시작하는 숫자입니다.

   - 숫자 **활성화 상태입니다**.

   - 숫자 **형식입니다**.

   - 전화 번호 **상태입니다**.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>사용자에게 할당된 모든 전화 번호를 보려면

사용자를 설정할 때 사용자에게 이미 할당된 전화 번호 목록과 사용자에게 할당할 수 있는 전화 번호 목록을 볼 수 있습니다.

1. **Microsoft Teams 관리 센터로** 이동합니다.

2. 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동합니다.

    > [!IMPORTANT]
    > Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** 옵션을 보려면 먼저 **하나 이상의 Enterprise E5 라이선스**, 1개의 **전화 시스템** 추가 기능 라이선스 또는 하나의 **오디오 회의** 추가 기능 라이선스를 구입해야 합니다.

3. 할당된 숫자를 확인할 수 있도록 숫자를 빠르게 정렬하려면 **할당 상태** 열 머리글을 클릭합니다. 또는 필터 아이콘을 클릭한 다음 보기를 필터링하여 사용자에게 이미 할당된 전화 번호 또는 사용자에게 할당할 수 있는 할당되지 않은 번호를 볼 수 있습니다. 다음을 통해 필터링할 수 있습니다.

   - **사용자에게 할당됨**
   - **컨퍼런스 브리지에 할당됨** 
   - **음성 앱에 할당됨(자동 전화 교환/통화 큐)**
   - **할당**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>음성 사용자에게 할당된 모든 전화 번호를 보려면

조직의 사용자가 전화를 걸고 받을 수 있도록 설정하는 경우 먼저 전화 번호를 받은 다음 사용자에게 할당해야 합니다. 전화 번호를 받은 후 번호 할당의 활성화 상태를 볼 수 있습니다.
  
1. **Microsoft Teams 관리 센터로** 이동합니다.

2. 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동합니다.

3. 필터 아이콘을 클릭하여 **활성화 상태로** 보기를 필터링합니다. 다음을 통해 필터링할 수 있습니다.

   - **활성화**
   - **배정 보류 중**
   - **할당 실패**
   - **업데이트 보류 중**
   - **업데이트 실패**

## <a name="using-the-teams-powershell-module"></a>Teams PowerShell 모듈 사용

Teams PowerShell 모듈을 사용하여 이전 섹션에서 동일한 정보를 가져올 수 있지만 비즈니스용 Skype Online 커넥터의 통합을 포함하는 버전 1.1.6 이상이 필요합니다. 모듈에 대한 자세한 내용은 [Microsoft Teams PowerShell 개요](teams-powershell-overview.md)를 참조하세요.

조직에 대해 가지고 있는 모든 전화 번호 목록을 보려면 [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) cmdlet을 사용합니다. 예를 들어 각 전화 번호, 해당 유형 및 상태를 보려면 다음 명령을 실행합니다.

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

사용자에게 할당된 모든 전화 번호를 보려면 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) cmdlet을 사용합니다. 예를 들어 전화 번호가 할당된 모든 사용자를 보려면 다음 명령을 실행합니다.

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>관련 항목

[조직의 전화 번호 관리](manage-phone-numbers-landing-page.md)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
