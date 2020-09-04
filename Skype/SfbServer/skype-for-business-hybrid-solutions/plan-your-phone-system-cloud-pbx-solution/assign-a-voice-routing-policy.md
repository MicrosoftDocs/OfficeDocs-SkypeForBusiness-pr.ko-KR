---
title: 음성 라우팅 정책 할당
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
description: '요약: 온-프레미스 PSTN 연결과 함께 전화 시스템을 사용 하는 사용자에 게 음성 정책을 할당 하는 방법에 대해 알아보려면이 항목을 읽어 보십시오.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359324"
---
# <a name="assign-a-voice-routing-policy"></a>음성 라우팅 정책 할당
 
> [!Important]
> 비즈니스용 Skype Online은 서비스에 더 이상 액세스할 수 없게 되 고, 2021 년 7 월 31 일에 만료 됩니다.  또한 비즈니스용 Skype 서버 또는 클라우드 Connector Edition과 비즈니스용 Skype Online을 통해 온-프레미스 환경 간의 PSTN 연결이 더 이상 지원 되지 않습니다.  [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아봅니다.

**요약:** 온-프레미스 PSTN 연결과 함께 전화 시스템을 사용 하는 사용자에 게 음성 정책을 할당 하는 방법에 대 한 자세한 내용은이 항목을 참조 하십시오. 
  
사용자가 비즈니스용 Skype 온라인에 있고 온-프레미스 PSTN 연결을 통해 전화 시스템을 사용 하는 경우 두 가지 음성 정책이 적용 됩니다. 하나는 온-프레미스 음성 라우팅 정책 (온-프레미스에 할당)입니다. 이 정책은 전역 또는 사용자별 일 수 있으며 사용자와 연결 된 PSTN 사용 레코드를 정의 합니다. 이 항목에서는이 정책을 할당 하는 방법에 대해 설명 합니다.
  
다른 음성 정책은 사용자가 사용할 수 있는 호출 기능을 정의 합니다. 이 음성 정책은 Microsoft에서 정의 되며 온-프레미스 PSTN 연결 사용자가 있는 모든 전화 시스템에서 동일 합니다. 전화 시스템 사용자에 게 자동으로 할당 됩니다.
  
||**온-프레미스 사용자**|**온-프레미스 PSTN 연결 사용자가 있는 전화 시스템**|
|:-----|:-----|:-----|
|통화 기능 정의  <br/> |음성 정책  <br/> |사용자가 전화 시스템에 대해 사용이 허가 될 때 자동으로 할당 되는 미리 정의 된 음성 정책  <br/> |
|연결 된 PSTN 사용 레코드  <br/> |음성 정책  <br/> |사용자가 계속 온-프레미스에 있는 동안 지정 된 음성 라우팅 정책  <br/> |
   
온-프레미스 배포를 사용 하 여 다음 단계를 수행 하는 동안 사용자는 여전히 온-프레미스 배포에 속해 있습니다.
  
## <a name="using-a-global-voice-routing-policy"></a>전역 음성 라우팅 정책 사용

온-프레미스 PSTN 연결 사용자와 전화 시스템에 대해 전역 음성 라우팅 정책을 사용 하기 전에 정책에 PSTN 사용 레코드를 추가 해야 합니다.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>전역 음성 라우팅 정책에 PSTN 사용 레코드를 할당 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.
    
3. 정책에 PSTN 사용 레코드를 추가 합니다.
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    예를 들어,
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>새 음성 라우팅 정책 만들기

### <a name="to-create-a-new-voice-routing-policy"></a>새 음성 라우팅 정책을 만들려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.
    
3. 새 음성 라우팅 정책을 만듭니다.
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    예를 들어,
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

이 예에서는 PSTN을 두 번 사용 하 여 연결 된 HybridVoice 라는 새 음성 라우팅 정책을 만듭니다.
  
## <a name="assigning-a-voice-routing-policy"></a>음성 라우팅 정책 지정

전역 음성 라우팅 정책이 사용 되는지, 아니면 사용자에 게 어떤 관련이 있는지에 관계 없이 다음 단계를 수행 하 여 사용자에 게 정책을 할당 합니다.
  
### <a name="to-assign-the-voice-routing-policy"></a>음성 라우팅 정책을 할당 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.
    
3. 기존 음성 정책을 사용자에 게 할당 합니다.
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들어,
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

이 예에서 표시 이름이 Bob 최소라 인 사용자는 이름이 HybridVoice 인 이전에 만든 음성 정책에 할당 됩니다.
  
음성 라우팅 정책에 대 한 자세한 내용은 [Create or modify a voice policy And 비즈니스용 Skype 2015, get-csvoiceroutingpolicy 및 set-csvoicepolicy에 대 한 PSTN 사용 레코드 구성을](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)참조 하십시오 [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps). [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)
  

