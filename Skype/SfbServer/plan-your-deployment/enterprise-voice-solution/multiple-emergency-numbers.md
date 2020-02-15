---
title: 비즈니스용 Skype 서버에서 여러 응급 번호 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: 비즈니스용 Skype 서버에서 여러 응급 번호를 계획 하는 방법을 알아보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: 10b6d02391fbf1ac7af1ae5233261c36fd2fd6ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983023"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 여러 응급 번호 계획
 
비즈니스용 Skype 서버에서 여러 응급 번호를 계획 하는 방법을 알아보려면이 항목을 읽어 보십시오.
  
비즈니스용 Skype 서버는 이제 클라이언트에 대해 여러 응급 번호 구성을 지원 합니다. 여러 응급 번호는 6 월 2016 누적 업데이트에 도입 된 새로운 기능입니다. 미국의 비상 번호가 하나인 911 경우에는 많은 나라에서 여러 응급 번호를 지원 합니다. 예를 들어 영국은 영국에 해당 하는 999, 112, 유럽 연합의 비상 번호를 모두 지원 합니다. 
  
이 기능은 미국 내의 의료 보험 공급자에 게 여러 코드 파란색 비상 전화에 대 한 로밍 지원을 원하는 경우에도 유용 합니다.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>여러 응급 번호 및 위치 정책

응급 통화를 구현 하는 방법을 정의 하는 위치 정책을 만들어 응급 통화를 구성 합니다. 위치 정책을 사용 하 여 미국에서 911와 같이 긴급 통화를 구성 하는 번호를 정의 합니다. 영국에 999 및 112가 있습니다. 위치 정책은 사용자가 응급 통화를 사용할 수 있는지 여부를 결정 하 고, 그렇다면 비상 전화의 동작을 확인 합니다. 또한 회사 보안에서 자동으로 알릴지 여부와 통화를 라우팅하는 방법을 정의할 수 있습니다.
  
