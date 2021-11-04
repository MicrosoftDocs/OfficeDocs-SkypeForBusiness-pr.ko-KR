---
title: 2016년 8월에 여러 긴급 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: 이 항목을 읽고 여러 긴급 번호를 계획하는 방법을 비즈니스용 Skype 서버.
ms.openlocfilehash: 8e4761b22295d71c33af414e2a92dac7bf1210d6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741965"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>2016년 8월에 여러 긴급 비즈니스용 Skype 서버
 
이 항목을 읽고 여러 긴급 번호를 계획하는 방법을 비즈니스용 Skype 서버.
  
비즈니스용 Skype 서버 클라이언트에 대해 여러 긴급 번호 구성을 지원할 수 있습니다. 여러 긴급 번호는 2016년 6월 누적 업데이트에 도입된 새로운 기능입니다. 미국은 하나의 긴급 번호인 911을 보유하고 있는 반면 많은 국가는 여러 긴급 번호를 지원하고 있습니다. 예를 들어 영국은 영국의 긴급 번호인 999와 유럽 연합의 긴급 번호인 112를 모두 지원합니다. 
  
이 기능은 여러 코드 파랑 긴급 번호에 대한 로밍 지원을 원하는 미국 내 의료 서비스 공급자에게도 유용합니다.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>여러 긴급 번호 및 위치 정책

긴급 통화를 구현하는 방법을 정의하는 위치 정책을 만들어 긴급 통화를 구성합니다. 위치 정책을 사용하여 긴급 통화를 구성하는 번호(예: 미국의 경우 911)를 정의합니다. 영국의 999 및 112 위치 정책은 사용자가 긴급 통화를 사용할 수 있는지 여부와 긴급 통화의 동작이 어떤지 여부를 확인합니다. 회사 보안에 자동으로 알림을 할지 여부와 통화를 라우팅할 방법을 정의할 수도 있습니다.
  
