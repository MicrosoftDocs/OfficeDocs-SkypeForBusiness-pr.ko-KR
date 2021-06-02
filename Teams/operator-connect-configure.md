---
title: 연산자 커넥트
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 연산자를 구성하는 방법에 대해 자세히 커넥트.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb6ceacb6e7a2cc4d458c86edda96511e5230ace
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717859"
---
# <a name="configure-operator-connect"></a>연산자 커넥트

>[!NOTE]
>연산자 커넥트 현재 공개 미리 보기에서만 **사용할 수 있습니다.** 공개 미리 보기를 사용하면 예정된 기능을 테스트하고 피드백을 제공할 수 있습니다. 공개 미리 보기에 포함된 기능은 완료되지 않을 수 있으며, 변경이 진행될 수 있으며, 클라우드에서 지원되지 Office 365 Government 있습니다.

이 문서에서는 연산자를 구성하는 커넥트. 연산자 커넥트 구성하기 전에 연산자에 대한 [](operator-connect-plan.md) 계획을 커넥트 및 라이선스에 대한 정보를 읽어야 합니다.

## <a name="enable-an-operator"></a>연산자 사용

관리 센터에서 연산자를 사용하도록 설정, 편집 및 Teams 수 있습니다. 왼쪽 탐색 창에서 Voice **> 연산자로 이동합니다.**

연산자를 사용하도록 설정하려면:

1. **연산자를 선택 합니다.** 모든 **연산자 탭에서** 지역 또는 서비스별로 사용 가능한 연산자를 필터링하여 음성 요구에 적합한 연산자를 찾습니다. 그런 다음 사용하려는 연산자를 선택합니다.  

2. **국가를 선택합니다.** 연산자 **설정에서** 선택한 연산자를 사용하여 사용하도록 설정할 국가를 선택합니다.

3. **연락처 정보(선택 사항)를 제공합니다.** 연산자에 대한 추가 정보를 연산자에 문의하려는 경우 커넥트 확인란을 확인하고 연락처 정보를 제공합니다.  

4. **데이터 전송 알림에 동의합니다.**

5. **연산자를 추가합니다.** 저장할 **연산자로 추가를** 선택합니다.

## <a name="set-up-phone-numbers"></a>전화 번호 설정

전화 번호를 설정하는 방법은 새 사용자에 대한 번호를 설정하는지 또는 Microsoft 통화 계획 또는 직접 라우팅에서 기존 번호를 이동하는지 여부에 따라 결정됩니다.

