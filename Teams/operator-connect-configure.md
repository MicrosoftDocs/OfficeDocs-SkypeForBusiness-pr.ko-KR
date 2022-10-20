---
title: 연산자 연결 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Operator Connect를 구성하는 방법에 대해 자세히 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03fa1900986b12925e2f611e2d6553d9e5d627f8
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613870"
---
# <a name="configure-operator-connect"></a>연산자 연결 구성

이 문서에서는 Operator Connect를 구성하는 방법을 설명합니다. Operator Connect를 구성하기 전에 필수 구성 요소 및 라이선스 [에 대한 자세한 내용은 Operator Connect에 대한 계획을](operator-connect-plan.md) 읽어보세요.

## <a name="enable-an-operator"></a>연산자 사용

Teams 관리 센터에서 운영자를 사용, 편집 및 제거할 수 있습니다. 왼쪽 탐색 창에서 **Voice > Operator** 로 이동합니다.

운영자를 사용하도록 설정하려면 다음을 수행합니다.

1. **연산자를 선택합니다.** **모든 연산자** 탭에서 지역 또는 서비스별로 사용 가능한 연산자를 필터링하여 음성 요구 사항에 적합한 연산자를 찾습니다. 그런 다음, 사용하도록 설정할 연산자를 선택합니다.  

2. **국가를 선택합니다.** **운영자 설정** 에서 선택한 연산자를 사용하여 사용하도록 설정할 국가를 선택합니다.

3. **연락처 정보 제공** 전체 이름 및 전자 메일 주소를 포함한 연락처 정보는 운영자와 자동으로 공유됩니다. 나중에 이 정보를 변경할 수 있습니다. 또한 회사 크기를 제공해야 하며 전화 번호를 제공하는 옵션이 제공됩니다. 운영자는 이 정보를 사용하여 Operator Connect에 대한 자세한 내용을 문의합니다.

4. 데이터 전송 알림을 수락합니다.

5. **운영자를 추가합니다.** 저장할 **내 연산자로 추가** 를 선택합니다.

## <a name="set-up-phone-numbers"></a>전화 번호 설정

전화 번호를 설정하는 방법은 새 사용자에 대한 번호를 설정하는지 또는 Microsoft 통화 플랜 또는 직접 라우팅에서 기존 번호를 이동하는지에 따라 달라집니다.