위치 정책을 정의하고 수정하는 데 대한 자세한 내용은 [Plan location policies for 비즈니스용 Skype 서버](location-policies.md) and Create location policies in [비즈니스용 Skype 서버.](../../deploy/deploy-enterprise-voice/create-location-policies.md) 이러한 항목에서는 위치 정책에 대한 개념에 대해 설명하고 있습니다. 그러나 여러 긴급 번호를 [](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 구성하려면 에서 여러 긴급 번호 구성의 비즈니스용 Skype 따라야 합니다.
  
여러 긴급 번호를 계획할 때 다음에 유의하십시오.
  
- 2016년 6월 누적 업데이트를 사용하면 특정 위치 정책에 대해 최대 5개 긴급 번호를 정의할 수 있습니다. 2016년 11월 누적 업데이트의 경우 이 수치가 100으로 늘어납니다.
    
    > [!NOTE]
    > 아직 2016년 11월 누적 업데이트로 업그레이드하지 않은 경우 [Updates to 비즈니스용 Skype 서버 2015를 참조하세요.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) 
  
- 각 긴급 번호에 대해 0개 이상의 긴급 다이얼 마스크를 지정할 수 있습니다. 이는 특정 위치 정책에 고유한 것입니다.
    
    다이얼 마스크는 전화를 걸 때 긴급 전화 번호 값으로 변환하려는 번호입니다. 예를 들어 이 필드에 값 212를 입력하고 긴급 전화 번호 필드의 값이 911인 경우를 가정해 보겠습니다. 사용자가 212로 전화를 걸면 번호가 911로 변환됩니다. 이렇게 하면 대체 긴급 번호로 전화를 걸 수 있으며 통화가 긴급 서비스에 연결됩니다(예: 다른 긴급 번호가 있는 국가나 지역의 누군가가 현재 있는 국가 또는 지역의 번호가 아닌 해당 국가 또는 지역 번호로 전화를 걸려 시도하는 경우). 예를 들어 응급 번호가 다른 국가의 사용자가 외국에서 그 나라의 번호 대신 자신의 국가에서 사용되는 번호로 전화를 거는 경우에 유용합니다. 예: 212;414. 다이얼 마스크의 문자열 제한은 100자입니다. 각 문자는 0부터 9까지의 숫자여야 합니다.
    
- 각 위치 정책에는 이 정책을 사용하여 클라이언트의 긴급 통화를 라우팅하는 데 사용되는 음성 경로를 결정하는 데 사용되는 단일 PSTN(공용 전화망) 사용이 있습니다. 사용법은 긴급 번호당 고유한 경로를 사용할 수 있습니다.
    
- 위치 정책에 EmergencyNumbers 및 DialString 매개 변수가 모두 정의되어 있으며 클라이언트가 여러 긴급 번호를 지원하는 경우 긴급 번호가 우선합니다. 클라이언트가 여러 긴급 번호를 지원하지 않는 경우 긴급 전화 문자열이 사용됩니다.
    
- 여러 긴급 번호비즈니스용 Skype 전화 마스크 및 PSTN(Public Switched Telephone Network) 사용 수신을 지원하는 클라이언트 및 Lync 클라이언트에 대한 자세한 내용은 클라이언트 지원을 [참조하세요.](multiple-emergency-numbers.md#BKMK_Clients)
    
> [!NOTE]
> 제어판을 사용하여 여러 긴급 번호를 구성할 비즈니스용 Skype 없습니다. PowerShell을 사용하여 여러 긴급 번호를 구성해야 합니다. 
  
여러 긴급 번호를 구성하기 전에 다음에 유의해야 합니다.
  
- 여러 긴급 번호를 구성하려면 New-CsEmergencyNumber cmdlet을 사용하며, [New-CsLocationPolicy 및 Set-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용하여 EmergencyNumbers 매개 변수를 지정하여 두 개 이상의 긴급 번호를 지원하는 위치 정책을 정의해야 합니다. [](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)
    
- EmergencyDialString 및 EmergencyDialMask 매개 변수와 함께 Set-CsLocationPolicy 또는 New-CsLocationPolicy cmdlet을 사용하여 정의된 기존 번호가 있는 경우 EmergencyNumbers 매개 변수로 지정된 값이 이전 값보다 우선합니다. 즉, EmergencyDialString 및 EmergencyDialMask 매개 변수의 값은 무시됩니다.
    
- emergencyDialString 및 EmergencyDialMask 매개 변수를 사용하여 Set-CsLocationPolicy 또는 New-CsLocationPolicy cmdlet을 사용하여  기존 번호를 정의한 경우 새 긴급 번호를 구성하지 않은 경우 기존 번호가 계속 사용됩니다.
    
- 여러 긴급 번호 기능이 작동하려면 실행 중인 클라이언트 버전이 새 기능을 지원할 수 있어야 합니다. 이전 클라이언트는 EmergencyDialString 및 EmergencyDialMask 매개 변수와 Set-CsLocationPolicy New-CsLocationPolicy 지정한 이전 값을 계속 사용합니다. 
    
- 사용자가 전화 걸기 문자열과 일치하는 번호로 전화를 걸 경우 다이얼 마스크가 필요하지 않습니다. 예를 들어 사용자가 전화를 걸 수 있는 번호가 911이면 전화 걸기 문자열은 911이고 마스크는 필요하지 않습니다. 
    
여러 긴급 번호를 구성하는 자세한 내용은 에서 여러 긴급 [번호 구성을 비즈니스용 Skype.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)
  
다음 표에는 예제 위치 정책이 나와 있습니다(예에서는 모든 특성이 표시되지는 않습니다).
  

|**위치 정책 이름**|**E911 사용**|**긴급 전화 문자열**|**다이얼 마스크**|**긴급 번호**|**PSTN 사용**|**필요한 위치**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|미국  <br/> |예  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |예  <br/> |
|US-Hospital  <br/> |예  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |예  <br/> |
|런던  <br/> |예  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |아니요  <br/> |
|인도  <br/> |예  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |아니오  <br/> |
   
 **미국** -여러 긴급 번호에 대한 요구 사항은 없습니다. 미국에서는 이전 긴급 전화 문자열 및 전화 걸기 마스크 구성을 사용하게 됩니다.
  
 **US-Hospital** — "450"을 마스크하지 말아야 하는 요구 사항이 있습니다. 아직 여러 긴급 번호를 지원하지 않는 클라이언트의 경우 이전 긴급 전화 문자열 및 전화 걸기 마스크 구성을 사용할 수 있습니다. 여러 긴급 번호를 지원하는 클라이언트의 경우 450을 마스킹하는 대신 "911"과 "450"에 대해 긴급 번호를 정의할 수 있습니다.
  
 **런던** — 아직 여러 긴급 번호를 지원하지 않는 클라이언트의 경우 이전 긴급 전화 문자열 및 전화 걸기 마스크 구성을 사용할 수 있습니다. 여러 긴급 번호를 지원하는 클라이언트의 경우 각각에 대해 마스크를 사용하여 "999" 및 "112"에 대해 긴급 번호를 정의할 수 있습니다.
  
 **인도** — 모든 배포된 클라이언트는 여러 긴급 번호를 지원합니다. 인도에서는 여러 긴급 번호만 구성하면 됩니다.
  
## <a name="client-support"></a>클라이언트 지원
<a name="BKMK_Clients"> </a>

다음 표에는 여러 긴급 번호에 대한 클라이언트 지원이 표시됩니다. Microsoft는 추가 클라이언트에 대한 지원을 계속 테스트하고 릴리스합니다. 종종 확인하십시오.

|**Windows**|**버전**|
|:-----|:-----|
|**간편 실행** <br/> |CC(현재 채널) 2016년 5월 10일 - 버전 1604(빌드 6868.2062)  <br/> |
||FRDC(2016년 6월 14일 - 버전 1605(빌드 6965.2058)에 릴리스된 FRDC(첫 번째 릴리스 현재 채널)  <br/> |
||2016년 10월 11일 출시된 DC(지연 채널) - 버전 1605(빌드 6965.2092)  <br/> |
|**MSI** <br/> |6월 7일 업데이트 - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac 및 iOS** <br/> |**버전** <br/> |
||비즈니스용 Skype Mac 클라이언트 버전 16.9  <br/> 비즈니스용 Skype iOS 클라이언트 버전 6.16  <br/> |
|**Android** <br/> |**버전** <br/> |
||비즈니스용 Skype Android 클라이언트 버전 6.17  <br/> |
|**Lync Phone Edition** <br/> |**버전** <br/> |
|| Aastra 6721ip 및 Aastra 6725ip 전화 - 2016년 9월 누적 업데이트(빌드 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 및 HP 4120 전화 - 2016년 9월 누적 업데이트(빌드 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 및 Polycom CX3000 전화 - 2016년 9월 누적 업데이트(빌드 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
