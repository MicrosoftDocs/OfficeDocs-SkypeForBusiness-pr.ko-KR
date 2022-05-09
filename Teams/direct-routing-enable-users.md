---
title: 직접 라우팅에 대한 사용자 사용
ms.reviewer: filippse
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
description: 사용자가 Microsoft Teams 전화 직접 라우팅을 사용하도록 설정하는 방법을 알아봅니다.
ms.openlocfilehash: edf02077bf5c15da56fe7894d1faec2a9b87b0d5
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284083"
---
# <a name="enable-users-for-direct-routing"></a>직접 라우팅에 대한 사용자 사용

이 문서에서는 사용자가 직접 라우팅을 사용하도록 설정하는 방법을 설명합니다. 직접 라우팅을 구성하기 위한 다음 단계 중 2단계입니다.

- 1단계. [전화 시스템 사용하여 SBC 커넥트 연결의 유효성을 검사합니다.](direct-routing-connect-the-sbc.md) 
- **2단계. 직접 라우팅에 대한 사용자 사용**   (이 문서)
- 3단계. [음성 라우팅 구성](direct-routing-voice-routing.md)
- 4단계. [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md) 


직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 [직접 라우팅 구성을 참조하세요](direct-routing-configure.md).

사용자가 직접 라우팅을 사용하도록 설정할 준비가 되면 다음 단계를 수행합니다. 

1. Microsoft 365 사용자를 만들고 전화 시스템 라이선스를 할당합니다.  
2. 사용자가 온라인 상태가 되었는지 확인합니다.
3. 전화 번호를 구성하고 엔터프라이즈 음성을 사용하도록 설정합니다. 
4. 사용자에게 Teams 전용 모드를 할당합니다.

## <a name="create-a-user-and-assign-the-license"></a>사용자 만들기 및 라이선스 할당

Microsoft 365 새 사용자를 만들기 위한 두 가지 옵션이 있습니다. 그러나 조직에서 라우팅 문제를 방지하기 위해 한 가지 옵션을 선택하는 것이 좋습니다. 

- 온-프레미스 Active Directory 사용자를 만들고 사용자를 클라우드에 동기화합니다. [온-프레미스 디렉터리를 Azure Active Directory 통합](/azure/active-directory/connect/active-directory-aadconnect)을 참조하세요.
- Microsoft 365 관리 센터 직접 사용자를 만듭니다. Microsoft 365 [또는 Office 365 개별적으로 또는 대량으로 사용자 추가 - 관리자 도움말](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)을 참조하세요. 

비즈니스용 Skype Online 배포가 비즈니스용 Skype 2015 또는 Lync 2010 또는 2013 온-프레미스와 공존하는 경우 지원되는 유일한 옵션은 온-프레미스 Active Directory 사용자를 만들고 사용자를 클라우드에 동기화하는 것입니다(옵션 1). 

라이선스 요구 사항에 대한 자세한 내용은 [플랜 직접 라우팅](direct-routing-plan.md)의 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements) 참조하세요.

## <a name="ensure-that-the-user-is-homed-online"></a>사용자가 온라인 홈인지 확인 

이 단계는 Teams 직접 라우팅으로 마이그레이션되는 비즈니스용 Skype 서버 Enterprise Voice 사용하도록 설정된 사용자에게 적용됩니다.

직접 라우팅을 사용하려면 사용자가 온라인 홈을 사용해야 합니다. infra.lync.com 도메인에 값이 있어야 하는 RegistrarPool 매개 변수를 확인하여 확인할 수 있습니다. 사용자를 Teams 직접 라우팅으로 마이그레이션할 때 LineURI를 온-프레미스에서 온라인으로 변경하는 것이 좋지만 필요하지는 않습니다. 

1. Microsoft Teams PowerShell 세션을 커넥트.

2. 다음 명령을 실행합니다. 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    OnPremLineUri가 <E.164 전화 번호> 채워지면 전화 번호가 온-프레미스에 할당되고 Microsoft 365 동기화됩니다. 온라인으로 전화 번호를 관리하려면 온-프레미스 비즈니스용 Skype 관리 셸을 사용하여 매개 변수를 지우고 Teams PowerShell을 사용하여 전화 번호를 구성하기 전에 Microsoft 365 동기화합니다. 

