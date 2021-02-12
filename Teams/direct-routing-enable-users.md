---
title: 직접 라우팅에 대해 사용자 사용
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone System 직접 라우팅을 사용하도록 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655485"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>사용자가 직접 라우팅, 음성 및 음성을 사용할 수 있도록 설정

이 문서에서는 사용자가 전화 시스템 직접 라우팅을 사용하도록 설정하는 방법을 설명하고 있습니다.  직접 라우팅을 구성하기 위한 다음 단계의 2단계입니다.

- 1단계. [Microsoft Phone System에 SBC 연결 및 연결 유효성 검사](direct-routing-connect-the-sbc.md) 
- **2단계. 사용자가 직접 라우팅,**   음성 및 음성을 사용할 수 있도록 설정(이 문서)
- 3단계. [음성 라우팅 구성](direct-routing-voice-routing.md)
- 4단계. [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md) 


직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)

직접 라우팅에 사용자를 사용하도록 설정할 준비가 되면 다음 단계를 수행합니다. 

1. Microsoft 365 또는 Office 365에서 사용자를 만들고 전화 시스템 라이선스를 할당합니다. 
2. 사용자가 비즈니스용 Skype Online에 있는지 확인 
3. 전화 번호를 구성하고 엔터프라이즈 음성 및 음성 번호를 사용하도록 설정합니다. 
4. 사용자에게 Teams 전용 모드를 할당합니다.

## <a name="create-a-user-and-assign-the-license"></a>사용자 만들기 및 라이선스 할당 

Microsoft 365 또는 Office 365에서 새 사용자를 만들기 위한 두 가지 옵션이 있습니다. 그러나 라우팅 문제를 방지하기 위해 조직에서 한 가지 옵션을 선택하는 것이 좋습니다. 

- 사용자를 프레미스 Active Directory에서 만들고 사용자를 클라우드에 동기화합니다. Azure Active Directory와의 Azure 프레미스 [디렉터리 통합을 참조하세요.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- Microsoft 365 관리 센터에서 직접 사용자를 만들 수 있습니다. [Microsoft 365 또는 Office 365에](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)개별적으로 또는 대량으로 사용자 추가 - 관리자 도움말을 참조하세요. 

비즈니스용 Skype Online 배포가 비즈니스용 Skype 2015 또는 Lync 2010 또는 2013 온-프레미스와 공존하는 경우 지원되는 유일한 옵션은 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드에 동기화하는 것입니다(옵션 1). 

라이선스 요구 사항에 대한 자세한 내용은 [계획](direct-routing-plan.md#licensing-and-other-requirements) 직접 라우팅의 라이선스 및 기타 요구 [사항을 참조하세요.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>사용자가 온라인에 있는 경우 전화 번호가 프레미스에서 동기화되지 않는지 확인합니다(Teams 직접 라우팅으로 마이그레이션되는 비즈니스용 Skype Server Enterprise Voice 가능)

직접 라우팅을 사용하려면 사용자가 온라인에 연결해야 합니다. 레지스트리 도메인에 값이 필요한 RegistrarPool 매개 변수를 확인하여 확인할 infra.lync.com 있습니다. OnPremLineUriManuallySet 매개 변수도 True로 설정해야 합니다. 이는 전화 번호를 구성하고 비즈니스용 Skype Online PowerShell을 사용하여 엔터프라이즈 음성 및 음성을 사용하도록 설정하여 달성됩니다.

1. 비즈니스용 Skype Online PowerShell 세션을 연결합니다.

2. 명령을 실행합니다. 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    OnPremLineUriManuallySet이 False로 설정되고 LineUri가 <E.164 전화 번호로> 경우 비즈니스용 Skype Online PowerShell을 사용하여 전화 번호를 구성하기 전에 비즈니스용 Skype 관리 셸을 사용하여 매개 변수를 정리하세요. 

1. 비즈니스용 Skype 관리 셸에서 다음 명령을 실행합니다. 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   변경 내용이 Office 365와 동기화된 후 예상되는 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 출력은

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>전화 번호 구성 및 엔터프라이즈 음성 및 음성 이메일 사용 

사용자를 만들어 라이선스를 할당한 후 다음 단계는 사용자의 전화 번호와 음성 번호를 구성하는 것입니다. 

전화 번호를 추가하고 음성메일을 사용하도록 설정하려면:
 
1. 비즈니스용 Skype Online PowerShell 세션을 연결합니다. 

2. 명령을 실행합니다. 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    예를 들어 "Spencer Low" 사용자에 대한 전화 번호를 추가하기 위해 다음을 입력합니다. 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    "Spencer Low" 및 "Stacy Quinn" 사용자가 고유 확장명과 동일한 기본 번호를 공유하는 경우 다음을 입력합니다.
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    사용되는 전화 번호는 국가 코드가 있는 전체 E.164 전화 번호로 구성되는 것이 좋습니다. 기본 번호에 대한 Lookup이 두 개 이상의 결과를 반환할 때 사용자를 찾아보는 데 사용되는 내선 번호를 사용하여 전화 번호를 구성할 수 있습니다. 이렇게 하면 회사에서 동일한 기본 번호 및 고유 확장명으로 전화 번호를 구성할 수 있습니다. 보기가 성공하려면 다음과 같이 확장명과 함께 전체 번호를 초대에 포함해야 합니다.
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > 사용자의 전화 번호가 프레미스에서 관리되는 경우, 비즈니스용 Skype 관리 셸 또는 제어판을 사용하여 사용자의 전화 번호를 구성합니다. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>음성 메일로 직접 통화 보내기 구성

직접 라우팅을 사용하면 사용자에 대한 통화를 종료하고 사용자의 음성 메일로 직접 보낼 수 있습니다. 음성 메일로 직접 통화를 보내고 싶은 경우 요청 URI 헤더에 opaque=app:voicemail을 첨부합니다. 예를 들어 "sip:user@yourdomain.com;opaque=app:voicemail"입니다. 이 경우 Teams 사용자는 통화 알림을 받지 못하고 통화는 사용자의 음성 메일에 직접 연결됩니다.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>사용자에게 Teams 전용 모드를 할당하여 통화가 Microsoft Teams에 오게 합니다.

직접 라우팅을 사용하려면 사용자가 Teams 전용 모드로 전환해야 수신 전화가 Teams 클라이언트에 연결되도록 할 수 있습니다. 사용자를 Teams 전용 모드로 전환하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다. 자세한 내용은 IT 관리자에 대한 업그레이드 [지침을 참조하세요.](upgrade-to-teams-on-prem-overview.md) 조직에서 비즈니스용 Skype Server 또는 비즈니스용 Skype Online을 사용하는 경우 Skype와 Teams 간의 상호 연동성에 대한 자세한 내용은 다음 문서를 [참조하세요.](migration-interop-guidance-for-teams-with-skype.md)비즈니스용 Skype와의 마이그레이션 및 상호 연동성.

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
