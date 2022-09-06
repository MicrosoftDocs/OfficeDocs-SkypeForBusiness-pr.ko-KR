---
title: 운영자 연결 모바일 구성
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
ms.reviewer: crowe
search.appverid: MET150
description: 운영자 연결 모바일 구성하는 방법에 대해 자세히 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca49ac8cb74bcb61cd8c1d8fc2056c69a89d715
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606902"
---
# <a name="configure-operator-connect-mobile"></a>운영자 연결 모바일 구성

**운영자 연결 모바일 공개 미리 보기 릴리스입니다.** Microsoft 운영자 연결 모바일 프로그램에 참여하는 운영자 목록과 서비스를 사용할 수 있는 국가 또는 지역은 [Microsoft 365 운영자 연결 모바일](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/connect-mobile) 참조하세요.

이 문서에서는 운영자 연결 모바일 구성하는 방법을 설명합니다. 운영자 연결 모바일 구성하기 전에 혜택, 필수 구성 요소 및 라이선스[에 대한 정보는 운영자 연결 모바일 계획을](operator-connect-mobile-plan.md) 읽어야 합니다.

## <a name="enable-an-operator"></a>연산자 사용

Teams 관리 센터에서 운영자를 사용, 편집 및 제거할 수 있습니다. 왼쪽 탐색 창에서 **Voice > Operator** 로 이동합니다.

운영자를 사용하도록 설정하려면 다음을 수행합니다.

1. 운영자 연결 모바일 지원하는 연산자를 선택합니다. **모든 연산자** 탭에서 지역 또는 서비스별로 사용 가능한 연산자를 필터링하여 운영자 연결 모바일 지원하는 올바른 연산자를 찾습니다. 그런 다음, 사용하도록 설정할 연산자를 선택합니다.

2. **운영자 설정** 에서 선택한 연산자를 사용하여 사용하도록 설정할 국가를 선택합니다.

3. **연락처 정보를 제공합니다.** 전체 이름 및 전자 메일 주소를 포함한 연락처 정보는 운영자와 자동으로 공유됩니다. 나중에 이 정보를 변경할 수 있습니다. 또한 회사 크기를 제공해야 하며 전화 번호를 제공하는 옵션이 제공됩니다. 운영자는 이 정보를 사용하여 운영자 연결 모바일 대한 자세한 내용을 문의합니다.

4. 데이터 전송 알림을 수락합니다.

5. 저장할 **내 연산자로 추가** 를 선택합니다.

## <a name="set-up-phone-numbers"></a>전화 번호 설정

기존 회사 유료 SIM 사용 전화 번호를 Teams에 추가하려면 운영자에게 문의하여 적격 운영자 연결 모바일 구독이 있는지 확인하고 Teams에 번호를 업로드할 수 있습니다. 운영자가 주문을 완료한 후 해당 숫자를 사용자에게 할당할 수 있습니다. 