1. 비즈니스용 Skype 관리 셸에서 다음 명령을 실행합니다. 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > EnterpriseVoiceEnabled를 False로 설정하지 마세요. 레거시 비즈니스용 Skype 휴대폰이 사용 중이고 테넌트 하이브리드 구성이 UseOnPremDialPlan $True 설정된 경우 전화 걸기 계획 정규화 문제가 발생할 수 있으므로 EnterpriseVoiceEnabled를 False로 설정하지 마세요. 
    
   변경 내용이 Microsoft 365 동기화된 후 예상되는 출력 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri` 은 다음과 같습니다.

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > 온[-프레미스 비즈니스용 Skype 환경을 디코딩](/skypeforbusiness/hybrid/decommission-on-prem-overview)하기 전에 모든 사용자의 전화 특성을 온라인으로 관리해야 합니다. 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>전화 번호 구성 및 엔터프라이즈 음성 사용 

사용자를 만들고 라이선스를 할당한 후에는 사용자의 온라인 전화 설정을 구성해야 합니다. 사용자에 대한 클라우드 음성 사서함 구성은 자동이므로 다른 구성을 수행할 필요가 없습니다.

Teams 관리 센터를 사용하거나 Teams PowerShell을 사용하여 전화 번호를 구성할 수 있습니다.

### <a name="use-teams-admin-center"></a>Teams 관리 센터 사용

1. **UsersManage** ->  **사용자** 로 이동합니다.

2. 사용자를 선택합니다.

2. **계정** **일반 정보** 에서 **편집** 을 선택합니다.

3. **전화 번호 할당** 의 **전화 번호 유형** 드롭다운 메뉴에서 **직접 라우팅을** 선택합니다.

4. 해당하는 경우 할당된 전화 번호와 전화 번호 확장을 입력합니다.

5. **적용을 선택합니다.**

이제 계정 일반 정보에 할당된 전화 번호와 직접 라우팅이 전화 번호 유형으로 표시됩니다.


### <a name="use-powershell"></a>PowerShell 사용

1. Microsoft Teams PowerShell 세션에 커넥트. 

2. 다음 단계는 온-프레미스 또는 온라인에서 사용자의 전화 번호를 관리하는지 여부에 따라 달라집니다. 온-프레미스에서 전화 번호를 관리하는 경우 온-프레미스 비즈니스용 Skype Management Shell, 제어판 또는 [서비스 해제 후 특성을 관리하는 방법 결정](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)에서 설명한 방법 중 하나를 사용해야 합니다.

   - 온-프레미스에서 사용자의 전화 번호를 관리하는 경우 다음 명령을 사용하여 사용자가 온라인에서 Enterprise Voice 사용하도록 설정되어 있는지 확인해야 합니다.

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - 온라인으로 사용자의 전화 번호를 관리하는 경우 Teams PowerShell에서 다음 명령을 사용하여 사용자에게 전화 번호를 할당해야 합니다. 사용자는 다음 명령을 통해 자동으로 Enterprise Voice 사용하도록 설정됩니다. 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       예를 들어 사용자 "Spencer Low"에 대한 전화 번호를 추가하려면 다음을 입력합니다. 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       사용자 "Spencer Low" 및 "Stacy Quinn"이 동일한 기본 번호를 고유한 확장과 공유하는 경우 다음을 입력합니다.
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft는 전화 번호가 국가 코드를 사용하여 전체 E.164 전화 번호로 구성되도록 권장하지만 필요하지는 않습니다. 확장명으로 전화 번호를 구성할 수 있습니다. 이러한 확장은 기본 번호에 대한 조회가 둘 이상의 결과를 반환할 때 사용자를 조회하는 데 사용됩니다. 이 기능을 사용하면 회사에서 동일한 기본 번호와 고유한 확장명으로 전화 번호를 구성할 수 있습니다. 조회에 성공하려면 다음과 같이 초대에 확장이 포함된 전체 번호가 포함되어야 합니다.
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>음성 메일로 직접 통화 보내기 구성

직접 라우팅을 사용하면 사용자에 대한 통화를 종료하고 사용자의 음성 메일로 직접 보낼 수 있습니다. 음성 메일에 직접 전화를 보내려면 요청 URI 헤더에 opaque=app:voicemail을 연결합니다. 예를 들어 "sip:user@yourdomain.com;opaque=app:voicemail"입니다. Teams 사용자는 통화 알림을 받지 못합니다. 대신 통화가 사용자의 음성 메일에 직접 연결됩니다.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>사용자에게 Teams 전용 모드를 할당하여 통화가 Microsoft Teams

직접 라우팅을 사용하려면 사용자가 Teams 전용 모드에 있어야 수신 호출이 Teams 클라이언트에 연결됩니다. 사용자를 Teams 전용 모드로 전환하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다. 자세한 내용은 [IT 관리자를 위한 업그레이드 전략을 참조하세요](upgrade-to-teams-on-prem-implement.md). 조직에서 비즈니스용 Skype 서버 사용하는 경우 Skype Teams 간의 상호 운용성에 대한 자세한 내용은 다음 문서를 참조하세요. [마이그레이션 및 비즈니스용 Skype 상호 운용성](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
