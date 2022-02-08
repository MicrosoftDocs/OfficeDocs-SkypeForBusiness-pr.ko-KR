---
title: 연산자 커넥트
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 09/30/2021
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
ms.openlocfilehash: aa31a954bb36369417f408734fa3b1622e101e69
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384166"
---
# <a name="configure-operator-connect"></a>연산자 커넥트

이 문서에서는 연산자를 구성하는 커넥트. 연산자를 구성하기 전에 커넥트 및 라이선스에 대한 자세한 내용은 연산자 [](operator-connect-plan.md) 에 대한 커넥트 계획을 읽어야 합니다.

## <a name="enable-an-operator"></a>연산자 사용

관리 센터에서 연산자를 사용하도록 설정, 편집 및 Teams 수 있습니다. 왼쪽 탐색 창에서 **Voice > 연산자로 이동합니다**.

연산자를 사용하도록 설정하려면:

1. **연산자를 선택 합니다.** 모든 **연산자 탭에서** 지역 또는 서비스별로 사용 가능한 연산자를 필터링하여 음성 요구에 적합한 연산자를 찾습니다. 그런 다음 사용하려는 연산자를 선택합니다.  

2. **국가를 선택합니다.** 연산자 **설정에서** 선택한 연산자를 사용하여 사용하도록 설정할 국가를 선택합니다.

3. **연락처 정보 제공** 전체 이름 및 전자 메일 주소를 포함한 연락처 정보는 운영자와 자동으로 공유됩니다. 나중에 이 정보를 변경할 수 있습니다. 또한 회사 크기를 제공해야 합니다. 전화 번호를 제공할 수 있는 옵션이 있습니다. 운영자는 이 정보를 사용하여 연산자에 대한 자세한 정보를 커넥트.

4. 데이터 전송 알림에 동의합니다.

5. **연산자를 추가합니다.** 저장할 **연산자로 추가** 를 선택합니다.

## <a name="set-up-phone-numbers"></a>전화 번호 설정

전화 번호를 설정하는 방법은 새 사용자에 대한 번호를 설정하는지 또는 Microsoft 통화 계획 또는 직접 라우팅에서 기존 번호를 이동하는지 여부에 따라 결정됩니다.

