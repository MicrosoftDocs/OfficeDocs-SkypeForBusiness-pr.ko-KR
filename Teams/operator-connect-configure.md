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
ms.openlocfilehash: 32745682712261b6fe88f4735a1b54974c440a39
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045924"
---
# <a name="configure-operator-connect"></a>연산자 커넥트

이 문서에서는 연산자를 구성하는 커넥트. 연산자 커넥트 구성하기 전에 연산자에 대한 [](operator-connect-plan.md) 계획을 커넥트 및 라이선스에 대한 정보를 읽어야 합니다.

## <a name="enable-an-operator"></a>연산자 사용

관리 센터에서 연산자를 사용하도록 설정, 편집 및 Teams 수 있습니다. 왼쪽 탐색 창에서 Voice **> 연산자로 이동합니다.**

연산자를 사용하도록 설정하려면:

1. **연산자를 선택 합니다.** 모든 **연산자 탭에서** 지역 또는 서비스별로 사용 가능한 연산자를 필터링하여 음성 요구에 적합한 연산자를 찾습니다. 그런 다음 사용하려는 연산자를 선택합니다.  

2. **국가를 선택합니다.** 연산자 **설정에서** 선택한 연산자를 사용하여 사용하도록 설정할 국가를 선택합니다.

3. **연락처 정보 제공** 전체 이름 및 전자 메일 주소를 포함한 연락처 정보는 운영자와 자동으로 공유됩니다. 나중에 이 정보를 변경할 수 있습니다. 또한 회사 크기를 제공해야 합니다. 전화 번호를 제공할 수 있는 옵션이 있습니다. 운영자는 이 정보를 사용하여 연산자에 대한 자세한 정보를 커넥트.

4. 데이터 전송 알림에 동의합니다.

5. **연산자를 추가합니다.** 저장할 **연산자로 추가를** 선택합니다.

## <a name="set-up-phone-numbers"></a>전화 번호 설정

전화 번호를 설정하는 방법은 새 사용자에 대한 번호를 설정하는지 또는 Microsoft 통화 계획 또는 직접 라우팅에서 기존 번호를 이동하는지 여부에 따라 결정됩니다.

