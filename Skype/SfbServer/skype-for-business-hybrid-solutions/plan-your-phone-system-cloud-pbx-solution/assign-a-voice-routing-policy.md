---
title: 음성 라우팅 정책 지정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 요약:이 항목에서는 Office 365에서 온-프레미스 PSTN 연결을 사용 하는 사용자를 위해 음성 정책을 할당 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0e9a39fba8d1db7b70f0422e71223d49917716ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803998"
---
# <a name="assign-a-voice-routing-policy"></a>음성 라우팅 정책 지정
 
**요약:** 이 항목에서는 Office 365에서 온-프레미스 PSTN 연결을 사용 하는 사용자를 위해 음성 정책을 할당 하는 방법에 대해 알아봅니다. 
  
사용자가 비즈니스용 Skype Online을 사용 하 고 있고 온-프레미스 PSTN 연결을 사용 하는 Office 365에서 전화 시스템을 사용할 경우 두 가지 음성 정책이 적용 됩니다. 하나는 온-프레미스 음성 라우팅 정책으로 서, 구내에 할당 됩니다. 이 정책은 전역 또는 사용자에 따라 가능 하며 사용자와 연결 되는 PSTN 사용 레코드를 정의 합니다. 이 항목에서는이 정책을 할당 하는 방법에 대해 설명 합니다.
  
다른 음성 정책은 사용자에 게 제공 되는 통화 기능을 정의 합니다. 이 음성 정책은 Microsoft에서 정의 하며 온-프레미스 PSTN 연결 사용자와 Office 365의 모든 전화 시스템에 대해 동일 합니다. Office 365 사용자의 전화 시스템에 자동으로 할당 됩니다.
  
||**온-프레미스 사용자**|**온-프레미스 PSTN 연결 사용자와 Office 365의 전화 시스템**|
|:-----|:-----|:-----|
|에 정의 된 통화 기능  <br/> |음성 정책  <br/> |사전 정의 된 음성 정책은 사용자가 Office 365에서 전화 시스템을 사용 하도록 허가 받은 경우 자동으로 할당 됩니다.  <br/> |
|와 연결 된 PSTN 사용 레코드  <br/> |음성 정책  <br/> |사용자가 온-프레미스 상태에서 지정 된 음성 라우팅 정책  <br/> |
   
온-프레미스 배포를 사용 하 여 다음 단계를 수행 하는 반면 사용자는 온-프레미스 배포에 남아 있습니다.
  
## <a name="using-a-global-voice-routing-policy"></a>전역 음성 라우팅 정책 사용

Office 365에서 온-프레미스 PSTN 연결 사용자와 함께 전화 시스템에 대 한 전역 음성 라우팅 정책을 사용 하기 전에 정책에 PSTN 사용 레코드를 추가 해야 합니다.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>전역 음성 라우팅 정책에 PSTN 사용 레코드 할당

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 정책에 PSTN 사용 레코드를 추가 합니다.
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>새 음성 라우팅 정책 만들기

### <a name="to-create-a-new-voice-routing-policy"></a>새 음성 라우팅 정책 만들기

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 새 음성 라우팅 정책 만들기:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

이 예제에서는 두 개의 PSTN 용도와 연결 된 HybridVoice 이라는 새 음성 라우팅 정책을 만듭니다.
  
## <a name="assigning-a-voice-routing-policy"></a>음성 라우팅 정책 지정

전역 음성 라우팅 정책 (사용자 관련)을 사용 하는지 여부에 관계 없이 다음 단계를 사용 하 여 정책을 사용자에 게 할당 합니다.
  
### <a name="to-assign-the-voice-routing-policy"></a>음성 라우팅 정책을 할당 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 기존 음성 정책을 사용자에 게 할당 합니다.
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

이 예제에서 표시 이름이 Bob 최소라 인 사용자는 이전에 만든 이름 HybridVoice를 사용 하는 음성 정책에 할당 됩니다.
  
음성 라우팅 정책에 대 한 자세한 내용은 [음성 정책 만들기 또는 수정 및 비즈니스용 Skype 2015, CsVoiceRoutingPolicy 및 CsVoicePolicy에 대 한 PSTN 사용 레코드 구성을](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)참조 하세요. [](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)
  

