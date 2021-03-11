---
title: 사용자의 전화 번호 할당, 변경 또는 제거
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 외부 기업 및 클라이언트가 전화를 걸 수 있도록 Teams 사용자에 대한 회사 전화 번호를 할당, 변경 또는 제거하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589622"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>사용자에 대한 전화 번호 할당, 변경 또는 제거(계획 호출)

통화 계획을 설정할 때 사용자에게 전화 번호를 할당합니다. Microsoft Teams에서 사용자가 호출을 클릭하면 할당한 전화 번호가 **나열됩니다.** 직접 라우팅 시나리오에서 사용자로부터 전화 번호를 할당, 변경 또는 제거하는 방법에 대한 지침은 직접 라우팅, 음성 및 음성메일에 대해 사용자 사용 을 [참조하세요.](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)

![Teams에 표시되는 사용자의 전화 번호입니다.](media/teams-phone-number.png)

사용자가 전화를 걸고 받을 수 있도록 사용자를 설정하는 경우 먼저 Microsoft Teams 관리 센터를 사용하여 전화 번호를 할당해야 합니다. 필요한 경우 전화 번호를 변경하거나 제거할 수 있습니다.
  
Teams에서 통화 요금제와 비용에 대한 자세한 내용은 [Teams 추가 기능 라이선스 를 참조합니다.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
> [!NOTE]
> 사용자가 라이선스가 할당되어 있는지를 보는 한 가지 방법은 Microsoft Teams 관리 센터로 > **있습니다.** 라이선스가 할당된 경우 페이지에 표시됩니다.  Microsoft 365 관리 센터를 사용할 수도 있습니다.
  
## <a name="assign-a-phone-number-to-a-user"></a>사용자에게 전화 번호 할당
 
![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**
    
1. 왼쪽 탐색에서 **음성**  >  **전화 번호 를 클릭합니다.**
2. 전화 번호 **페이지에서** 목록에서 부호 없는 번호를 선택한 다음 **편집을 클릭합니다.**  
3. 편집 **창의** 에 할당된 **에서** 표시 이름 또는 사용자 이름으로 사용자를 검색한 다음 **할당을 클릭합니다.**
4. 관련 긴급 위치를 할당하거나 변경하려면 긴급 위치 **아래에서** 위치를 검색한 다음 위치를 선택합니다.
5. 전화 번호 정보가 있는 사용자에게 전자 메일을 보낼지 여부에 따라 전화 번호 정보가 있는 전자 메일 사용자를 끄거나 **끄거나 끄기** 기본적으로 이 설정은 설정되어 있습니다. 
6. **저장** 을 클릭합니다.

PowerShell 예제는 [Set-CsOnlineVoiceUser 를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>사용자의 전화 번호 변경
 
![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**
    
1. 왼쪽 탐색에서 사용자를 클릭하고 원하는 사용자를 찾아 두 번 클릭한 다음, 계정을 클릭한 다음 일반 정보에서 사용자에게 할당된 전화 번호를 메모합니다. 
2. 왼쪽 탐색에서 **음성**  >  **전화 번호 를 클릭합니다.**
3. 전화 번호 **페이지에서** 1단계에서 식별한 번호를 선택한 다음 편집을 **클릭합니다.**  
4. 편집 **창의** 할당된 **에서** **X를** 클릭하여 사용자를 제거합니다.
5. **저장** 을 클릭합니다.
6. 전화 번호 **페이지에서** 목록에서 부호 없는 번호를 선택한 다음 **편집을 클릭합니다.**  
7. 편집 **창의** 에 할당된 **에서** 표시 이름 또는 사용자 이름으로 사용자를 검색한 다음 **할당을 클릭합니다.**
8. 관련 긴급 위치를 할당하거나 변경하려면 긴급 위치 **아래에서** 위치를 검색한 다음 위치를 선택합니다.
9. **저장** 을 클릭합니다.

PowerShell 예제는 [Set-CsOnlineVoiceUser 를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="remove-a-phone-number-from-a-user"></a>사용자에서 전화 번호 제거
 
![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 사용자를 클릭하고 원하는 사용자를 찾아 두 번 클릭한 다음, 계정을 클릭한 다음 일반 정보에서 사용자에게 할당된 전화 번호를 메모합니다. 
2. 왼쪽 탐색에서 **음성**  >  **전화 번호 를 클릭합니다.**
3. 전화 번호 **페이지에서** 2단계에서 식별한 번호를 선택한 다음 **편집을 클릭합니다.**  
4. 편집 **창의** 할당된 **에서** **X를** 클릭하여 사용자를 제거합니다.
5. **저장** 을 클릭합니다.

PowerShell 예제는 [Set-CsOnlineVoiceUser 를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="related-topics"></a>관련 항목

[주소 유효성 검사란?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Microsoft 365 요금제 호출](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