- 새 사용자에 대한 전화 번호를 획득해야 하는 경우 새 사용자에 [대한 번호 Teams 참조합니다](#acquire-numbers-for-new-teams-users).

- 기존 번호를 호출 계획에서 연산자로 이동하려는 커넥트 통화 요금제에서 연산자로 번호 이동을 [커넥트](#move-numbers-from-calling-plans-to-operator-connect).

- 기존 번호를 직접 라우팅에서 연산자로 이동하려는 커넥트 직접 라우팅에서 연산자로 번호 [이동을 커넥트](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>새 사용자에 대한 Teams 획득

새 사용자에 대한 번호를 Teams 다음 단계를 수행합니다.

1. **라이선스를 전화 시스템 할당합니다.** PowerShell을 사용하여 전화 시스템 사용자에 Microsoft 365 관리 센터 수 있습니다. 자세한 내용은 사용자에게 Teams 추가 기능 라이선스 할당을 [참조하세요](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. 연산자를 통해 획득한 전화 번호가 할당되는 커넥트 TeamsOnly 모드로 전환해야 합니다. 조직이 TeamsOnly 모드인 경우 모든 사용자가 TeamsOnly 모드에 있습니다. 이 확인을 확인하려면 Teams 관리 센터에서 업그레이드 Teams > Teams **이동합니다**. 조직이 제도 모드인 경우 특정 사용자가 TeamsOnly 모드에 있는지 검사합니다. 사용자 **로 이동하여** 사용자 계정을 선택합니다. 계정 탭 **에서** 업그레이드 Teams 'TeamsOnly'로 공존 모드를 설정해야 합니다.

3. **숫자를 획득합니다.** 전화 번호를 주문하고 획득하기 위해 운영자의 웹 사이트로 이동하세요. 운영자 웹 사이트 목록은 운영자 Microsoft 365 [디렉터리로 커넥트 합니다](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 Microsoft 365 테넌트 [ID](/onedrive/find-your-office-365-tenant-id) 찾기를 참조하세요.

4. **숫자를 할당합니다.** 운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. Voice Teams 번호로 Teams 관리 센터에서 숫자 **및 공급자를 볼 > 전화 있습니다**. 관리자 센터에서 또는 PowerShell을 Teams 사용자에게 번호를 할당합니다. 자세한 내용은 숫자 [할당을 참조하세요](#assign-numbers).

> [!NOTE]
> 사용자에 대한 [](getting-phone-numbers-for-your-users.md) 전화 번호 외에도 오디오 회의(전화 회의용), 자동 참석자 및 통화 큐(서비스 번호라고도 하는)와 같은 서비스에 대한 전화 번호 또는 무료 전화 번호를 얻을 수 있습니다. 서비스 전화 번호는 사용자 또는 구독자 전화 번호보다 더 높은 동시 통화 용량을 습니다. 예를 들어 서비스 번호는 수백 개의 통화를 동시에 처리할 수 있는 반면, 사용자의 전화 번호는 몇 개의 호출만 동시에 처리할 수 있습니다. 서비스 번호를 얻지 못하면 운영자에게 문의합니다.

### <a name="emergency-addresses"></a>긴급 주소

긴급 주소는 숫자와 연결된 정적 위치입니다. 관리 센터에서 Teams 주소를 지정하거나 나중에 변경하는 방법은 운영자에 따라 달라 지는 것입니다.

긴급 주소에 번호를 할당하기 위해 운영자는 다음 세 가지 시나리오 중 하나를 구현합니다.

- 운영자는 전화 번호에 긴급 주소를 할당하고 나중에 관리 센터에서 Teams 수 있습니다.

- 운영자는 주소를 할당하지 않습니다. 관리 센터의 전화 번호에 긴급 주소를 Teams 수 있습니다.

- 운영자는 전화 번호에 긴급 주소를 할당하고 변경할 수 없습니다. 이 시나리오에서는 전화 번호 및 할당된 긴급 주소를 변경하려면 운영자에게 문의해야 합니다.

긴급 통화에 대한 자세한 [내용은 긴급 통화](what-are-emergency-locations-addresses-and-call-routing.md) 관리 및 계획 및 동적 긴급 통화 [구성을 참조하세요](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>통화 계획에서 연산자로 번호 이동 커넥트

1. 연산자에 문의하여 번호를 연산자로 커넥트. 운영[자의 Microsoft 365 커넥트 디렉터리](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)를 참조하세요.

2. 운영자가 포터링 순서를 완료한 후 사용자의 통화 계획 전화 번호의 선택을 제거하고 통화 계획 라이선스를 제거할 수 있습니다. 그런 다음 운영자는 테넌트에 번호를 업로드할 수 있습니다.

3. 관리자 커넥트 또는 PowerShell을 사용하여 Teams 사용자에 대한 연산자 번호 할당 자세한 내용은 숫자 [할당을 참조하세요](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>직접 라우팅에서 연산자로 번호 이동 커넥트

직접 라우팅에서 연산자로 번호를 커넥트 연산자에 의해 테넌트에 업로드된 기존 직접 라우팅 번호는 할당된 사용자에서 제거해야 합니다. 그런 다음 연산자로 번호가 마이그레이션된 커넥트 사용자에게 번호를 다시 할당할 수 있습니다. 직접 라우팅에서 운영자 커넥트 온라인 전화 번호로 이동하는 경우 아래 단계를 따릅니다.

>[!IMPORTANT]
> 마이그레이션하는 동안 전화 번호가 서비스가 제공되지 않습니다. 따라서 시작하기 전에 운영자 커넥트 운영자와 조정합니다.

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>1단계 - 기존 직접 라우팅 번호를 제거합니다.

기존 직접 라우팅 번호를 제거하는 방법은 번호가온-프레미스 또는 온라인에 할당되어 있는지 여부에 따라 결정됩니다. 확인을 위해 다음 명령을 실행합니다.
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```

`OnPremLineUriManuallySet` `False` `LineUri` E.164 전화 번호로 설정되어 있는 경우 전화 번호가 프레미스에 할당되어 전화 번호로 Office 365.
    
**프레미스에** 할당된 직접 라우팅 번호를 제거하려면 다음 명령을 실행합니다.
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

제거가 적용되는 데 걸리는 시간은 구성에 따라 다릅니다. 프레미스 번호가 제거되고 변경 내용이 동기화되어 있는지 확인을 위해 다음 PowerShell 명령을 실행합니다. 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```
       
변경 내용이 온라인 디렉터리에 동기화된 Office 365 예상 출력은 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
 OnPremLineURIManuallySet             : True
 OnPremLineURI                        : 
LineURI                              : 
```

<br> **온라인에 할당된 기존 온라인 직접** 라우팅 번호를 제거하려면 다음 PowerShell 명령을 실행합니다.


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

전화 번호를 제거하는 데 최대 10분이 걸릴 수 있습니다. 드문 경우로 최대 24시간이 걸릴 수 있습니다. 프레미스 번호가 제거되고 변경 내용이 동기화되어 있는지 확인을 위해 다음 PowerShell 명령을 실행합니다. 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl Number
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>2단계 - 사용자와 연결된 온라인 음성 라우팅 정책 제거

번호가 선택되지 않은 경우 다음 PowerShell 명령을 실행하여 사용자와 연결된 온라인 음성 라우팅 정책을 제거합니다.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>3단계 - 전화 번호 획득

전화 번호를 주문하고 획득하기 위해 운영자의 웹 사이트로 이동하세요. 운영자 웹 사이트를 찾으신 경우 운영자 Microsoft 365 [디렉터리를 커넥트 참조하세요](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 Microsoft 365 테넌트 [ID](/onedrive/find-your-office-365-tenant-id) 찾기를 참조하세요.

#### <a name="step-4---assign-phone-numbers"></a>4단계 - 전화 번호 할당

운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. Voice Teams 번호로 Teams 관리 센터에서 숫자 **및 공급자를 볼 > 전화 있습니다**. 관리자 커넥트 또는 PowerShell을 사용하여 Teams 사용자에 대한 연산자 번호 할당 자세한 내용은 숫자 [할당을 참조하세요](#assign-numbers).

### <a name="assign-numbers"></a>숫자 할당

사용자에게 전화 번호를 할당하는 방법에 대한 자세한 내용은 사용자에 대한 전화 번호 할당, 변경 또는 제거 [를 참조하세요](assign-change-or-remove-a-phone-number-for-a-user.md).

## <a name="manage-your-operators"></a>운영자 관리

내 연산자 **탭에서** 연산자 및 해당 상태를 보고 선택 내용을 변경할 수 있습니다.  

- 국가에 의해 운영자 서비스 관리
- 연산자 일시 중단
- 연산자 제거

> [!NOTE]
> 조직 또는 국가에서 연산자를 제거하기 전에 조직 또는 국가의 사용자에게 할당된 모든 전화 번호를 제거하고 운영자에게 문의하여 번호를 해제해야 합니다.

## <a name="release-numbers"></a>릴리스 번호

관리 센터에서 전화 Teams 해제하려면 전화 페이지로 이동하고 번호를 선택합니다.

- 사용자에게 전화 번호가 할당되지 않은 경우 릴리스를 **선택합니다**.

- 전화 번호가 사용자에게 할당된 경우 번호 할당을 해지해야 합니다. 편집 **을** 선택한 다음 사용자 **제거를 선택합니다**. 변경 내용을 저장한 후 릴리스를 **선택합니다**.

## <a name="related-topics"></a>관련 항목

- [자동 Teams 큐에 대한 계획](plan-auto-attendant-call-queue.md)
