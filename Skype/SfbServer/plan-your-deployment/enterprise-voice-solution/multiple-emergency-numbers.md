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
description: 비즈니스용 Skype 서버에서 여러 응급 번호를 계획 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 6f10b5c22a26a42f33f2a3b453dd2e244c9f32ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815966"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 여러 응급 번호 계획
 
비즈니스용 Skype 서버에서 여러 응급 번호를 계획 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
비즈니스용 Skype 서버는 이제 클라이언트에 대 한 여러 응급 번호 구성을 지원 합니다. 여러 비상 번호는 6 월 2016 누적 업데이트에 도입 된 새로운 기능입니다. 미국에는 한 가지 긴급 한 번호 (911)가 있지만 여러 국가에서 비상 번호를 지원 합니다. 예를 들어 영국에는 999, 영국에 대 한 긴급 전화 번호, 그리고 유럽 연합에 대 한 비상 전화 번호 (112)가 모두 지원 됩니다. 
  
이 기능은 여러 코드 파란색 비상 전화에 대해 로밍을 지원 하려는 미국 내의 의료 보험 공급 업체에도 유용 합니다.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>여러 응급 번호 및 위치 정책

응급 통화를 구현 하는 방법을 정의 하는 위치 정책을 만들어 응급 통화를 구성할 수 있습니다. 위치 정책을 사용 하 여 전화를 거는 번호를 정의 합니다 (예: 미국에서 911). 영국에서 999 및 112. 위치 정책은 사용자가 비상 전화를 사용할 수 있는지 여부 및 긴급 통화의 동작을 확인 합니다. 또한 회사 보안에서 자동으로 알림을 받을지 여부와 통화를 라우팅하는 방법을 정의할 수 있습니다.
  
