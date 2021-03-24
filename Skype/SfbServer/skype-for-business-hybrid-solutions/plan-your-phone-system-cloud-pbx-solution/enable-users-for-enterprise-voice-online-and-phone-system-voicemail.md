---
title: 사용자가 전화 시스템 음성 사서함과 온라인으로 Enterprise Voice를 사용하도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
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
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 비즈니스용 Skype 사용자에 대해 전화 시스템 음성 서비스를 사용하도록 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098574"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>사용자가 전화 시스템 음성 사서함과 온라인으로 Enterprise Voice를 사용하도록 설정
 
> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.  직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)

비즈니스용 Skype 사용자에 대해 전화 시스템 음성 서비스를 사용하도록 설정하는 방법을 배워야 합니다.
  
전화 시스템을 배포하는 마지막 단계는 사용자가 전화 시스템 및 음성메일을 사용할 수 있도록 설정하는 것입니다. 이러한 기능을 사용하려면 전역 관리자 역할이 있는 사용자로, 원격 PowerShell을 실행할 수 있어야 합니다. 비즈니스용 Skype Online에 대해 아직 사용하도록 설정되지 않은 모든 사용자 계정에 대해 이 Enterprise Voice 단계를 따라야 합니다.
  
## <a name="enable-phone-system-voice-services"></a>전화 시스템 음성 서비스 사용

사용자가 전화 시스템 음성 및 음성메일을 사용할 수 있도록 설정하려면 서버에 비즈니스용 Skype Online 커넥터가 배포되어 있으며 사용자가 호스팅된 음성메일을 사용할 수 있도록 설정하는 등 초기 단계를 수행해야 합니다.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>사용자가 전화 시스템 음성 및 음성메일을 사용할 수 있도록 설정하려면

> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

1. 시작하기 전에 Teams PowerShell 모듈이 프런트 엔드 서버에 설치되어 있는지 확인합니다. 그렇지 않은 경우 Teams PowerShell 모듈 설치의 지침을 [사용하여 설치하세요.](/microsoftteams/teams-powershell-install)
    
2. 관리자 Windows PowerShell 시작
    
3. 다음을 입력하고 Enter를 입력합니다.
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Set-CsUser cmdlet을 사용하여 $EnterpriseVoiceEnabled $HostedVoiceMail 속성을 사용자에게 할당할 수 있습니다.
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    예:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 또한 SIP 주소, UPN(사용자 계정 이름), 도메인 이름 및 사용자 이름(도메인\사용자 이름) 및 Active Directory의 표시 이름("Bob Kelly")으로 사용자를 지정할 수도 있습니다. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>전화 시스템에 대해 사용하도록 설정된 사용자의 줄 URI 및 다이얼 플랜 업데이트

이 섹션에서는 전화 시스템에 대해 사용하도록 설정된 사용자의 줄 URI 및 다이얼 플랜을 업데이트하는 방법을 설명합니다. 
  
### <a name="to-update-the-line-uri"></a>줄 URI를 업데이트합니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 시작 메뉴 또는 데스크톱 바로 가기를 사용하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.
    
    > [!NOTE]
    > 브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다. 
  
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.
    
5. 표에서 줄 URI를 변경할 비즈니스용 Skype 사용자 계정을 클릭합니다.
    
6. 줄 **URI를 클릭하고** 고유한 정규화된 전화 번호(예: tel:+14255550200)를 입력합니다. 그런 다음 **커밋을 클릭합니다.**
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>프레미스 cmdlet을 사용하여 다이얼 Windows PowerShell 업데이트