- 새 사용자에 대한 전화 번호를 획득해야 하는 경우 새 사용자에 대한 Teams [참조합니다.](#acquire-numbers-for-new-teams-users)

- 기존 번호를 호출 계획에서 연산자로 이동하려는 커넥트 요금제에서 연산자로 번호 [이동을 커넥트.](#move-numbers-from-calling-plans-to-operator-connect)

- 기존 번호를 직접 라우팅에서 연산자로 이동하려는 커넥트 직접 라우팅에서 연산자로 번호 [이동을 커넥트.](#move-numbers-from-direct-routing-to-operator-connect)

>[!IMPORTANT]
>**긴급 주소:** 연산자에서 획득한 번호와 연결된 긴급 주소는 연산자와 직접 관리됩니다. 변경을 위해 운영자에게 문의해 주세요.

### <a name="acquire-numbers-for-new-teams-users"></a>새 사용자에 대한 Teams 획득

새 사용자에 대한 번호를 Teams 다음 단계를 수행합니다.

1. **라이선스를 전화 시스템 할당합니다.** 관리자 센터 또는 PowerShell을 전화 시스템 사용자에 Microsoft 365 라이선스를 할당할 수 있습니다. 자세한 내용은 사용자에게 Teams 추가 기능 라이선스 할당을 [참조하세요.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. **TeamsOnly 모드에 있는지 확인 합니다.** 확인하려면 Teams 관리 센터에서 업그레이드 에서 **org-wide 설정으로 > Teams 합니다.** 공존 모드는 Teams 설정해야 합니다.

3. **긴급 주소를 만들고 유효성을 검사합니다.** Teams 관리 센터에서 위치 > 주소로 이동하여 긴급 **주소를** 설정합니다. 자세한 내용은 조직의 응급 위치 추가, 변경 또는 [제거를 참조하세요.](add-change-remove-emergency-location-organization.md)

4. **숫자를 획득합니다.** 전화 번호를 주문하고 획득하기 위해 운영자의 웹 사이트로 이동하세요. 운영자 웹 사이트 목록은 [연산자 를 참조하세요.](#operators) 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 Microsoft 365 테넌트 [ID](/onedrive/find-your-office-365-tenant-id) 찾기를 참조하세요.

5. **숫자를 할당합니다.** 운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. Voice Teams 번호로 Teams 관리 센터에서 숫자 및 공급자를 볼 **> 전화 있습니다.** 관리자 센터를 Teams PowerShell을 사용하여 사용자에게 숫자를 할당합니다. 자세한 내용은 숫자 할당 [을 참조하세요.](#assign-numbers)
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>통화 계획에서 연산자로 번호 이동 커넥트

1. 연산자에 문의하여 번호를 연산자로 커넥트. 연산자를 [참조하여](#operators) 운영자의 웹 사이트를 찾을 수 있습니다.

2. 운영자가 포터링 순서를 완료한 후 사용자의 통화 계획 전화 번호의 선택을 제거하고 통화 계획 라이선스를 제거할 수 있습니다. 그런 다음 운영자는 테넌트에 번호를 업로드할 수 있습니다.

3. 관리자 커넥트 또는 PowerShell을 사용하여 Teams 사용자에 대한 연산자 번호 할당 자세한 내용은 숫자 할당 [을 참조하세요.](#assign-numbers)

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>직접 라우팅에서 연산자로 번호 이동 커넥트

1. 다음과 같이 사용자에서 기존 전화 번호를 제거합니다.  

   다음 PowerShell 명령을 실행하여 기존 On-prem Line URI를 얻게 됩니다.

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   다음 PowerShell 명령을 실행하여 On-prem Line URI를 제거합니다.  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. 사용자와 연결된 모든 PSTNUsage를 제거하고, 그렇지 않으면 호출이 PSTN 사용량에 지정된 게이트웨이로 라우팅됩니다. PSTN 사용량을 제거하는 방법에 대한 자세한 내용은 [Set-CsOnlinePstnUsage 를 참조합니다.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)

3. 전화 번호를 주문하고 획득하기 위해 운영자의 웹 사이트로 이동하세요. 운영자 웹 사이트 목록은 [연산자 를 참조하세요.](#operators) 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 Microsoft 365 테넌트 [ID](/onedrive/find-your-office-365-tenant-id) 찾기를 참조하세요.

4. 운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. Voice Teams 번호로 Teams 관리 센터에서 숫자 및 공급자를 볼 **> 전화 있습니다.** 관리자 커넥트 또는 PowerShell을 사용하여 Teams 사용자에 대한 연산자 번호 할당 자세한 내용은 숫자 할당 [을 참조하세요.](#assign-numbers)

   

### <a name="assign-numbers"></a>숫자 할당

새 사용자를 추가하거나 Teams 기존 사용자를 연산자로 커넥트 번호 할당 단계는 다음과 같습니다.

Teams 관리 센터를 사용하여 숫자를 할당하려면 전화 **로 이동하세요.** 단계는 통화 계획에 대한 번호를 할당하는 단계와 동일합니다. 자세한 내용은 사용자에게 전화 [번호 할당을 참조하세요.](assign-change-or-remove-a-phone-number-for-a-user.md)

PowerShell을 사용하여 숫자를 할당하기 위해 다음과 Set-CsOnlineVoiceUser cmdlet을 사용 합니다.

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

예를 들면 다음과 같습니다.

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

사용자에게 전화 번호를 할당하는 방법에 대한 자세한 내용은 사용자에 대한 전화 번호 할당, 변경 또는 [제거를 참조하세요.](assign-change-or-remove-a-phone-number-for-a-user.md)



## <a name="manage-your-operators"></a>운영자 관리

내 연산자 탭에서 연산자 및 해당 상태를 보고 선택 내용을 변경할 수 있습니다.  

- 국가에 의해 운영자 서비스 관리
- 연산자 일시 중단
- 연산자 제거

> [!NOTE]
> 조직 또는 국가에서 연산자를 제거하기 전에 조직 또는 국가의 사용자에게 할당된 모든 전화 번호를 제거하고 운영자에게 문의하여 번호를 해제해야 합니다.

## <a name="operators"></a>연산자

여기에 연결된 웹 사이트로 가면 다음 연산자에서 전화 번호를 획득할 수 있습니다.


|연산자  |운영자 웹 사이트  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
