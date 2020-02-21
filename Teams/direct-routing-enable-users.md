---
title: 사용자가 직접 라우팅 하도록 설정
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
description: 사용자의 Microsoft 전화 시스템 다이렉트 라우팅을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e9120dcbcd4b1a82eb864f545efdbadc42481794
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157999"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정

이 문서에서는 전화 시스템 다이렉트 라우팅에 대 한 사용자를 설정 하는 방법을 설명 합니다.  직접 라우팅 구성에 대 한 다음 단계 중 2 단계입니다.

- 1 단계. [Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인](direct-routing-connect-the-sbc.md) 
- **2 단계. 사용자가 직접 라우팅, 음성 및 보이스 메일을 사용할 수 있도록 설정** (이 문서)
- 3 단계. [음성 라우팅 구성](direct-routing-voice-routing.md)
- 4 단계. [숫자를 대체 형식으로 번역](direct-routing-translate-numbers.md) 


직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.

사용자가 직접 라우팅을 사용할 준비가 되 면 다음 단계를 따릅니다. 

1. Office 365에서 사용자를 만들고 전화 시스템 라이선스를 할당 합니다. 
2. 사용자가 비즈니스용 Skype Online에 있는지 확인 합니다. 
3. 전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일을 사용 하도록 설정 합니다. 
4. 사용자에 게 팀 전용 모드를 할당 합니다.

## <a name="create-a-user-in-office-365-and-assign-the-license"></a>Office 365에서 사용자를 만들고 라이선스를 할당 합니다. 

Office 365에서 새 사용자를 만드는 두 가지 옵션이 있습니다. 그러나 조직에서 라우팅 문제를 방지 하기 위한 옵션 하나를 선택 하는 것이 좋습니다. 

- 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 합니다. [Azure Active Directory와 온-프레미스 디렉터리 통합](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)을 참조 하세요.
- Office 365 관리자 포털에서 직접 사용자를 만듭니다. [Office 365에 개별적으로 또는 대량으로 사용자 추가-관리자 도움말을](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)참조 하세요. 

비즈니스용 Skype Online 배포가 비즈니스용 Skype 2015 또는 Lync 2010 또는 2013 온-프레미스와 함께 존재 하는 경우 유일 하 게 지원 되는 옵션은 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 (옵션 1) 하는 것입니다. 

라이선스 요구 사항에 대 한 자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md)의 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements) 참조 하세요.

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>사용자가 비즈니스용 Skype Online에 있는지 확인 

직접 라우팅에는 사용자가 비즈니스용 Skype Online에 있어야 합니다. Infra.lync.com 도메인에 값이 있어야 하는 RegistrarPool 매개 변수를 확인 하 여 확인할 수 있습니다.

1. 원격 PowerShell에 연결 합니다.
2. 다음 명령을 실행 합니다. 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일 사용 

사용자를 만들고 라이선스를 할당 한 후 다음 단계는 사용자의 전화 번호와 보이스 메일을 구성 하는 것입니다. 

전화 번호를 추가 하 고 보이스 메일을 사용 하도록 설정 하려면:
 
1. 원격 PowerShell 세션에 연결 합니다. 
2. 명령 입력: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    예를 들어 사용자 "Spencer Low"에 대 한 전화 번호를 추가 하려면 다음을 입력 합니다. 

    ```PowerShell
    Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    사용 된 전화 번호는 국가 코드를 사용 하 여 전체 전자 164 자로 구성 되어야 합니다. 

      > [!NOTE]
      > 사용자의 전화 번호가 온-프레미스에서 관리 되는 경우 온-프레미스 Skype for Business 관리 셸 또는 제어판을 사용 하 여 사용자의 전화 번호를 구성 합니다. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>전화를 음성 메일로 바로 보내는 방법 구성

직접 라우팅이 사용자에 대 한 통화를 종료 하 고 사용자의 음성 메일로 직접 보낼 수 있도록 합니다. 전화를 음성 메일로 바로 보내려면 불투명 = 앱: 보이스 메일을 요청 URI 헤더에 첨부 합니다. 예를 들어 "sip: user@yourdomain .com, 불투명 = 앱: 보이스". 이 경우에는 팀 사용자가 통화 알림을 받지 못할 수 있으며 통화는 사용자의 보이스 메일에 직접 연결 됩니다.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Microsoft 팀에서 전화를 걸 수 있도록 사용자에 게 팀 전용 모드 할당

다이렉트 라우팅은 팀 클라이언트에서 수신 전화를 받을 수 있도록 사용자가 팀 전용 모드에 있어야 합니다. 사용자를 팀 전용 모드로 전환 하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당 합니다. 자세한 내용은 [IT 관리자를 위한 업그레이드 지침](upgrade-to-teams-on-prem-overview.md)을 참조 하세요. 조직에서 비즈니스용 skype Server 또는 비즈니스용 Skype Online을 사용 하는 경우 Skype와 팀 간의 상호 운용성에 대 한 자세한 내용은 다음 문서를 참조 하세요. 비즈니스용 [skype를 통한 마이그레이션 및 상호 운용성](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