위치 정책을 정의 하 고 수정 하는 방법에 대 한 자세한 내용은 비즈니스용 skype [서버의 계획 위치 정책](location-policies.md) 및 [Create Location Policy for business server](../../deploy/deploy-enterprise-voice/create-location-policies.md)을 참조 하십시오. 다음 항목에서는 위치 정책에 대 한 개념에 대해 설명 합니다. 그러나 [비즈니스용 Skype에서 여러 응급 번호 구성](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 의 지침에 따라 여러 응급 전화 번호를 구성 해야 합니다.
  
여러 응급 번호를 계획할 때는 다음 사항을 염두에 두어야 합니다.
  
- 6 월 2016 누적 업데이트를 사용 하 여 지정 된 위치 정책에 대해 최대 5 개의 비상 번호를 정의할 수 있습니다. 11 월 2016 누적 업데이트를 사용 하는 경우이 번호는 100로 증가 합니다.
    
    > [!NOTE]
    > 11 월 2016 누적 업데이트를 아직 업그레이드 하지 않은 경우 [비즈니스용 Skype 서버 2015 업데이트](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)를 참조 하세요. 
  
- 각 비상 전화 번호에 대해 지정 된 위치 정책에 고유한 비상 다이얼 마스크를 0 개 이상 지정할 수 있습니다.
    
    다이얼 마스크는 전화를 걸 때 비상 전화 걸기 번호 값의 값으로 변환 하려는 숫자입니다. 예를 들어이 필드에 212 값을 입력 하 고 응급 전화 걸기 번호 필드에 911 값이 있는 경우를 가정해 보겠습니다. 사용자가 212에 전화를 걸면 번호가 911로 변환 됩니다. 이를 통해 대체 응급 번호에 전화를 걸 수 있으며, 다른 비상 번호로 전화를 걸 수 있는 국가 또는 지역 사용자가 해당 국가나 지역 번호를 사용 하 여 통화를 시도 하는 경우 (예: 현재 거주 하는 국가 또는 지역입니다. 예를 들어 응급 번호가 다른 국가의 사용자가 외국에서 그 나라의 번호 대신 자신의 국가에서 사용되는 번호로 전화를 거는 경우에 유용합니다. 예: 212; 414 다이얼 마스크의 문자열 제한은 100 자입니다. 각 문자는 0부터 9까지의 숫자여야 합니다.
    
- 각 위치 정책에는이 정책을 사용 하 여 클라이언트 로부터 긴급 통화를 라우팅하는 데 사용 되는 음성 경로를 결정 하는 데 사용 되는 단일 PSTN (공중 전화망) 사용이 있습니다. 사용에는 비상 번호로 고유한 경로를 사용할 수 있습니다.
    
- 위치 정책에 EmergencyNumbers 및 DialString 매개 변수가 모두 정의 되어 있고 클라이언트가 여러 응급 번호를 지 원하는 경우 응급 번호가 우선 합니다. 클라이언트에서 여러 응급 수치를 지원 하지 않는 경우 비상 다이얼 문자열이 사용 됩니다.
    
- 비즈니스용 Skype 및 Lync 클라이언트에서 여러 응급 번호, 다이얼 마스크 및 PSTN (공중 전화망) 사용을 지 원하는 방법에 대 한 자세한 내용은 [클라이언트 지원](multiple-emergency-numbers.md#BKMK_Clients)을 참조 하십시오.
    
> [!NOTE]
> 비즈니스용 Skype 제어판을 사용 하 여 여러 응급 전화 번호를 구성할 수는 없습니다. 여러 응급 전화 번호를 구성 하려면 PowerShell을 사용 해야 합니다. 
  
여러 응급 번호를 구성 하기 전에 다음 사항을 염두에 두십시오.
  
- 여러 응급 번호를 구성 하려면 CsEmergencyNumber cmdlet을 사용 해야 하 고, EmergencyNumbers 매개 변수를 [새-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 및 [Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet과 함께 지정 하 여 두 개 이상의 비상 번호를 지 원하는 위치 정책을 정의 해야 합니다.
    
- EmergencyDialString 및 EmergencyDialMask 매개 변수를 사용 하 여 CsLocationPolicy 또는 새-CsLocationPolicy cmdlet을 사용 하 여 정의 된 기존 번호가 있는 경우 EmergencyNumbers 매개 변수에 지정 된 값이 이전 항목 보다 우선적으로 적용 됩니다. 값. 즉, EmergencyDialString 및 EmergencyDialMask 매개 변수의 값이 무시 됩니다.
    
- EmergencyDialString 및 EmergencyDialMask 매개 변수와 함께 CsLocationPolicy 또는 새 CsLocationPolicy cmdlet을 사용 하 여 정의 된 기존 번호가 있고 *새 응급 번호를 구성 하지* 않은 경우에는 기존 번호가 계속 사용 됩니다.
    
- 여러 응급 번호 기능이 작동 하려면 실행 중인 클라이언트 버전에서 새 기능을 지원할 수 있어야 합니다. 오래 된 클라이언트는 EmergencyDialString 및 EmergencyDialMask 매개 변수와 함께 CsLocationPolicy 또는 새 CsLocationPolicy cmdlet으로 지정 된 이전 값을 계속 사용 합니다. 
    
- 사용자가 다이얼 문자열과 일치 하는 번호로 전화를 걸려면 다이얼 마스크가 필요 하지 않습니다. 예를 들어 사용자가 전화를 거는 번호가 911 이면 다이얼 문자열이 911이 고 마스크는 필요 하지 않습니다. 
    
여러 응급 번호를 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype에서 여러 응급 번호 구성](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)를 참조 하세요.
  
다음 표에서는 예제 위치 정책 (예: 일부 특성이 표시 되지 않음)을 보여 줍니다.
  

|**위치 정책 이름**|**E911 사용**|**비상 다이얼 문자열**|**다이얼 마스크**|**비상 번호**|**PSTN 사용**|**위치 필요**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|NZRatingAO  <br/> |예  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |예  <br/> |
|미국-병원  <br/> |예  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |예  <br/> |
|인  <br/> |예  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |아니요  <br/> |
|인도  <br/> |예  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |아니요  <br/> |
   
 **미국** -여러 응급 전화 번호에 대 한 요구 사항은 없습니다. 미국의 경우 이전 응급 전화 걸기 문자열 및 다이얼 마스크 구성을 사용 합니다.
  
 **미국-병원** -"450"을 마스킹할 필요는 없습니다. 여러 응급 수치를 지원 하지 않는 클라이언트의 경우 이전 응급 전화 걸기 문자열 및 다이얼 마스크 구성을 사용할 수 있습니다. 여러 응급 번호를 지 원하는 클라이언트의 경우 마스킹 450 대신 "911" 및 "450"에 대해 비상 번호를 정의할 수 있습니다.
  
 **런던** -여러 응급 전화 번호를 지원 하지 않는 클라이언트의 경우에는 오래 된 비상 다이얼 문자열 및 다이얼 마스크 구성을 사용할 수 있습니다. 여러 응급 번호를 지 원하는 클라이언트의 경우 각각에 대해 "999" 및 "112" 둘 다에 대해 비상 번호를 정의할 수 있습니다.
  
 **인도** -배포 된 모든 클라이언트에서 여러 응급 전화 번호를 지원 합니다. 인도에서는 여러 비상 번호를 구성 하기만 하면 됩니다.
  
## <a name="client-support"></a>클라이언트 지원
<a name="BKMK_Clients"> </a>

다음 표에는 여러 응급 번호에 대 한 클라이언트 지원이 나와 있습니다. Microsoft는 계속 해 서 추가 클라이언트에 대 한 지원을 테스트 하 고 릴리스 합니다. 종종 확인하십시오.

|**Windows**|**버전**|
|:-----|:-----|
|**간편 실행** <br/> |5 월 10 일에 릴리스된 CC (현재 채널) 2016-버전 1604 (빌드 6868.2062)  <br/> |
||FRDC (첫 번째 릴리스 현재 채널)가 6 월 14 일에 출시 되었습니다. 2016-버전 1605 (빌드 6965.2058)  <br/> |
||10 월 11 일에 릴리스된 DC (지연 된 채널) 2016-버전 1605 (빌드 6965.2092)  <br/> |
|**MSI** <br/> |6 월 7 일 업데이트-[https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac 및 iOS** <br/> |**버전** <br/> |
||비즈니스용 Skype Mac 클라이언트 버전 16.9  <br/> 비즈니스용 Skype iOS 클라이언트 버전 6.16  <br/> |
|**Android** <br/> |**버전** <br/> |
||비즈니스용 Skype Android 클라이언트 버전 6.17  <br/> |
|**Lync Phone Edition** <br/> |**버전** <br/> |
|| Aastra 6721ip 및 Aastra 6721ip 전화-9 월 2016 누적 업데이트 (빌드 7577.4512)-[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 및 HP 4120 전화-09-9 2016 월 누적 업데이트 (빌드 7577.4512)-[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 및 Polycom CX3000 전화-9 월 2016 누적 업데이트 (빌드 7577.4512)-[https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

