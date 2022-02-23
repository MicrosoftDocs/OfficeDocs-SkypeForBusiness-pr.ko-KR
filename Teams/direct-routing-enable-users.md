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
description: 사용자가 직접 라우팅을 사용하도록 Microsoft Teams 전화 방법을 알아보습니다.
ms.openlocfilehash: be2f0e0f33bd236591c8c8a2d9cf415972e018d6
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926301"
---
# <a name="enable-users-for-direct-routing"></a>직접 라우팅에 대한 사용자 사용

이 문서에서는 직접 라우팅에 대해 사용자를 사용하도록 설정하는 방법을 설명합니다. 직접 라우팅을 구성하기 위한 다음 단계의 2단계입니다.

- 1단계. [커넥트 SBC를 전화 시스템 확인](direct-routing-connect-the-sbc.md) 
- **2단계. 직접 라우팅에 사용자**   사용(이 문서)
- 3단계. [음성 라우팅 구성](direct-routing-voice-routing.md)
- 4단계. [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md) 


직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 직접 라우팅 [구성을 참조하세요](direct-routing-configure.md).

직접 라우팅에 사용자를 사용하도록 설정할 준비가 된 경우 다음 단계를 따릅니다. 

1. 사용자 지정에서 사용자를 Microsoft 365 라이선스를 전화 시스템 할당합니다.  
2. 사용자가 온라인에 홈이 되도록 합니다.
3. 전화 번호를 구성하고 엔터프라이즈 음성을 사용하도록 설정합니다. 
4. 사용자에게 Teams 전용 모드를 할당합니다.

## <a name="create-a-user-and-assign-the-license"></a>사용자 만들기 및 라이선스 할당

새 사용자를 만들기 위한 두 가지 옵션이 Microsoft 365. 그러나 조직에서 라우팅 문제를 방지하기 위해 한 가지 옵션을 선택하는 것이 좋습니다. 

