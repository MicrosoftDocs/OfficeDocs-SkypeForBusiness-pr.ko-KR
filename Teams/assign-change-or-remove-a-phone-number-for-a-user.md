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
description: 외부 기업과 클라이언트가 전화를 걸 수 있도록 Teams 사용자의 회사 전화 번호를 할당, 변경 또는 제거하는 방법을 알아봅니다.
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414686"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>사용자의 전화 번호 할당, 변경 또는 제거

통화 플랜, 운영자 연결 또는 Teams Phone Mobile을 설정할 때 사용자에게 전화 번호를 할당합니다. Microsoft Teams에서는 사용자가 **통화를** 클릭할 때 할당하는 전화 번호가 나열됩니다.

이 문서는 통화 플랜, 운영자 연결 및 Teams 전화 모바일에 적용됩니다. 직접 라우팅 시나리오에서 사용자의 전화 번호 할당, 변경 또는 제거에 대한 자세한 내용은 [직접 라우팅, 음성 및 음성 메일에 대한 사용자 사용을 참조하세요](./direct-routing-enable-users.md).

통화 플랜, 운영자 연결 또는 Teams Phone Mobile 사용자에 대한 번호를 할당하기 전에 사용자의 번호를 받아야 합니다. 자세한 내용은 [통화 플랜 사용자에 대한 번호 가져오기](getting-phone-numbers-for-your-users.md), [운영자 연결 사용자에 대한 번호 설정](operator-connect-configure.md#set-up-phone-numbers) 또는 [Teams Phone Mobile 사용자에 대한 번호 설정을 참조하세요](operator-connect-mobile-configure.md).

> [!NOTE]
> 사용자에게 할당된 라이선스가 있는지 확인하는 한 가지 방법은 Microsoft Teams 관리 센터 > **Users** 로 가는 것입니다. 라이선스가 할당되면 페이지에 표시됩니다.  Microsoft 365 관리 센터 사용할 수도 있습니다.

> [!NOTE]
> 이 메모는 온-프레미스 Active Directory 사용하여 하이브리드 배포를 하는 고객에게 적용됩니다. 통화 플랜 또는 운영자 연결 전화 번호를 사용자 또는 리소스 계정에 할당하려면 온-프레미스 Active Directory 사용자 또는 리소스 계정 개체의 msRTCSIP-Line 특성에 저장된 전화 번호가 제거되고 변경 내용이 Microsoft 365로 동기화되었는지 확인해야 합니다.

## <a name="assign-a-phone-number-to-a-user"></a>사용자에게 전화 번호 할당

사용자에게 전화 번호를 할당할 때 사용자의 전화 번호와 사용 위치가 동일한 국가인지 확인합니다.

Teams 관리 센터를 사용하여 숫자를 할당하려면 다음을 수행합니다.

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


PowerShell을 사용하여 숫자를 할당하려면 [다음과 같이 Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) cmdlet을 사용합니다.

통화 플랜 번호의 경우:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

연산자 연결 번호의 경우:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Teams 전화 번호의 경우:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

예를 들면 다음과 같습니다.

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```

> [!NOTE]
> Microsoft 365와 Teams 간의 대기 시간으로 인해 사용자를 사용하도록 설정하는 데 최대 24시간이 걸릴 수 있습니다. 24시간 후에 전화 번호가 올바르게 할당되지 않은 경우 [전화 번호 서비스 센터를 참조하세요](https://pstnsd.powerappsportals.com/).

> [!NOTE]
> 전화 번호를 할당하면 EnterpriseVoiceEnabled 플래그가 자동으로 True로 설정됩니다.

## <a name="change-a-phone-number-for-a-user"></a>사용자의 전화 번호 변경

Teams 관리 센터를 사용하여 사용자의 전화 번호를 변경하려면 다음을 수행합니다.

1. 왼쪽 탐색 영역에서 **사용자를** 클릭하고, 원하는 사용자를 찾아 두 번 클릭하고, **계정을** 클릭한 다음, **일반 정보** 에서 사용자에게 할당된 전화 번호를 기록합니다.

2. 왼쪽 탐색 영역에서 **음성** \> **전화 번호를** 클릭합니다.

3. **전화 번호** 페이지에서 1단계에서 식별한 번호를 선택한 다음 **편집** 을 클릭합니다.

4. **편집** 창의 **할당 대상** 에서 **X** 를 클릭하여 사용자를 제거합니다.

5. **저장** 을 클릭합니다.

6. **전화 번호** 페이지에서 목록에서 할당되지 않은 번호를 선택한 다음 **편집** 을 클릭합니다.

7. **편집** 창의 **할당 대상** 에서 표시 이름 또는 사용자 이름으로 사용자를 검색한 다음 **할당** 을 클릭합니다.

8. 연결된 긴급 위치를 할당하거나 변경하려면 **긴급 위치에서** 위치를 검색한 다음 선택합니다.

      > [!NOTE]
      > Operator Connect 또는 Teams Phone Mobile 사용자의 번호를 변경하는 경우 연결된 긴급 위치를 할당하거나 변경하지 못할 수 있습니다. 이 기능은 운영자에 따라 달라집니다. 자세한 내용은 운영자에게 문의하세요.

9. **저장** 을 클릭합니다.

PowerShell 예제는 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)를 참조하세요.

## <a name="remove-a-phone-number-from-a-user"></a>사용자로부터 전화 번호 제거

Teams 관리 센터를 사용하여 전화 번호를 제거하려면 다음을 수행합니다.

1. 왼쪽 탐색 영역에서 **사용자를** 클릭하고, 원하는 사용자를 찾아 두 번 클릭하고, **계정을** 클릭한 다음, **일반 정보** 에서 사용자에게 할당된 전화 번호를 기록합니다.

2. 왼쪽 탐색 영역에서 **음성** \> **전화 번호를** 클릭합니다.

3. **전화 번호** 페이지에서 2단계에서 식별한 번호를 선택한 다음 **편집** 을 클릭합니다.

4. **편집** 창의 **할당 대상** 에서 **X** 를 클릭하여 사용자를 제거합니다.

5. **저장** 을 클릭합니다.

PowerShell 예제는 [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)를 참조하세요.

## <a name="related-topics"></a>관련 주제

[주소 유효성 검사란?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