- 새 사용자의 전화 번호를 획득해야 하는 경우 [새 Teams 사용자의 번호 획득을](#acquire-numbers-for-new-teams-users) 참조하세요.

- 기존 숫자를 통화 계획에서 운영자 연결로 이동하려면 [통화 플랜에서 운영자 연결로 번호 이동을](#move-numbers-from-calling-plans-to-operator-connect) 참조하세요.

- 기존 숫자를 직접 라우팅에서 운영자 연결로 이동하려면 [직접 라우팅에서 운영자 연결로 번호 이동을](#move-numbers-from-direct-routing-to-operator-connect) 참조하세요.

### <a name="assign-numberes-to-emergency-addresses"></a>긴급 주소에 번호 할당

긴급 주소는 숫자와 연결된 정적 위치입니다. Teams 관리 센터에서 긴급 주소를 만들면 주소를 할당하거나 나중에 변경하는 방법은 운영자에 따라 달라집니다.

긴급 주소에 숫자를 할당하기 위해 운영자는 세 가지 시나리오 중 하나를 구현합니다.

- 운영자는 전화 번호에 긴급 주소를 할당하고 나중에 Teams 관리 센터에서 변경할 수 있습니다.

- 운영자는 주소를 할당하지 않으며 Teams 관리 센터의 전화 번호에 긴급 주소를 할당할 수 있습니다.

- 운영자는 전화 번호에 긴급 주소를 할당하며 변경할 수 없습니다. 이 시나리오에서는 전화 번호 및 할당된 긴급 주소를 변경하려면 운영자에게 문의해야 합니다.

긴급 통화에 대한 자세한 내용은 [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md) 및 [동적 긴급 통화 계획 및 구성](configure-dynamic-emergency-calling.md)을 참조하세요.

### <a name="acquire-numbers-for-new-teams-users"></a>새 Teams 사용자에 대한 번호 획득

새 Teams 사용자에 대한 숫자를 확보하려면 다음 단계를 수행합니다.

1. **전화 시스템 라이선스를 할당합니다.** Microsoft 365 관리 센터 또는 PowerShell을 사용하여 사용자에게 전화 시스템 라이선스를 할당할 수 있습니다. 자세한 내용은 [사용자에게 Teams 추가 기능 라이선스 할당을 참조하세요](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Operator Connect를 사용하여 획득한 전화 번호가 할당되는 사용자는 TeamsOnly 모드여야 합니다. 조직이 TeamsOnly 모드인 경우 모든 사용자가 TeamsOnly 모드에 있습니다. 이를 확인하려면 Teams 관리 센터에서 **Teams > Teams 업그레이드 설정** 으로 이동합니다. 조직이 아일랜드 모드인 경우 특정 사용자가 TeamsOnly 모드에 있는지 확인합니다. **사용자** 로 이동하여 사용자 계정을 선택합니다. **계정** 탭의 **Teams 업그레이드** 에서 공존 모드를 'TeamsOnly'로 설정해야 합니다.

3. **숫자를 획득합니다.** 운영자의 웹 사이트로 이동하여 전화 번호를 주문하고 가져옵니다. 운영자 웹 사이트 목록은 [Microsoft 365 Operator Connect 디렉터리](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)로 이동합니다. 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 [Microsoft 365 테넌트 ID 찾기](/onedrive/find-your-office-365-tenant-id) 를 참조하세요.

4. **숫자를 할당합니다.** 운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. **음성 > 전화 번호** 로 이동하여 Teams 관리 센터에서 번호와 공급자를 볼 수 있습니다. Teams 관리 센터에서 또는 PowerShell을 사용하여 사용자에게 번호를 할당합니다. 자세한 내용은 [숫자 할당을 참조하세요](#assign-numbers).

> [!NOTE]
> [사용자의 전화 번호를 받는](getting-phone-numbers-for-your-users.md) 것 외에도 오디오 회의(회의 브리지), 자동 전화 교환 및 통화 큐(서비스 번호라고도 함)와 같은 서비스에 대한 유료 또는 무료 전화 번호를 받을 수 있습니다. 서비스 전화 번호는 사용자 또는 구독자 전화 번호보다 동시 통화 용량이 높습니다. 예를 들어 서비스 번호는 수백 건의 통화를 동시에 처리할 수 있는 반면, 사용자의 전화 번호는 몇 개의 통화만 동시에 처리할 수 있습니다. 서비스 번호를 얻으려면 운영자에게 문의하세요.

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>통화 플랜에서 운영자 연결로 번호 이동

1. 운영자에게 문의하여 번호를 Operator Connect로 이식합니다. 운영자의 웹 사이트를 찾으려면 [Microsoft 365 Operator Connect 디렉터리를](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) 참조하세요.

2. 운영자가 포팅 순서를 완료하면 운영자가 테넌트에 숫자를 업로드합니다.

3. Teams 관리 센터를 사용하거나 PowerShell을 사용하여 사용자에게 Operator Connect 번호를 할당합니다. 자세한 내용은 [숫자 할당을 참조하세요](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>직접 라우팅에서 운영자 연결로 숫자 이동

온-프레미스 또는 온라인 전화 번호를 사용하여 직접 라우팅에서 운영자 연결로 이동하려면 다음 단계를 수행합니다.

#### <a name="step-1---identify-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>1단계 - 기존 직접 라우팅 번호가 온라인 또는 온-프레미스에 할당되었는지 식별합니다.

Teams PowerShell 모듈 명령을 실행하여 사용자에게 직접 라우팅 번호가 할당되어 있는지 확인합니다.

```PowerShell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
```

DirectRouting인지 `NumberType` 확인합니다.

기존 직접 라우팅 번호를 제거하는 방법은 숫자가 온-프레미스 또는 온라인인지에 따라 달라집니다. 확인하려면 다음 Teams PowerShell 모듈 명령을 실행합니다.
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

E.164 전화 번호로 채워진 경우 `OnPremLineUri` 전화 번호가 온-프레미스에 할당되고 Microsoft 365와 동기화됩니다.

**온라인으로 할당된 기존 직접 라우팅 번호를 Operator Connect로 마이그레이션하려면 운영자에게** 문의하세요. 운영자의 웹 사이트를 찾으려면 [Microsoft 365 Operator Connect 디렉터리를 참조하세요](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). 합의된 날짜 및 시간에 운영자는 직접 라우팅에서 운영자 연결로 숫자를 마이그레이션합니다.

**온-프레미스에 할당된 직접 라우팅 번호를 Operator Connect로 마이그레이션하려면** 다음 비즈니스용 Skype 서버 PowerShell 명령을 실행합니다.
>[!IMPORTANT]
> 마이그레이션 중에 전화 번호가 서비스가 중단되므로 시작하기 전에 Operator Connect 운영자와 조정합니다.

```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

제거가 적용되는 데 걸리는 시간은 구성에 따라 달라집니다. 온-프레미스 번호가 제거되고 변경 내용이 온-프레미스에서 Microsoft 365로 동기화되었는지 확인하려면 다음 Teams PowerShell 모듈 명령을 실행합니다. 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
변경 내용이 Microsoft 365 온라인 디렉터리에 동기화된 후 예상되는 출력은 다음과 같습니다. 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```




```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

전화 번호를 제거하는 데 최대 10분이 걸릴 수 있습니다. 드문 경우이지만 최대 24시간이 걸릴 수 있습니다. 전화 번호가 제거되었는지 확인하려면 다음 Teams PowerShell 모듈 명령을 실행합니다. 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>2단계 - 사용자와 연결된 온라인 음성 라우팅 정책 제거

번호가 할당되지 않으면 다음 Teams PowerShell 모듈 명령을 실행하여 사용자와 연결된 온라인 음성 라우팅 정책을 제거합니다.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>3단계 - 전화 번호 가져오기

운영자의 웹 사이트로 이동하여 전화 번호를 주문하고 가져옵니다. 운영자 웹 사이트를 찾으려면 [Microsoft 365 Operator Connect 디렉터리를 참조하세요](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 자세한 내용은 [Microsoft 365 테넌트 ID 찾기](/onedrive/find-your-office-365-tenant-id) 를 참조하세요.

#### <a name="step-4---assign-phone-numbers"></a>4단계 - 전화 번호 할당

운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. **음성 > 전화 번호** 로 이동하여 Teams 관리 센터에서 번호와 공급자를 볼 수 있습니다. Teams 관리 센터를 사용하거나 PowerShell을 사용하여 사용자에게 Operator Connect 번호를 할당합니다. 자세한 내용은 [숫자 할당을 참조하세요](#assign-numbers).

### <a name="assign-numbers"></a>숫자 할당

사용자에게 전화 번호를 할당하는 방법에 대한 자세한 내용은 사용자의 [전화 번호 할당, 변경 또는 제거를](assign-change-or-remove-a-phone-number-for-a-user.md) 참조하세요.

## <a name="manage-your-operators"></a>연산자 관리

**내 연산자** 탭에서 연산자와 해당 상태를 보고 선택 항목을 다음과 같이 변경할 수 있습니다.  

- 국가별 운영자 서비스 관리
- 연산자 일시 중단
- 연산자 제거

> [!NOTE]
> 조직 또는 국가에서 운영자를 제거하기 전에 조직 또는 국가의 사용자에게 할당된 모든 전화 번호를 제거하고 운영자에게 연락하여 번호를 해제해야 합니다.

## <a name="release-numbers"></a>릴리스 번호

Teams 관리 센터에서 전화 번호를 해제하려면 **전화 번호** 페이지로 이동하여 번호를 선택합니다.

- 사용자에게 전화 번호가 할당되지 않은 경우 **릴리스** 를 선택합니다.

- 사용자에게 전화 번호가 할당된 경우 번호를 할당 취소해야 합니다. **편집** 을 선택한 다음 **, 사용자를 제거합니다**. 변경 내용을 저장한 후 **릴리스** 를 선택합니다.

## <a name="related-topics"></a>관련 주제

- [Teams 자동 전화 교환 및 통화 큐 계획](plan-auto-attendant-call-queue.md)