위치 정책의 정의 및 수정에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 위치 정책 계획](location-policies.md) 및 [비즈니스 용 skype 서버의 위치 정책 만들기](../../deploy/deploy-enterprise-voice/create-location-policies.md)를 참조 하세요. 이 항목에서는 위치 정책에 대 한 개념에 대해 설명 합니다. 그러나 [비즈니스용 Skype에서](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 여러 비상 번호를 구성 하는 지침에 따라 여러 비상 전화를 구성 해야 합니다.
  
여러 비상 번호를 계획할 때 다음 사항을 염두에 두어야 합니다.
  
- 6 월 2016 누적 업데이트를 사용 하 여 지정 된 위치 정책에 대해 최대 5 개의 비상 번호를 정의할 수 있습니다. 11 월 2016 누적 업데이트를 사용 하는 경우이 번호는 100로 증가 합니다.
    
    > [!NOTE]
    > 11 월 2016 누적 업데이트로 아직 업그레이드 하지 않은 경우 비즈니스용 [Skype Server 2015 업데이트](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)를 참조 하세요. 
  
- 각 비상 전화 번호에 대해 지정 된 위치 정책에 고유한 0 개 이상의 응급 다이얼 마스크를 지정할 수 있습니다.
    
    다이얼 마스크는 전화를 걸 때 비상 다이얼 번호 값의 값으로 번역 하려는 번호입니다. 예를 들어이 필드에 212 값을 입력 하 고 긴급 전화 걸기 번호 필드에 911 값이 있는 것으로 가정 합니다. 사용자가 212으로 전화를 걸면 숫자가 911로 변환 됩니다. 이렇게 하면 대체 긴급 번호로 전화를 걸 수 있으며, 다른 비상 번호로 전화를 걸 수 있는 국가 또는 지역 사용자가 해당 국가나 지역 번호를 사용 하는 경우, 예를 들어 현재 거주 하 고 있는 국가 또는 지역입니다. 세미콜론으로 값을 구분 하 여 여러 응급 전화 접속 마스크를 정의할 수 있습니다. 예를 들어 212; 414. 다이얼 마스크의 문자열 제한은 100 자입니다. 각 문자는 0 ~ 9의 숫자 여야 합니다.
    
- 각 위치 정책에는이 정책을 사용 하 여 클라이언트에서 비상 전화를 라우팅하는 데 사용 되는 음성 경로를 결정 하는 데 사용 되는 단일 PSTN (공공 전환 전화 네트워크) 사용이 있습니다. 사용량에 따라 비상 번호로 고유한 경로를 사용할 수 있습니다.
    
- 위치 정책에 EmergencyNumbers 및 DialString 매개 변수가 모두 정의 되어 있고 클라이언트가 여러 응급 번호를 지 원하는 경우 비상 번호가 우선 합니다. 클라이언트가 여러 응급 번호를 지원 하지 않는 경우 비상 다이얼 문자열이 사용 됩니다.
    
- 여러 응급 번호, 다이얼 마스크, PSTN (공개 통신 네트워크) 사용을 지 원하는 비즈니스용 Skype 및 Lync 클라이언트에 대 한 자세한 내용은 [클라이언트 지원](multiple-emergency-numbers.md#BKMK_Clients)을 참조 하세요.
    
> [!NOTE]
> 비즈니스용 Skype 제어판을 사용 하 여 여러 응급 전화 번호를 구성할 수 없습니다. 여러 비상 번호를 구성 하려면 PowerShell을 사용 해야 합니다. 
  
여러 비상 번호를 구성 하기 전에 다음 사항에 유의 하세요.
  
- 여러 비상 번호를 구성 하려면 CsEmergencyNumber cmdlet을 사용 해야 하며, [새-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 및 [Set cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet을 사용 하 여 EmergencyNumbers 매개 변수를 지정 하면 두 개 이상의 비상 번호를 지 원하는 위치 정책을 정의 해야 합니다.
    
- EmergencyDialString 및 EmergencyDialMask 매개 변수를 사용 하 여 Set-CsLocationPolicy 또는 New-CsLocationPolicy cmdlet을 사용 하 여 기존 번호를 정의한 경우 EmergencyNumbers 매개 변수를 사용 하 여 지정한 값이 이전 최대값. 즉, EmergencyDialString 및 EmergencyDialMask 매개 변수의 값은 무시 됩니다.
    
- EmergencyDialString 및 EmergencyDialMask 매개 변수를 사용 하 여 Set CsLocationPolicy 또는 New-CsLocationPolicy cmdlet을 통해 정의 된 기존 번호가 있는 경우 *새 비상 번호를 구성 하지* 않으면 기존 번호가 계속 사용 됩니다.
    
- 여러 비상 번호 기능을 사용 하려면, 실행 중인 클라이언트 버전이 새 기능을 지원할 수 있어야 합니다. 이전 클라이언트는 EmergencyDialString 및 EmergencyDialMask 매개 변수를 사용 하 여 Set-CsLocationPolicy 또는 New Cslocationxpolicy cmdlet에 의해 지정 된 이전 값을 계속 사용 합니다. 
    
- 사용자가 다이얼 문자열과 일치 하는 번호로 전화를 거는 경우에는 다이얼 마스크가 필요 하지 않습니다. 예를 들어 사용자가 전화를 거는 번호가 911 인 경우 다이얼 문자열은 911이 고 마스크는 필요 하지 않습니다. 
    
여러 응급 번호를 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype에서 여러 응급 번호 구성을](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)참조 하세요.
  
다음 표에는 예제 위치 정책 (이 예에서는 일부 특성이 표시 되지 않음)이 나와 있습니다.
  

|**위치 정책 이름**|**E911 사용**|**비상 다이얼 문자열**|**다이얼 마스크**|**비상 전화 번호**|**PSTN 사용**|**위치 필요**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|미국  <br/> |예  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |예  <br/> |
|미국-병원  <br/> |예  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |예  <br/> |
|시흥시  <br/> |예  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-119; 117; 118  <br/> |GBEmergency  <br/> |아니요  <br/> |
|인도  <br/> |예  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |아니요  <br/> |
   
 **미국** -여러 비상 전화 번호에 대 한 요구 사항은 없습니다. 미국에서는 이전의 긴급 전화 접속 문자열 및 다이얼 마스크 구성을 사용 합니다.
  
 **미국-병원** -"450"을 마스킹할 필요는 없습니다. 아직 여러 비상 번호를 지원 하지 않는 클라이언트의 경우 이전의 긴급 전화 접속 문자열 및 다이얼 마스크 구성을 사용할 수 있습니다. 여러 응급 번호를 지 원하는 클라이언트의 경우 마스킹 450 대신 "911" 및 "450"에 대 한 비상 번호를 정의할 수 있습니다.
  
 **London** -아직 여러 응급 번호를 지원 하지 않는 클라이언트의 경우 이전의 긴급 전화 접속 문자열 및 다이얼 마스크 구성을 사용할 수 있습니다. 여러 응급 번호를 지 원하는 클라이언트의 경우 각각에 대해 "999" 및 "112"에 대 한 긴급 전화 번호를 정의할 수 있습니다.
  
 **인도** -모든 배포 된 클라이언트가 여러 비상 전화를 지원 합니다. 인도에서는 여러 비상 번호를 구성 하기만 하면 됩니다.
  
## <a name="client-support"></a>클라이언트 지원
<a name="BKMK_Clients"> </a>

다음 표에는 여러 비상 전화에 대 한 클라이언트 지원이 나와 있습니다. Microsoft는 계속 해 서 추가 클라이언트에 대 한 지원을 테스트 하 고 릴리스 합니다. 자주 확인 하세요.

|**창을**|**버전**|
|:-----|:-----|
|**간편 실행** <br/> |5 월 10 일에 릴리스된 CC (현재 채널) 2016-버전 1604 (빌드 6868.2062)  <br/> |
||2016 년 6 월 14 일에 릴리스된 FRDC (현재 채널의 첫 번째 릴리스)-버전 1605 (빌드 6965.2058)  <br/> |
||10 월 11 일에 릴리스된 DC (지연 채널) 2016-버전 1605 (빌드 6965.2092)  <br/> |
|**MSI** <br/> |6 월 7 일 업데이트-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac 및 iOS** <br/> |**버전** <br/> |
||비즈니스용 Skype Mac 클라이언트 버전 16.9  <br/> 비즈니스용 Skype iOS 클라이언트 버전 6.16  <br/> |
|**Android** <br/> |**버전** <br/> |
||비즈니스용 Skype Android 클라이언트 버전 6.17  <br/> |
|**Lync Phone Edition** <br/> |**버전** <br/> |
|| Aastra 6721ip 및 Aastra 6721ip 전화-9 월 2016 누적 업데이트 (빌드 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 및 HP 4120 전화기-9 월 2016 누적 업데이트 (빌드 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 및 Polycom CX3000 전화-9 월 2016 누적 업데이트 (빌드 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