- 프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드에 동기화합니다. [프레미스와 프레](/azure/active-directory/connect/active-directory-aadconnect)미스 Azure Active Directory.
- 사용자 직접 Microsoft 365 관리 센터. 사용자 추가를 개별적으로 또는 일괄적으로 참조하여 Microsoft 365 또는 Office 365 [관리자 도움말을 참조하세요](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

온라인 비즈니스용 Skype 비즈니스용 Skype 2015 또는 Lync 2010 또는 2013 온-프레미스와 온라인 배포가 공존하는 경우 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드에 동기화하는 유일한 옵션입니다(옵션 1). 

라이선스 요구 사항에 대한 자세한 내용은 계획 [](direct-routing-plan.md#licensing-and-other-requirements) 직접 라우팅의 라이선스 및 기타 [요구 사항을 참조하세요](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>사용자가 온라인에 홈이 되도록 합니다. 

이 단계는 직접 라우팅으로 비즈니스용 Skype 서버 Enterprise Voice 활성화된 사용자에 Teams 적용됩니다.

직접 라우팅을 사용하려면 사용자가 온라인으로 홈으로 돌아와야 합니다. 도메인에 값이 필요한 RegistrarPool 매개 변수를 확인하여 확인할 infra.lync.com 있습니다. 사용자를 직접 라우팅으로 마이그레이션할 때 LineURI를 온라인에서 온라인으로 변경하는 것이 Teams 권장되지만 필요하지 않습니다. 

1. 커넥트 PowerShell Microsoft Teams 세션을 제공합니다.

2. 명령을 실행합니다. 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    OnPremLineUriManuallySet이 False로 설정되고 Line <Uri에 E.164 전화 번호> 번호가 채워진 경우 전화 번호가 Microsoft 365. 전화 번호를 온라인으로 관리하려는 경우 PowerShell을 사용하여 전화 번호를 구성하기 비즈니스용 Skype 프레미스 비즈니스용 Skype Teams 사용하여 매개 변수를 Microsoft 365 동기화합니다. 

1. 관리 비즈니스용 Skype 셸에서 명령을 실행합니다. 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > 이를 위한 요구 사항이 없는 경우 EnterpriseVoiceEnabled를 False로 설정하지 말고 레거시 비즈니스용 Skype 휴대폰이 사용 중일 때 테넌트 하이브리드 구성이 UseOnPremDialPlan을 사용하여 설정되어 있는 경우 계획 정규화 $True. 
    
   변경 내용이 동기화된 Microsoft 365 출력은 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 다음입니다.

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > 모든 사용자의 전화 특성은 온라인에서 관리되어야만 프레미스 비즈니스용 Skype [합니다](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>전화 번호 구성 및 엔터프라이즈 음성 사용 

사용자를 만들어 라이선스를 할당한 후 사용자의 온라인 전화 설정을 구성해야 합니다. 사용자에 대한 클라우드 음성 사서함 구성은 자동으로 수행됩니다. 추가 구성을 완료할 필요가 없습니다.

관리자 센터를 사용하여 전화 번호를 구성하거나 Teams PowerShell을 사용하여 전화 Teams 수 있습니다.

### <a name="use-teams-admin-center"></a>관리 Teams 사용

1. **UsersManage 사용자** -> **로 이동합니다**.

2. 사용자를 선택합니다.

2. 계정 **일반** **정보에서** 편집을 **선택합니다**.

3. 전화 **번호 할당** 에서 번호 전화 드롭  다운 메뉴에서 직접 라우팅 **을 선택합니다**.

4. 앱에 할당된 전화 번호 및 전화 번호 확장을 입력합니다.

5. 적용을 **선택합니다.**

이제 계정 일반 정보가 할당된 전화 번호 및 직접 라우팅을 전화 번호 유형으로 표시됩니다.


### <a name="use-powershell"></a>PowerShell 사용

1. 커넥트 PowerShell Microsoft Teams 합니다. 

2. 다음 단계는 사용자의 전화 번호를 온라인에서 관리하는지 여부에 따라 결정됩니다. 전화 번호를온-프레미스에서 관리하는 경우 관리 셸, 제어판 또는 디모전 후 특성을 관리하는 방법 결정에 설명된 방법 중 비즈니스용 Skype 관리 프레미스 및 관리 프레미스를 사용해야 [합니다](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes).

   - 사용자의 전화 번호를 관리하는 경우 다음 명령을 사용하여 사용자가 온라인에서 Enterprise Voice 사용하도록 설정되어 있는지 확인해야 합니다.

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - 온라인에서 사용자의 전화 번호를 관리하는 경우 PowerShell에서 다음 명령을 사용하여 사용자에게 전화 번호를 Teams 합니다. 사용자가 명령에 Enterprise Voice 자동으로 활성화됩니다. 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       예를 들어 "Spencer Low"에 대한 전화 번호를 추가하면 다음을 입력합니다. 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       사용자가 "Spencer Low" 및 "Stacy Quinn"이 고유 확장과 동일한 기본 번호를 공유하는 경우 다음을 입력합니다.
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft는 전화 번호가 국가 코드가 있는 전체 E.164 전화 번호로 구성되는 것이 좋습니다. 확장을 사용하여 전화 번호를 구성할 수 있습니다. 이러한 확장은 기본 번호에 대한 룩업이 두 개 이상의 결과를 반환할 때 사용자를 찾아보는 데 사용됩니다. 이 기능을 사용하면 회사에서 동일한 기본 번호 및 고유 확장으로 전화 번호를 구성할 수 있습니다. 보기가 성공하려면 다음과 같이 확장이 포함된 전체 번호를 포함해야 합니다.
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>음성 메일에 직접 통화 보내기 구성

직접 라우팅을 사용하면 사용자에 대한 통화를 종료하고 사용자의 음성 메일로 직접 보낼 수 있습니다. 음성 메일에 직접 전화를 보내고 싶은 경우 요청 URI 헤더에 opaque=app:voicemail을 연결합니다. 예를 들어 "sip:user@yourdomain.com;opaque=app:voicemail"을 예로 들 수 있습니다. Teams 사용자가 호출 알림을 받지 못하고 통화가 사용자의 음성 메일에 직접 연결됩니다.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>사용자에게 Teams 전용 모드를 할당하여 호출이 Microsoft Teams

직접 라우팅을 사용하려면 사용자가 Teams 클라이언트에서 들어오는 호출이 Teams 수 있습니다. 사용자를 Teams 전용 모드로 전환하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다. 자세한 내용은 IT 관리자에 대한 업그레이드 전략을 [참조하세요](upgrade-to-teams-on-prem-implement.md). 조직에서 비즈니스용 Skype 서버 경우 다음 문서를 참조하여 Skype Teams 마이그레이션 및 상호 [비즈니스용 Skype.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