운영자의 웹 사이트를 찾으려면 [Microsoft 365 Operator Connect 디렉터리를 참조하세요](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 [Microsoft 365 테넌트 ID 찾기](/onedrive/find-your-office-365-tenant-id.md)를 참조하세요. 해당 지역 및 운영자가 지원하는 경우 기존 책상 전화 번호 또는 유선 번호를 무선 음성 구독으로 포팅할 수 있습니다. 

전화 번호를 설정하는 방법은 새 사용자에 대한 번호를 설정하는지 또는 Microsoft 통화 플랜, 운영자 연결 또는 직접 라우팅에서 기존 번호를 이동하는지에 따라 달라집니다.

- [새 Teams 사용자에 대한 숫자를 획득합니다](#acquire-numbers-for-new-teams-users).  

- [통화 플랜에서 운영자 연결 모바일 번호로 이동합니다](#move-numbers-from-calling-plans-to-operator-connect-mobile).  

- [연산자 연결에서 운영자 연결 모바일 숫자를 이동합니다](#move-numbers-from-operator-connect-to-operator-connect-mobile).  

- [직접 라우팅에서 운영자 연결 모바일 숫자를 이동합니다](#move-numbers-from-direct-routing-to-operator-connect-mobile).  


### <a name="assign-numbers-to-emergency-addresses"></a>긴급 주소에 번호 할당

긴급 주소는 Microsoft Teams 엔드포인트/클라이언트를 통해 액세스할 수 있는 경우 숫자와 연결된 정적 위치입니다. Teams 관리 센터에서 긴급 주소를 만들면 주소를 할당하거나 나중에 변경하는 방법은 운영자에 따라 달라집니다.

Microsoft Teams 엔드포인트에서 사용하는 긴급 주소에 숫자를 할당하기 위해 운영자는 다음 세 가지 시나리오 중 하나를 구현합니다.

- 운영자는 전화 번호에 긴급 주소를 할당하고 나중에 Teams 관리 센터에서 변경할 수 있습니다.

- 운영자는 주소를 할당하지 않으며 Teams 관리 센터의 전화 번호에 긴급 주소를 할당할 수 있습니다.

- 운영자는 전화 번호에 긴급 주소를 할당하며 변경할 수 없습니다. 이 시나리오에서는 전화 번호 및 할당된 긴급 주소를 변경하려면 운영자에게 문의해야 합니다.

SIM 지원 스마트폰의 네이티브 다이얼러를 통해 전화를 걸면 운영자는 지리 좌표 또는 셀 타워를 사용하여 긴급 위치를 대략적인 긴급 위치로 처리하여 도움을 받을 수 있습니다.

긴급 통화에 대한 자세한 내용은 [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md) 및 [동적 긴급 통화 계획 및 구성](configure-dynamic-emergency-calling.md)을 참조하세요.

### <a name="acquire-numbers-for-new-teams-users"></a>새 Teams 사용자에 대한 번호 획득

새 Teams 사용자에 대한 숫자를 확보하려면 다음 단계를 수행합니다.

1. **전화 시스템 라이선스 및 운영자 연결 모바일 추가 기능 라이선스를 할당합니다.** Microsoft 365 관리 센터 또는 PowerShell을 사용하여 사용자에게 전화 시스템 라이선스 및 운영자 연결 모바일 추가 기능 라이선스를 할당할 수 있습니다. 자세한 내용은 [사용자에게 Teams 추가 기능 라이선스 할당을 참조하세요](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **운영자 연결 모바일 사용하여 획득한 전화 번호가 할당되는 사용자는 TeamsOnly 모드에 있어야 합니다.** 조직이 TeamsOnly 모드인 경우 모든 사용자가 TeamsOnly 모드에 있습니다. 

   확인하려면 Teams 관리 센터에서 **Teams > Teams 업그레이드 설정** 으로 이동합니다. 조직이 아일랜드 모드인 경우 특정 사용자가 TeamsOnly 모드에 있는지 확인합니다. **사용자** 로 이동하여 사용자 계정을 선택합니다. **계정** 탭의 **Teams 업그레이드** 에서 공존 모드를 'TeamsOnly'로 설정해야 합니다.

3. **숫자를 획득합니다.** 운영자의 웹 사이트로 이동하거나 문의하여 운영자 연결 모바일 서비스를 사용하도록 설정된 모바일 SIM 지원 전화 번호를 주문하고 가져옵니다. 

   운영자가 주문을 완료하면 SIM 지원 휴대폰 번호를 테넌트에 업로드합니다. **음성 > 전화 번호** 로 이동하여 Teams 관리 센터에서 번호와 공급자를 볼 수 있습니다. 

4. **숫자를 할당합니다.** Teams 관리 센터에서 또는 PowerShell을 사용하여 사용자에게 숫자를 할당할 수 있습니다. 자세한 내용은 [숫자 할당을 참조하세요](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect-mobile"></a>통화 플랜에서 운영자 연결 모바일 번호 이동

1. 운영자 연결 모바일 및 운영자 연결 모바일 추가 기능 라이선스에 적합한 Microsoft 365 구독이 있는지 확인합니다. [각 사용자에 대해 이동할 전화 번호를 제거해야 합니다](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). 

2. SIM 사용이 가능한 적격 무선 음성 요금제에서 운영자 연결 모바일 번호를 포트하려면 운영자에게 문의하세요. 

3. 운영자가 포팅 순서를 완료하면 운영자가 테넌트에 숫자를 업로드합니다.  **음성 > 전화 번호** 로 이동하여 Teams 관리 센터에서 번호와 공급자를 볼 수 있습니다. 

4. Teams 관리 센터를 사용하거나 PowerShell을 사용하여 사용자에게 숫자를 할당할 수 있습니다. 자세한 내용은 [숫자 할당을 참조하세요](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-operator-connect-to-operator-connect-mobile"></a>Operator Connect에서 운영자 연결 모바일 번호 이동

1. 운영자 연결 모바일 및 Operator Connect 추가 기능 라이선스에 적합한 Microsoft 365 구독이 있는지 확인합니다. [각 사용자에 대해 이동할 전화 번호를 제거해야 합니다](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). 기존 운영자 연결 공급자에게 문의하여 테넌트에서 전화 번호를 제거합니다.

2. SIM 사용이 가능한 적격 무선 음성 요금제에서 운영자 연결 모바일 번호를 포트하려면 운영자에게 문의하세요. 

3. 운영자가 포팅 순서를 완료하면 운영자가 테넌트에 숫자를 업로드합니다. **음성 > 전화 번호** 로 이동하여 Teams 관리 센터에서 번호와 공급자를 볼 수 있습니다. 

4. Teams 관리 센터를 사용하거나 PowerShell을 사용하여 사용자에게 숫자를 할당할 수 있습니다. 자세한 내용은 [숫자 할당을 참조하세요](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-direct-routing-to-operator-connect-mobile"></a>직접 라우팅에서 운영자 연결 모바일 번호 이동   

직접 라우팅에서 운영자 연결 모바일 숫자를 이동하려면 다음 단계를 완료해야 합니다.

1. [기존 직접 라우팅 번호가 온라인 또는 온-프레미스에 할당되었는지 확인합니다](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises).

2. [직접 라우팅에서 운영자 연결 모바일 숫자를 마이그레이션합니다](#migrate-the-numbers-from-direct-routing-to-operator-connect-mobile).

2. [사용자와 연결된 온라인 음성 라우팅 정책을 제거합니다](#remove-the-online-voice-routing-policy-associated-with-your-user).

3. [전화 번호를 획득합니다](#acquire-phone-numbers).

4. [전화 번호를 할당합니다](#assign-phone-numbers).

이러한 단계는 다음 섹션에서 자세히 설명합니다.

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>기존 직접 라우팅 번호가 온라인 또는 온-프레미스에 할당되었는지 확인합니다.

기존 직접 라우팅 번호를 제거하는 방법은 숫자가 온-프레미스 또는 온라인인지에 따라 달라집니다.

1. 먼저 다음 Teams PowerShell 명령을 실행하여 사용자에게 직접 라우팅 번호가 할당되어 있는지 확인합니다. NumberType은 DirectRouting이어야 합니다.

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. 다음 Teams PowerShell 명령을 실행하여 번호가 온라인 또는 온-프레미스에 할당되는지 확인합니다.

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   OnPremLineUri가 E.164 전화 번호로 채워지면 전화 번호가 온-프레미스에 할당되고 Microsoft 365와 동기화됩니다.

#### <a name="migrate-the-numbers-from-direct-routing-to-operator-connect-mobile"></a>직접 라우팅에서 운영자 연결 모바일 숫자 마이그레이션

숫자를 마이그레이션하려면 아래 단계를 수행합니다.  

> [!Important]
> 마이그레이션하는 동안 전화 번호가 서비스가 중단됩니다. 마이그레이션을 시작하기 전에 Operator Connect 연산자를 조정합니다.

- **온라인으로 할당된 기존 직접 라우팅 번호를 운영자 연결 모바일 마이그레이션하려면 운영자에게** 문의하세요. 운영자의 웹 사이트를 찾으려면 [Microsoft 365 Operator Connect 디렉터리를 참조하세요](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). 합의된 날짜 및 시간에 운영자는 직접 라우팅에서 운영자 연결 모바일 번호로 마이그레이션합니다. 여기에는 테넌트에서 마이그레이션되는 전화 번호를 제거하고 운영자 연결 모바일 연결된 새 전화 번호로 다시 추가하는 작업이 포함될 수 있습니다.

- **온-프레미스에 할당된 직접 라우팅 번호를 운영자 연결 모바일 마이그레이션하려면** 다음 비즈니스용 Skype 서버 PowerShell 명령을 실행합니다.

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  온-프레미스 번호가 제거되고 변경 내용이 온-프레미스에서 Microsoft 365로 동기화되었는지 확인하려면 다음 Teams PowerShell 명령을 실행합니다.

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

변경 내용이 Microsoft 365 온라인 디렉터리에 동기화된 후 예상되는 출력은 다음과 같습니다.

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

전화 번호가 제거되었는지 확인하려면 다음 Teams PowerShell 명령을 실행합니다.

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> 제거가 적용되는 데 걸리는 시간은 구성에 따라 달라집니다. 전화 번호를 제거하는 데는 최대 10분이 걸릴 수 있으며, 드문 경우는 최대 24시간이 걸릴 수 있습니다. 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>사용자와 연결된 온라인 음성 라우팅 정책 제거

번호가 할당되지 않은 후 다음 Teams PowerShell 명령을 실행하여 사용자와 연결된 온라인 음성 라우팅 정책을 제거합니다.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>전화번호 받기

SIM 사용이 가능한 적격 무선 음성 요금제에서 운영자 연결 모바일 번호를 포트하려면 운영자에게 문의하세요.

운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. **음성 > 전화 번호** 로 이동하여 Teams 관리 센터에서 번호와 공급자를 볼 수 있습니다. 

#### <a name="assign-phone-numbers"></a>전화 번호 할당

Teams 관리 센터를 사용하거나 PowerShell을 사용하여 사용자에게 Operator Connect 번호를 할당할 수 있습니다. 자세한 내용은 [숫자 할당을 참조하세요](assign-change-or-remove-a-phone-number-for-a-user.md).


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

## <a name="manage-user-incoming-calling-policies"></a>사용자 수신 통화 정책 관리

Teams 관리 센터를 사용하거나 PowerShell을 사용하여 사용자의 수신 통화 정책을 관리할 수 있습니다. 기본적으로 운영자 연결 모바일 사용자에 대한 수신 호출은 사용자의 SIM 사용 모바일 디바이스에서 Teams 앱을 먼저 울릴 것입니다. 

- 사용자의 수신 통화 기본 설정이 Teams 앱으로 설정된 경우 들어오는 모든 통화는 SIM 지원 스마트폰의 Teams 앱과 다른 장치의 다른 Teams 엔드포인트를 동시에 울릴 것입니다. 

- 사용자의 수신 통화 기본 설정이 네이티브 다이얼러로 설정된 경우 들어오는 모든 통화는 SIM 지원 스마트폰에서 네이티브 다이얼러를 울리고 다른 장치의 다른 모든 Teams 엔드포인트를 동시에 울립니다. 

### <a name="use-the-teams-admin-center"></a>Teams 관리 센터 사용

Teams 관리 센터를 사용하여 사용자의 수신 통화 정책을 관리하려면 다음을 수행합니다.

1. 음성 탭에서 **모바일 정책을** 선택합니다. 

2. 새 모바일 정책을 추가하려면 **추가** 를 클릭합니다.

3. 이름을 선택하고 정책에 대한 설명을 추가하고 **모바일 전화 걸기** 드롭다운 선택 옵션에서 다음 중 하나를 선택합니다.

   -  **Microsoft Teams** 는 SIM 지원 스마트폰에서 Teams 앱을 먼저 울릴 수 있습니다. 

   - **네이티브 다이얼러는** 먼저 SIM 지원 스마트 폰에 네이티브 다이얼러를 울리는.

4. 사용자에게 정책을 할당합니다. [정책 할당](assign-policies-users-and-groups.md)을 참조하세요.


### <a name="use-powershell"></a>PowerShell 사용

1. 테넌트에 연결: Connect-MicrosoftTeams.
 
2. 네이티브 다이얼러 또는 Teams 앱을 먼저 울리기 위한 수신 호출에 대한 정책을 만듭니다. (정책 이름을 선택할 수 있습니다. 이 예제에서는 TeamsFirst 및 NativeFirst를 사용합니다.) 

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. 사용자에게 정책 부여: 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. 사용자 정책 확인: 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. 모든 모바일 정책 옵션을 확인합니다. 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