- 새 사용자에 대한 전화 번호를 획득해야 하는 경우 새 사용자에 대한 Teams [참조합니다.](#acquire-numbers-for-new-teams-users)

- 기존 번호를 호출 계획에서 연산자로 이동하려는 커넥트 요금제에서 연산자로 번호 [이동을 커넥트.](#move-numbers-from-calling-plans-to-operator-connect)

- 기존 번호를 직접 라우팅에서 연산자로 이동하려는 커넥트 직접 라우팅에서 연산자로 번호 [이동을 커넥트.](#move-numbers-from-direct-routing-to-operator-connect)

### <a name="acquire-numbers-for-new-teams-users"></a>새 사용자에 대한 Teams 획득

새 사용자에 대한 번호를 Teams 다음 단계를 수행합니다.

1. **라이선스를 전화 시스템 할당합니다.** PowerShell을 사용하여 전화 시스템 사용자에 Microsoft 365 관리 센터 수 있습니다. 자세한 내용은 사용자에게 Teams 추가 기능 라이선스 할당을 [참조하세요.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. 연산자를 통해 획득한 전화 번호가 할당되는 커넥트 TeamsOnly 모드로 전환해야 합니다. 조직이 TeamsOnly 모드인 경우 모든 사용자가 TeamsOnly 모드에 있습니다. 이 확인을 확인하려면 Teams 관리 센터에서 업그레이드 에서 **org-wide 설정으로 > Teams 이동합니다.** 조직이 제도 모드인 경우 특정 사용자가 TeamsOnly 모드에 있는지 검사합니다. 사용자로 **이동하여** 사용자 계정을 선택합니다. 계정 **탭에서** 업그레이드  Teams 'TeamsOnly'로 공존 모드를 설정해야 합니다.

3. **숫자를 획득합니다.** 전화 번호를 주문하고 획득하기 위해 운영자의 웹 사이트로 이동하세요. 운영자 웹 사이트 목록은 Microsoft 365 운영자 커넥트 [로 이동하세요.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 Microsoft 365 테넌트 [ID](/onedrive/find-your-office-365-tenant-id) 찾기를 참조하세요.

4. **숫자를 할당합니다.** 운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. Voice Teams 번호로 Teams 관리 센터에서 숫자 및 공급자를 볼 **> 전화 있습니다.** 관리자 센터에서 또는 PowerShell을 Teams 사용자에게 번호를 할당합니다. 자세한 내용은 숫자 할당 [을 참조하세요.](#assign-numbers)

> [!NOTE]
> 사용자에 [](getting-phone-numbers-for-your-users.md)대한 전화 번호를 받을 뿐만 아니라 오디오 회의(전화 회의용), 자동 참석자 및 통화 큐(서비스 번호라고도 하는)와 같은 서비스에 대한 무료 전화 번호를 받을 수 있습니다. 서비스 전화 번호는 사용자 또는 구독자 전화 번호보다 더 높은 동시 통화 용량을 습니다. 예를 들어 서비스 번호는 수백 개의 통화를 동시에 처리할 수 있는 반면, 사용자의 전화 번호는 몇 개의 호출만 동시에 처리할 수 있습니다. 서비스 번호를 얻지 못하면 운영자에게 문의합니다.

### <a name="emergency-addresses"></a>긴급 주소

긴급 주소는 숫자와 연결된 정적 위치입니다. 관리 센터에서 Teams 주소를 지정하거나 나중에 변경하는 방법은 운영자에 따라 달라 지는 것입니다.

긴급 주소에 번호를 할당하기 위해 운영자는 다음 세 가지 시나리오 중 하나를 구현합니다.

- 운영자는 전화 번호에 긴급 주소를 할당하고 나중에 관리 센터에서 Teams 수 있습니다.

- 운영자는 주소를 할당하지 않습니다. 관리 센터의 전화 번호에 긴급 주소를 Teams 수 있습니다.

- 운영자는 전화 번호에 긴급 주소를 할당하고 변경할 수 없습니다. 이 시나리오에서는 전화 번호 및 할당된 긴급 주소를 변경하려면 운영자에게 문의해야 합니다.

긴급 통화에 대한 자세한 내용은 [긴급](what-are-emergency-locations-addresses-and-call-routing.md) 통화 관리 및 계획 및 동적 긴급 호출 [구성을 참조하세요.](configure-dynamic-emergency-calling.md)

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>통화 계획에서 연산자로 번호 이동 커넥트

1. 연산자에 문의하여 번호를 연산자로 커넥트. 운영자의 [Microsoft 365 커넥트 디렉터리를](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) 참조하세요.

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

3. 전화 번호를 주문하고 획득하기 위해 운영자의 웹 사이트로 이동하세요. 운영자 웹 사이트를 찾으신 경우 운영자 Microsoft 365 [디렉터리를 커넥트 참조하세요.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 Microsoft 365 테넌트 [ID](/onedrive/find-your-office-365-tenant-id) 찾기를 참조하세요.

4. 운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. Voice Teams 번호로 Teams 관리 센터에서 숫자 및 공급자를 볼 **> 전화 있습니다.** 관리자 커넥트 또는 PowerShell을 사용하여 Teams 사용자에 대한 연산자 번호 할당 자세한 내용은 숫자 할당 [을 참조하세요.](#assign-numbers)

### <a name="assign-numbers"></a>숫자 할당

사용자에게 전화 번호를 할당하는 방법에 대한 자세한 내용은 사용자에 대한 전화 번호 할당, 변경 또는 [제거를 참조하세요.](assign-change-or-remove-a-phone-number-for-a-user.md)

## <a name="manage-your-operators"></a>운영자 관리

내 연산자 **탭에서** 연산자 및 해당 상태를 보고 선택 내용을 변경할 수 있습니다.  

- 국가에 의해 운영자 서비스 관리
- 연산자 일시 중단
- 연산자 제거

> [!NOTE]
> 조직 또는 국가에서 연산자를 제거하기 전에 조직 또는 국가의 사용자에게 할당된 모든 전화 번호를 제거하고 운영자에게 문의하여 번호를 해제해야 합니다.

## <a name="release-numbers"></a>릴리스 번호

관리 센터에서 전화 Teams 해제하려면 전화 **페이지로** 이동하고 번호를 선택합니다.

- 사용자에게 전화 번호가 할당되지 않은 경우 릴리스 를 **선택합니다.**

- 전화 번호가 사용자에게 할당된 경우 번호 할당을 해지해야 합니다. 편집을 선택한 다음 **사용자 제거 를 선택합니다.**  변경 내용을 저장한 후 릴리스 를 **선택합니다.**

## <a name="related-topics"></a>관련 주제

- [자동 Teams 큐에 대한 계획](plan-auto-attendant-call-queue.md)
