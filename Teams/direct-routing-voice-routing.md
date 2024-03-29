---
title: 직접 라우팅에 대한 호출 라우팅 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft 직접 라우팅을 사용하여 통화 라우팅을 구성하는 방법을 알아봅니다.
ms.openlocfilehash: a7f80a71aa83e255efe81b82ce57026ed0749165
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046668"
---
# <a name="configure-call-routing-for-direct-routing"></a>직접 라우팅에 대한 호출 라우팅 구성

이 문서에서는 직접 라우팅에 대한 호출 라우팅을 구성하는 방법을 설명합니다. 직접 라우팅을 구성하기 위한 다음 단계 중 3단계입니다.

- 1단계. [SBC를 Microsoft Phone System에 연결하고 연결의 유효성을 검사합니다.](direct-routing-connect-the-sbc.md) 
- 2단계. [사용자가 직접 라우팅, 음성 및 음성 메일을 사용하도록 설정](direct-routing-enable-users.md)
- **3단계. 통화 라우팅 구성** (이 문서)
- 4단계. [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md) 

직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 [직접 라우팅 구성을 참조하세요](direct-routing-configure.md).

## <a name="call-routing-overview"></a>통화 라우팅 개요

Microsoft Phone System에는 다음을 기반으로 특정 SBC(세션 테두리 컨트롤러)로 통화를 보낼 수 있는 라우팅 메커니즘이 있습니다. 

- 호출된 숫자 패턴 
- 호출된 번호 패턴과 호출을 하는 특정 사용자
 
SCC는 활성 및 백업으로 지정할 수 있습니다. 활성으로 구성된 SBC를 특정 호출 경로에 사용할 수 없는 경우 호출이 백업 SBC로 라우팅됩니다.
 
호출 라우팅은 다음 요소로 구성됩니다. 

- **통화 라우팅 정책** – 음성 라우팅 정책이라고도 합니다. 사용자 또는 여러 사용자에게 할당할 수 있는 PSTN 사용에 대한 컨테이너입니다. 

- **PSTN 사용 -** 음성 경로 및 PSTN 사용용 컨테이너로, 다양한 음성 라우팅 정책에서 공유할 수 있습니다. 

- **음성 경로** – 통화 번호가 패턴과 일치하는 통화에 사용할 수 있는 온라인 PSTN 게이트웨이의 숫자 패턴 및 집합입니다.

- **온라인 PSTN 게이트웨이** - 전달 P-Asserted-Identity(PAI) 또는 기본 코덱과 같이 SBC를 통해 호출을 할 때 적용되는 구성도 저장하는 SBC에 대한 포인터입니다. 음성 경로에 추가할 수 있습니다.

## <a name="voice-routing-policy-considerations"></a>음성 라우팅 정책 고려 사항

사용자에게 통화 플랜 라이선스가 있는 경우 해당 사용자의 발신 통화는 Microsoft 통화 플랜 PSTN 인프라를 통해 자동으로 라우팅됩니다. 통화 플랜 사용자에게 온라인 음성 라우팅 정책을 구성하고 할당하는 경우 해당 사용자의 발신 통화가 온라인 음성 라우팅 정책에 정의된 번호 패턴과 일치하는지 여부를 확인합니다. 일치하는 항목이 있으면 직접 라우팅 트렁크를 통해 호출이 라우팅됩니다. 일치하는 항목이 없으면 호출이 통화 계획 PSTN 인프라를 통해 라우팅됩니다.

> [!CAUTION]
> 전역(조직 전체 기본값) 온라인 음성 라우팅 정책을 구성하고 적용하는 경우 조직의 모든 음성 사용 가능 사용자가 해당 정책을 상속하므로 통화 플랜 및 운영자 연결 사용자의 PSTN 호출이 실수로 직접 라우팅 트렁크로 라우팅될 수 있습니다. 모든 사용자가 글로벌 온라인 음성 라우팅 정책을 사용하지 않도록 하려면 사용자 지정 온라인 음성 라우팅 정책을 구성하고 개별 음성 지원 사용자에게 할당합니다.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>예제 1: 하나의 PSTN을 사용하여 음성 라우팅

