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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '요약: 이 항목을 통해 사용자에 대해 음성 정책을 할당하는 방법을 전화 시스템 PSTN 연결을 참조하세요.'
ms.openlocfilehash: 158cd8e7bcd996297077adfb2c812febf4dc491b
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563359"
---
# <a name="assign-a-voice-routing-policy"></a>음성 라우팅 정책 할당
 
> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 사용 중지되어 비즈니스용 Skype 서버 또는 Cloud Connector Edition과 비즈니스용 Skype Online을 통해 지원되지 않는 사내 환경 간의 PSTN 연결은 더 이상 지원되지 않습니다.  직접 라우팅 을 사용하여 프레미스 전화 통신 Teams [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)

**요약:** 이 항목을 통해 사용자에 대해 음성 정책을 할당하는 방법에 대해 자세히 전화 시스템 PSTN 연결을 사용할 수 있습니다. 
  
사용자가 온라인에서 비즈니스용 Skype 및 전화 시스템 PSTN 연결에 대한 음성 정책을 사용하는 경우 두 개의 음성 정책이 적용됩니다. 하나는 프레미스에서 할당할 사내 음성 라우팅 정책입니다. 이 정책은 전역 또는 사용자별일 수 있으며 사용자와 연결된 PSTN 사용 레코드를 정의합니다. 이 항목에서는 이 정책을 할당하는 방법에 대해 설명합니다.
  
다른 음성 정책은 사용자가 사용할 수 있는 통화 기능을 정의합니다. 이 음성 정책은 Microsoft에서 정의하며, 모든 전화 시스템 PSTN 연결 사용자에 대해 동일합니다. 이 설정은 사용자에게 전화 시스템 할당됩니다.
  
|&nbsp;|On-premises user|전화 시스템 PSTN 연결 사용자와의 연결|
|:-----|:-----|:-----|
|에 정의된 통화 기능   |음성 정책   |사용자에게 라이선스가 부여될 때 자동으로 할당되는 미리 정의된 음성 전화 시스템.   |
|연결된 PSTN 사용 레코드   |음성 정책   |사용자가 여전히 사내에 있는 동안 할당된 음성 라우팅 정책입니다.   |
   
사용자가 여전히 On-premises deployment에 있는 동안에는 다음 단계를 수행하여 사내 배포를 수행합니다.
  
## <a name="using-a-global-voice-routing-policy"></a>전역 음성 라우팅 정책 사용

전역 음성 라우팅 정책을 전화 시스템 PSTN 연결 사용자와 함께 사용하려면 먼저 정책에 PSTN 사용 레코드를 추가해야 합니다.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>PSTN 사용 레코드를 전역 음성 라우팅 정책에 할당

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 정책에 PSTN 사용 레코드를 추가합니다.
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>새 음성 라우팅 정책 만들기

### <a name="to-create-a-new-voice-routing-policy"></a>새 음성 라우팅 정책을 만들 수 있습니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 새 음성 라우팅 정책을 만들 수 있습니다.
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

이 예에서는 두 개의 PSTN 사용이 연결된 HybridVoice라는 새 음성 라우팅 정책을 만듭니다.
  
## <a name="assigning-a-voice-routing-policy"></a>음성 라우팅 정책 할당

전역 음성 라우팅 정책 또는 사용자별 정책에 상관없이 다음 단계를 사용하여 사용자에게 정책을 할당합니다.
  
### <a name="to-assign-the-voice-routing-policy"></a>음성 라우팅 정책을 할당하기 위해

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 사용자에게 기존 음성 정책을 할당합니다.
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

이 예에서는 표시 이름이 Bob Kelly인 사용자에게 이전에 만든 음성 정책에 HybridVoice가 할당됩니다.
  
음성 라우팅 정책에 대한 자세한 내용은 비즈니스용 Skype [2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy)및 [Grant-CsVoicePolicy에서](/powershell/module/skype/grant-csvoicepolicy)음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성을 참조합니다.