[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet과 함께 사용자 Windows PowerShell 다이얼 플랜을 할당할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버의 원격 세션에서 Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>단일 사용자에게 사용자당 다이얼 플랜을 할당하는 경우

- [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용하여 사용자 Ken Myer에게 사용자당 다이얼 플랜 RedmondDialPlan을 할당합니다.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>여러 사용자에게 사용자당 다이얼 플랜을 할당하는 경우

- 다음 명령은 사용자당 다이얼 플랜 RedmondDialPlan을 Redmond 시에서 작업하는 모든 사용자에게 할당합니다. 이 명령에 사용되는 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet에 대한 설명서를 참조하십시오.
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 온라인 사용자에 대해 전역 또는 사용자 다이얼 플랜을 사용할 수 있습니다. 사이트 다이얼 플랜을 사용할 수는 없습니다. 이러한 계획은 프레미스에서 호스팅되는 사용자에게만 적용될 수 있으며, 이러한 요금제는 사내 사이트에 할당된 사용자에게만 적용됩니다. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>사용자당 다이얼 플랜의 이지정을 확정하지 않은 경우

- [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용하여 이전에 Ken Myer에게 할당된 사용자당 다이얼 플랜의 할당을 할당을 중단할 수 있습니다. 사용자당 다이얼 플랜이 할당되지 않은 후 Ken Myer는 등록자 또는 PSTN 게이트웨이에 할당된 서비스 범위 다이얼 플랜 또는 전역 다이얼 플랜을 사용하여 자동으로 관리됩니다. 서비스 범위 다이얼 플랜은 전역 다이얼 플랜보다 우선합니다.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>cmdlet을 사용하여 음성 라우팅 정책 Windows PowerShell 업데이트

이 섹션에서는 전화 시스템에 대해 사용하도록 설정된 사용자에 대한 음성 라우팅 정책을 업데이트하는 방법에 대해 설명합니다.
  
통화가 성공적으로 라우팅될 수 있도록 전화 시스템 사용자에게 음성 라우팅 정책이 할당되어 있어야 합니다. 이는 통화가 성공적으로 라우팅될 수 있도록 음성 정책을 할당해야 하는 사내 비즈니스 음성 사용자와는 다릅니다. 음성 라우팅 정책에는 전화 시스템 사용자에 대해 인증된 통화 및 경로를 정의하는 PSTN 사용법이 포함되어야 합니다. 이러한 PSTN 사용법을 기존 음성 정책에서 새 음성 라우팅 정책으로 복사할 수 있습니다. 자세한 내용은 [New-CsVoiceRoutingPolicy를 참조하세요.](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)
  
> [!NOTE]
> 모든 전화 시스템 사용자에게 허용되는 통화 기능을 정의하는 BusinessVoice라는 온라인 음성 정책이 할당됩니다. 예를 들어 동시 벨 울림을 허용합니다. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>단일 사용자에게 사용자당 음성 라우팅 정책을 할당하기 위해

- [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet을 사용하여 사용자 Ken Myer에게 사용자당 음성 라우팅 정책 RedmondVoiceRoutingPolicy를 할당합니다.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>여러 사용자에게 사용자당 음성 라우팅 정책을 할당하기 위해

- 다음 명령은 Redmond 시에서 작업하는 모든 사용자에게 사용자당 음성 라우팅 정책 RedmondVoiceRoutingPolicy를 할당합니다. 이 명령에 사용되는 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser를 참조하세요.](/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 온라인 사용자에 대해 전역 또는 사용자 음성 라우팅 정책을 사용할 수 있습니다. 사이트 음성 라우팅 정책은 이러한 정책이 프레미스에서 호스팅되는 사용자에게만 적용되어 있으며, 이 정책은 사내 사이트에 할당된 사용자에게만 적용될 수 없습니다. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>사용자당 음성 라우팅 정책의 위임

- 이 Grant-CsVoiceRoutingPolicy 사용하여 이전에 Ken Myer에게 할당된 사용자당 음성 라우팅 정책의 할당을 해지할 수 있습니다. 사용자당 음성 라우팅 정책의 사용이 자동으로 설정되지 않은 경우 Ken Myer는 전역 음성 라우팅 정책을 사용하여 자동으로 관리됩니다.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    자세한 내용은 [Grant-CsVoiceRoutingPolicy를 참조하세요.](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)