다음 다이어그램은 통화 흐름에서 음성 라우팅 정책의 두 가지 예를 보여 줍니다.

**통화 흐름 1(왼쪽):** 사용자가 +1 425 XXX XX 또는 +1 206 XXX XX XX를 호출하면 호출이 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz 라우팅됩니다. sbc1.contoso.biz 또는 sbc2.contoso.biz 모두 사용할 수 없는 경우 호출이 삭제됩니다. 

**통화 흐름 2(오른쪽):** 사용자가 +1 425 XXX XX 또는 +1 206 XXX XX XX를 호출하는 경우 호출은 먼저 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz 라우팅됩니다. SBC를 사용할 수 없는 경우 우선 순위가 낮은 경로가 시도됩니다(sbc3.contoso.biz 및 sbc4.contoso.biz). 사용할 수 있는 SCC가 없으면 호출이 삭제됩니다. 

![음성 라우팅 정책 예제를 보여 줍니다.](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

두 예제에서 음성 경로에 우선 순위가 할당되는 동안 경로의 SCC는 임의 순서로 시도됩니다.

  > [!NOTE]
  > 사용자에게 Microsoft 통화 플랜 라이선스가 없는 한 예제 구성에서 패턴 +1 425 XXX XX 또는 +1 206 XXX XX XX와 일치하는 숫자를 제외한 모든 번호에 대한 호출이 삭제됩니다. 사용자에게 통화 플랜 라이선스가 있는 경우 통화는 Microsoft 통화 플랜의 정책에 따라 자동으로 라우팅됩니다. Microsoft 통화 플랜은 Microsoft 통화 플랜 라이선스가 있는 모든 사용자에게 마지막 경로로 자동으로 적용되며 추가 통화 라우팅 구성이 필요하지 않습니다.

다음 다이어그램에 표시된 예제에서는 다른 모든 미국 및 캐나다 번호(전화 번호 패턴 +1 XXX XXX XX XX로 이동하는 호출)에 대한 호출을 보내기 위해 음성 경로가 추가됩니다.

![세 번째 경로가 있는 음성 라우팅 정책을 표시합니다.](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

다른 모든 통화의 경우 사용자에게 라이선스(Microsoft Phone 시스템 및 Microsoft 통화 플랜)가 모두 있는 경우 자동 경로가 사용됩니다. 관리자가 만든 온라인 음성 경로의 숫자 패턴과 일치하는 항목이 없는 경우 통화는 Microsoft 통화 플랜을 통해 라우팅됩니다. 사용자에게 Microsoft Phone 시스템만 있는 경우 일치하는 규칙을 사용할 수 없으므로 통화가 삭제됩니다.

  > [!NOTE]
  > 이 경우 경로 "기타 +1"의 우선 순위 값은 +1 XXX XXX XX XX 패턴과 일치하는 경로가 하나만 있기 때문에 중요하지 않습니다. 사용자가 +1 324 567 89 89를 호출하고 sbc5.contoso.biz 및 sbc6.contoso.biz 모두 사용할 수 없는 경우 호출이 삭제됩니다.

다음 표에서는 세 개의 음성 경로를 사용하는 구성을 요약합니다. 이 예제에서 세 경로는 모두 동일한 PSTN 사용 "미국 및 캐나다"의 일부입니다.  모든 경로는 "미국 및 캐나다" PSTN 사용과 연결되며 PSTN 사용은 "미국 전용" 음성 라우팅 정책과 연결됩니다.

|**PSTN 사용량**|**음성 경로**|**숫자 패턴**|**우선 순위**|**Sbc**|**설명**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|미국 및 캐나다|"레드먼드 1"|^\\+1(425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|호출된 숫자 +1 425 XXX XX XX 또는 +1 206 XXX XX XX에 대한 활성 경로|
|미국 및 캐나다|"레드먼드 2"|^\\+1(425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|호출된 숫자 +1 425 XXX XX XX 또는 +1 206 XXX XX XX에 대한 백업 경로|
|미국 및 캐나다|"기타 +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|호출된 숫자 +1 XXX XXX XX XX에 대한 경로(+1 425 XXX XX 또는 +1 206 XXX XX XX 제외)|
|||||||

## <a name="example-1-configuration-steps"></a>예제 1: 구성 단계

다음 예제에서는 다음 방법을 보여줍니다.

1. 단일 PSTN 사용을 만듭니다.
2. 세 개의 음성 경로를 구성합니다.
3. 음성 라우팅 정책을 만듭니다.
4. Spencer Low라는 사용자에게 정책을 할당합니다.

[Microsoft Teams 관리 센터](#admincenterexample1) 또는 [PowerShell](#powershellexample1)을 사용하여 이러한 단계를 수행할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>1단계: "미국 및 캐나다" PSTN 사용량 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **직접 라우팅** 으로 이동한 다음 오른쪽 위 모서리에서 **PSTN 사용 레코드 관리를** 선택합니다.
2. **추가** 를 클릭하고 **미국 및 캐나다를** 입력한 다음 **적용** 을 클릭합니다.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>2단계: 세 개의 음성 경로 만들기(Redmond 1, Redmond 2 및 기타 +1)

다음 단계에서는 음성 경로를 만드는 방법을 설명합니다. 이전 표에 설명된 설정을 사용하여 이 예제의 Redmond 1, Redmond 2 및 기타 +1이라는 세 개의 음성 경로를 만들려면 다음 단계를 사용합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **직접 라우팅** 으로 이동한 다음 **, 음성 경로** 탭을 선택합니다.
2. **추가** 를 클릭한 다음 음성 경로의 이름과 설명을 입력합니다.
3. 우선 순위를 설정하고 전화 걸기 번호 패턴을 지정합니다.
4. 음성 경로를 사용하여 SBC를 등록하려면 **등록된 SBC(선택 사항)** 에서 **SBC 추가** 를 클릭하고 등록할 SBC를 선택한 다음 **적용** 을 클릭합니다.
5. PSTN 사용 레코드를 추가하려면 **PSTN 사용량 레코드(선택 사항)** 에서 **PSTN 사용량 추가** 를 클릭하고 추가할 PSTN 레코드를 선택한 다음 **적용** 을 클릭합니다.
6. **저장** 을 클릭합니다.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>3단계: "US Only"라는 음성 라우팅 정책을 만들고 정책에 "미국 및 캐나다" PSTN 사용량을 추가합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성 음성** > **라우팅 정책** 으로 이동한 다음 **추가** 를 클릭합니다.
2. **이름으로 미국만** 입력하고 설명을 추가합니다.
3. **PSTN 사용 레코드** 에서 **PSTN 사용량 추가** 를 클릭하고 "미국 및 캐나다" PSTN 사용 레코드를 선택한 다음 **적용** 을 클릭합니다.
4. **저장** 을 클릭합니다.

자세한 내용은 [음성 라우팅 정책 관리를](manage-voice-routing-policies.md) 참조하세요.

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>4단계: Spencer Low라는 사용자에게 음성 라우팅 정책 할당

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자** 로 이동한 후 해당 사용자를 클릭합니다.
2. **정책을** 클릭한 다음 **할당된 정책** 옆에 있는 **편집** 을 클릭합니다.
3. **음성 라우팅 정책** 에서 "미국 전용" 정책을 선택한 다음 **저장** 을 클릭합니다.

자세한 내용은 [음성 라우팅 정책 관리를](manage-voice-routing-policies.md) 참조하세요.

### <a name="using-powershell"></a>PowerShell 사용
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>1단계: "미국 및 캐나다" PSTN 사용량 만들기

비즈니스용 Skype Online의 원격 PowerShell 세션에서 다음을 입력합니다.

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

다음을 입력하여 사용량이 생성되었는지 확인합니다.

```PowerShell
Get-CSOnlinePSTNUsage
``` 

자를 수 있는 이름 목록을 반환합니다.

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

다음 예제에서는 PowerShell 명령을 실행 `(Get-CSOnlinePSTNUsage).usage` 하여 전체 이름(잘리지 않음)을 표시한 결과를 보여줍니다.

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>2단계: 세 개의 음성 경로 만들기(Redmond 1, Redmond 2 및 기타 +1)

"Redmond 1" 경로를 만들려면 비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력합니다.

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

다음을 반환합니다.

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

Redmond 2 경로를 만들려면 다음을 입력합니다.

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

기타 +1 경로를 만들려면 다음을 입력합니다.

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > NumberPattern 특성의 정규식이 유효한 식인지 확인합니다. 이 웹 사이트를 사용하여 테스트할 수 있습니다. [https://www.regexpal.com](https://www.regexpal.com)

경우에 따라 모든 호출을 동일한 SBC로 라우팅해야 합니다. use -NumberPattern ".*"

모든 호출을 동일한 SBC로 라우팅합니다.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

다음과 같이 옵션을 사용하여 PowerShell 명령을 실행 `Get-CSOnlineVoiceRoute` 하여 경로를 올바르게 구성했는지 확인합니다.

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
다음을 반환해야 합니다.

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

예제에서 경로 "기타 +1"에 우선 순위 4가 자동으로 할당되었습니다. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>3단계: "US Only"라는 음성 라우팅 정책을 만들고 정책에 "미국 및 캐나다" PSTN 사용량을 추가합니다.

비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력합니다.

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

결과는 다음 예제에 나와 있습니다.

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>4단계: Spencer Low라는 사용자에게 음성 라우팅 정책 할당

비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력합니다.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

다음 명령을 입력하여 정책 할당의 유효성을 검사합니다.

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

이 명령은 다음을 반환합니다.

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>예제 2: 여러 PSTN 사용량이 있는 음성 라우팅

예제 1에서 만든 음성 라우팅 정책은 Microsoft 통화 플랜 라이선스가 사용자에게 할당되지 않는 한 미국 및 캐나다의 전화 번호에 대한 호출만 허용합니다.

다음 예제에서는 "제한 없음" 음성 라우팅 정책을 만들 수 있습니다. 이 정책은 예제 1에서 만든 "미국 및 캐나다" PSTN 사용량과 새로운 "International" PSTN 사용을 다시 사용합니다. 이 정책은 다른 모든 호출을 SCC sbc2.contoso.biz 및 sbc5.contoso.biz 라우팅합니다.

표시된 예제는 사용자 Spencer Low에 미국 전용 정책을 할당하고, 라우팅이 다음과 같이 수행되도록 사용자 John Woods에 제한 없음 정책을 할당합니다.

- 스펜서 로우 – 미국 전용 정책.  통화는 미국 및 캐나다 번호로만 허용됩니다. Redmond 번호 범위를 호출할 때 특정 SCC 집합을 사용해야 합니다. 통화 플랜 라이선스가 사용자에게 할당되지 않는 한 미국 이외의 번호는 라우팅되지 않습니다.

- 존 우즈 – 국제 정책.  호출은 임의의 번호로 허용됩니다. Redmond 번호 범위를 호출할 때 특정 SCC 집합을 사용해야 합니다. 미국 이외의 번호는 sbc2.contoso.biz 및 sbc5.contoso.biz 사용하여 라우팅됩니다.

![사용자 Spencer Low에 할당된 음성 라우팅 정책을 표시합니다.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

다른 모든 통화의 경우 사용자에게 라이선스(Microsoft Phone 시스템 및 Microsoft 통화 플랜)가 모두 있는 경우 자동 경로가 사용됩니다. 관리자가 만든 온라인 음성 경로의 숫자 패턴과 일치하는 항목이 없으면 Microsoft 통화 플랜을 사용하여 통화가 라우팅됩니다.  사용자에게 Microsoft Phone 시스템만 있는 경우 일치하는 규칙을 사용할 수 없으므로 통화가 삭제됩니다.

![사용자 John Woods에 할당된 음성 라우팅 정책을 표시합니다.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

다음 표에는 라우팅 정책 "제한 없음" 사용 지정 및 음성 경로가 요약되어 있습니다. 

| PSTN 사용량 | 음성 경로 | 숫자 패턴 | 우선 순위 | Sbc | 설명 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|미국 및 캐나다|"레드먼드 1"|^\\+1(425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|수신자 번호 +1 425 XXX XX 또는 +1 206 XXX XX XX에 대한 활성 경로|
|미국 및 캐나다|"레드먼드 2"|^\\+1(425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|수신자 번호 +1 425 XXX XX 또는 +1 206 XXX XX XX에 대한 백업 경로|
|미국 및 캐나다|"기타 +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|수신자 번호 +1 XXX XXX XX XX 경로(+1 425 XXX XX 또는 +1 206 XXX XX XX 제외)|
|국제|국제|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|임의의 숫자 패턴에 대한 경로 |

  > [!NOTE]
  > - 음성 라우팅 정책의 PSTN 사용 순서는 매우 중요합니다. 사용량은 순서대로 적용되며 첫 번째 사용량에서 일치하는 항목이 발견되면 다른 사용량은 평가되지 않습니다. "국가별" PSTN 사용량은 "미국 및 캐나다" PSTN 사용 후에 사용해야 합니다. PSTN 사용량의 순서를 변경하려면 명령을 실행합니다 `Set-CSOnlineVoiceRoutingPolicy` . <br/>예를 들어 순서를 "미국 및 캐나다" 첫 번째 및 "International" 두 번째 순서에서 역순 실행으로 변경하려면 다음을 수행합니다.<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - "기타 +1" 및 "국제" 음성 경로의 우선 순위가 자동으로 할당됩니다. "Redmond 1"과 "Redmond 2"보다 우선 순위가 낮으면 중요하지 않습니다.

## <a name="example-2-configuration-steps"></a>예제 2: 구성 단계

다음 예제에서는 다음 방법을 보여줍니다.

1. International이라는 새 PSTN 사용을 만듭니다.
2. International이라는 새로운 음성 경로를 만듭니다.
3. 제한 없음이라는 음성 라우팅 정책을 만듭니다.
4. 사용자 John Woods에 정책을 할당합니다.

[Microsoft Teams 관리 센터](#admincenterexample2) 또는 [PowerShell](#powershellexample2)을 사용하여 이러한 단계를 수행할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>1단계: "International" PSTN 사용량 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **직접 라우팅** 으로 이동한 다음 오른쪽 위 모서리에서 **PSTN 사용 레코드 관리를** 선택합니다.
2. **추가** 를 클릭하고 **International** 을 입력한 다음 **적용** 을 클릭합니다.

#### <a name="step-2-create-the-international-voice-route"></a>2단계: "국제" 음성 경로 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **직접 라우팅** 으로 이동한 다음 **, 음성 경로** 탭을 선택합니다.
2. **추가** 를 클릭하고 이름으로 "International"을 입력한 다음 설명을 추가합니다.
3. 우선 순위를 4로 설정한 다음 전화 접속 번호 패턴을 \d+로 설정합니다.
4. **등록된 SCC(선택 사항)** 에서 **SBC 추가** 를 클릭하고 sbc2.contoso.biz 선택하고 **sbc5.contoso.biz 적용을** 클릭합니다.
5. **PSTN 사용 레코드(선택 사항)** 에서 **PSTN 사용량 추가** 를 클릭하고 "International" PSTN 사용 레코드를 선택한 다음 **적용** 을 클릭합니다.
6. **저장** 을 클릭합니다.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>3단계: "제한 없음"이라는 음성 라우팅 정책을 만들고 정책에 "미국 및 캐나다" 및 "국제" PSTN 사용량을 추가합니다.

PSTN 사용 "미국 및 캐나다"는 로컬 또는 온-프레미스 호출로 "+1 425 XXX XX" 및 "+1 206 XXX XX"에 대한 호출에 대한 특수 처리를 유지하기 위해 이 음성 라우팅 정책에서 다시 사용됩니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성 음성** > **라우팅 정책** 으로 이동한 다음 **추가** 를 클릭합니다.
2. 이름으로 **제한 없음** 을 입력하고 설명을 추가합니다.
3. **PSTN 사용량 레코드** 아래에서 **PSTN 사용량 추가** 를 클릭하고 "미국 및 캐나다" PSTN 사용 레코드를 선택한 다음, "International" PSTN 사용 레코드를 선택합니다. **적용** 을 클릭합니다.

    PSTN 사용량의 순서를 기록해 둡니다.

    - 이 예제와 같이 사용량이 구성된 번호 "+1 425 XXX XX XX"를 호출한 경우 호출은 "미국 및 캐나다" 사용량에 설정된 경로를 따르며 특수 라우팅 논리가 적용됩니다. 즉, 호출은 sbc1.contoso.biz 사용하여 라우팅되고 먼저 sbc2.contoso.biz 백업 경로로 sbc3.contoso.biz sbc4.contoso.biz.

    - "International" PSTN 사용량이 "미국 및 캐나다" 이전인 경우 +1 425 XXX XX XX에 대한 호출은 라우팅 논리의 일부로 sbc2.contoso.biz sbc5.contoso.biz 라우팅됩니다.

4. **저장** 을 클릭합니다.

자세한 내용은 [음성 라우팅 정책 관리를](manage-voice-routing-policies.md) 참조하세요.

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>4단계: John Woods라는 사용자에게 음성 라우팅 정책 할당

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자** 로 이동한 후 해당 사용자를 클릭합니다.
2. **정책을** 클릭한 다음 **할당된 정책** 옆에 있는 **편집** 을 클릭합니다.
3. **음성 라우팅 정책** 에서 "제한 없음" 정책을 선택한 다음 **저장** 을 클릭합니다.

그 결과 John Woods의 통화에 적용되는 음성 정책은 무제한이며 미국, 캐나다 및 국제 통화에 사용할 수 있는 통화 라우팅 논리를 따릅니다.

### <a name="using-powershell"></a>PowerShell 사용
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>1단계: "International" PSTN 사용량 만들기

비즈니스용 Skype Online의 원격 PowerShell 세션에서 다음을 입력합니다.

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>2단계: "International"이라는 새 음성 경로 만들기

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

다음을 반환합니다.

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>3단계: "제한 없음"이라는 음성 라우팅 정책 만들기

PSTN 사용 "Redmond 1" 및 "Redmond"는 로컬 또는 온-프레미스 호출로 "+1 425 XXX XX" 및 "+1 206 XXX XX XX" 번호 호출에 대한 특수 처리를 유지하기 위해 이 음성 라우팅 정책에서 다시 사용됩니다.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

PSTN 사용량의 순서를 기록해 둡니다.

  - 다음 예제와 같이 사용량이 구성된 번호 "+1 425 XXX XX"를 호출한 경우 호출은 "미국 및 캐나다" 사용량에 설정된 경로를 따르며 특수 라우팅 논리가 적용됩니다. 즉, 호출은 sbc1.contoso.biz 사용하여 라우팅되고 먼저 sbc2.contoso.biz 백업 경로로 sbc3.contoso.biz sbc4.contoso.biz.

  - "International" PSTN 사용량이 "미국 및 캐나다" 이전인 경우 +1 425 XXX XX XX에 대한 호출은 라우팅 논리의 일부로 sbc2.contoso.biz sbc5.contoso.biz 라우팅됩니다. 다음 명령을 입력합니다.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

다음을 반환합니다.

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>4단계: John Woods라는 사용자에게 음성 라우팅 정책 할당

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

그런 다음, 다음 명령을 사용하여 할당을 확인합니다. 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

다음을 반환합니다.

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

그 결과 John Woods의 통화에 적용되는 음성 정책은 무제한이며 미국, 캐나다 및 국제 통화에 사용할 수 있는 통화 라우팅 논리를 따릅니다.

## <a name="run-a-self-diagnostics-tool"></a>자체 진단 도구 실행

Microsoft 365 관리자 사용자는 사용자가 직접 라우팅에 대해 올바르게 구성되었는지 확인하기 위해 테넌트 내에서 실행할 수 있는 진단에 액세스할 수 있습니다. 

> [!NOTE]
>이 기능은 Microsoft 365 Government, 21Vianet에서 운영하는 Microsoft 365 또는 Microsoft 365 독일에서 사용할 수 없습니다.

다음과 같이 테스트 실행을 선택합니다. 그러면 Microsoft 365 관리 센터의 진단이 채워집니다.
>> [!div class="nextstepaction"]
>> [테스트 실행: Teams 직접 라우팅](https://aka.ms/TeamsDirectRoutingDiag)

진단은 광범위한 확인을 수행합니다.

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
