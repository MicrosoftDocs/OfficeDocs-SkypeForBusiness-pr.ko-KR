---
title: 사용자의 전화 번호 할당, 변경 또는 제거
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 비즈니스 및 클라이언트 외부에서 전화를 걸 수 있도록 사용자에 대한 회사 Teams 전화 번호를 할당, 변경 또는 제거하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 6341b6c3242eafad7039b210995ee7c56613442e
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456911"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>사용자의 전화 번호 할당, 변경 또는 제거

통화 요금제 또는 운영자를 커넥트 사용자에게 전화 번호를 할당합니다. Microsoft Teams 사용자가 통화를 클릭하면 할당한 전화 번호가 나열 **됩니다**. 

이 문서는 통화 계획 및 운영자 커넥트. 직접 라우팅 시나리오에서 사용자로부터 전화 번호를 할당, 변경 또는 제거하는 자세한 내용은 직접 라우팅, 음성 및 음성메일에 대한 사용자 사용 을 [참조하세요](./direct-routing-enable-users.md).

통화 요금제 또는 운영자 사용자에 대한 번호를 할당하기 커넥트 사용자에 대한 번호를 입력해야 합니다. 자세한 [내용은 전화 요금](getting-phone-numbers-for-your-users.md)제 사용자에 대한 번호 [커넥트 참조하세요](operator-connect-configure.md#set-up-phone-numbers).

  
> [!NOTE]
> 사용자에게 할당된 라이선스가 있는지 여부를 확인하는 한 가지 방법은 사용자에 대한 Microsoft Teams 관리 센터로 > **있습니다**. 라이선스가 할당된 경우 페이지에 표시됩니다.  또한 이 Microsoft 365 관리 센터.

> [!NOTE]
> 이 참고 사항은 On-프레미스 Active Directory를 통해 하이브리드 배포가 있는 고객에게 적용됩니다. 전화 요금제 또는 운영자 커넥트 전화 번호를 사용자 또는 리소스 계정에 할당하려는 경우 프레미스 Active Directory의 사용자 또는 리소스 계정 개체의 msRTCSIP-Line 특성에 저장된 모든 전화 번호가 제거되고 변경 내용이 Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>사용자에게 전화 번호 할당

사용자에게 전화 번호를 할당할 때 사용자의 전화 번호와 사용 현황 위치가 같은 국가에 있는지 확인하세요.

관리 센터를 사용하여 Teams:
    
1. 왼쪽 탐색에서 **Voice** > **전화 숫자를 클릭합니다**.

2. 번호 **전화** 페이지에서 목록에서 부호 없는 번호를 선택한 다음 편집을 **클릭합니다**.  

3. 편집 **창의** 할당에서 표시 이름 또는 사용자 이름으로 사용자를 검색한 다음 할당을 **클릭합니다**.

4. 관련 긴급 위치를 할당하거나 변경하려면 긴급 위치 아래에서 위치를 검색한 다음 위치를 선택합니다.

   > [!NOTE]
   > 연산자 사용자에 번호를 할당하는 경우 커넥트 위치를 할당하거나 변경할 수 없습니다. 이 기능은 운영자에 따라 달라 습니다. 자세한 내용은 운영자에게 문의하세요.

5. 전화 번호 정보를 통해 사용자에게 전자 메일을 보낼지 여부에 따라 전화 번호 정보가 있는 전자 메일 사용자를 끄거나 **끄거나 끄면 됩니다**. 기본적으로 이 설정은 설정되어 있습니다. 

6. **저장** 을 클릭합니다.

PowerShell을 사용하여 숫자를 할당하기 위해 다음과 같이 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) cmdlet을 사용 합니다.

통화 계획 번호의 경우
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

연산자 커넥트 번호의 경우
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

예를 들면 다음과 같습니다.

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
```

> [!NOTE]
> 사용자와 Microsoft 365 Teams 대기 시간이 있기 때문에 사용자가 사용하도록 설정하는 데 최대 24시간이 걸릴 수 있습니다. 24시간 후에 전화 번호가 올바르게 할당되지 않은 경우 번호 [전화 서비스 센터를 참조합니다](https://pstnsd.powerappsportals.com/). 

  
## <a name="change-a-phone-number-for-a-user"></a>사용자의 전화 번호 변경

관리자 센터를 사용하여 사용자의 전화 번호를 Teams:
    
1. 왼쪽 탐색에서 사용자를 클릭하고 원하는 사용자를 찾아 두 번 클릭한 다음 계정을 클릭한 다음 일반 정보에서 사용자에게 할당된 전화 번호를 메모합니다.

2. 왼쪽 탐색에서 **Voice** > **전화 숫자를 클릭합니다**.

3. 숫자 **전화** 페이지에서 1단계에서 식별한 번호를 선택한 다음 편집을 **클릭합니다**.  

4. 편집 **창** 에서 할당된 창에서 **X** 를 클릭하여 사용자를 제거합니다.

5. **저장** 을 클릭합니다.

6. 번호 **전화** 페이지에서 목록에서 부호 없는 번호를 선택한 다음 편집을 **클릭합니다**.  

7. 편집 **창의** 할당에서 표시 이름 또는 사용자 이름으로 사용자를 검색한 다음 할당을 **클릭합니다**.

8. 관련 긴급 위치를 할당하거나 변경하려면 긴급 위치 아래에서 위치를 검색한 다음 위치를 선택합니다.

      > [!NOTE]
      > 연산자 사용자에 대한 번호를 변경하는 커넥트 관련 긴급 위치를 할당하거나 변경할 수 없습니다. 이 기능은 운영자에 따라 달라 습니다. 자세한 내용은 운영자에게 문의하세요.

9. **저장** 을 클릭합니다.

PowerShell 예제는 [Set-CsPhoneNumberAssignment를 참조합니다](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>사용자에서 전화 번호 제거

관리 센터를 사용하여 전화 번호를 Teams:

1. 왼쪽 탐색에서 사용자를 클릭하고 원하는 사용자를 찾아 두 번 클릭한 다음 계정을 클릭한 다음 일반 정보에서 사용자에게 할당된 전화 번호를 메모합니다.

2. 왼쪽 탐색에서 **Voice** > **전화 숫자를 클릭합니다**.

3. 숫자 **전화** 페이지에서 2단계에서 식별한 번호를 선택한 다음 편집을 **클릭합니다**.  

4. 편집 **창** 에서 할당된 창에서 **X** 를 클릭하여 사용자를 제거합니다.

5. **저장** 을 클릭합니다.

PowerShell 예제는 [Remove-CsPhoneNumberAssignment를 참조합니다](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>관련 항목

[주소 유효성 검사란?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)

