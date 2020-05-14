---
title: 사용자가 Enterprise Voice online 및 전화 시스템 음성 메일을 사용할 수 있도록 설정
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
description: 비즈니스용 Skype 사용자에 대해 전화 시스템 음성 서비스를 사용 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 522da56969f851280812670692a27d94e4df09a8
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221108"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>사용자가 Enterprise Voice online 및 전화 시스템 음성 메일을 사용할 수 있도록 설정
 
비즈니스용 Skype 사용자에 대해 전화 시스템 음성 서비스를 사용 하도록 설정 하는 방법을 알아봅니다.
  
온-프레미스 PSTN 연결을 사용 하 여 전화 시스템을 배포 하는 마지막 단계는 사용자가 전화 시스템 및 음성 메일을 사용할 수 있도록 하는 것입니다. 이러한 기능을 사용 하도록 설정 하려면 전역 관리자 역할을 가진 사용자 여야 하며 원격 PowerShell을 실행할 수 있어야 합니다. 비즈니스용 Skype Online에 Enterprise Voice가 사용 하도록 설정 되어 있지 않은 모든 사용자 계정에 대해이 항목의 단계를 수행 해야 합니다.
  
## <a name="enable-phone-system-voice-services"></a>전화 시스템 음성 서비스 사용

사용자가 전화 시스템 음성 및 음성 메일을 사용할 수 있도록 설정 하려면 비즈니스용 Skype Online 커넥터가 서버에 배포 되어 있는지 확인 하 고 사용자가 호스팅된 음성 메일을 사용할 수 있도록 하는 등의 초기 단계를 수행 해야 합니다.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>사용자가 전화 시스템 음성 및 음성 메일을 사용할 수 있도록 설정 하려면

1. 시작 하기 전에 비즈니스용 Skype Online 커넥터 (Windows PowerShell 모듈)가 프런트 엔드 서버에 배포 되었는지 확인 합니다. 그렇지 않은 경우 [다운로드 센터](https://www.microsoft.com/download/details.aspx?id=39366)에서 다운로드할 수 있습니다. 이 모듈을 사용 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype Online 관리를 위한 컴퓨터 구성](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx)에서 확인할 수 있습니다.
    
2. 관리자 권한으로 Windows PowerShell을 시작 합니다.
    
3. 다음을 입력 하 고 enter 키를 누릅니다.
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. 다음을 입력 하 고 enter 키를 누릅니다.
    
   ```powershell
   $cred = Get-Credential
   ```

    Enter 키를 누르면 Windows PowerShell 자격 증명 대화 상자가 표시 됩니다.
    
5. 테 넌 트 관리자 사용자 이름 및 암호를 입력 하 고 **확인**을 클릭 합니다.
    
6. PowerShell 창에서 다음을 입력 하 고 enter 키를 누릅니다.
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. 다음 cmdlet을 입력 하 여 세션을 가져옵니다.
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    비즈니스용 Skype 서버에서 PowerShell을 실행할 때 PowerShell을 열면 로컬 비즈니스용 Skype cmdlet이 이미 로드 된 것입니다. 온라인 cmdlet이 온-프레미스 cmdlet을 같은 이름으로 덮어쓰도록 허용 하려면-AllowClobber 매개 변수를 지정 해야 합니다.
    
8. $EnterpriseVoiceEnabled 및 $HostedVoiceMail 속성을 다음과 같이 사용자에 게 할당 하려면 CsUser cmdlet을 사용 합니다.
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    예시는 다음과 같습니다:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 또한 SIP 주소, UPN (사용자 계정 이름), 도메인 이름 및 사용자 이름 (domain\username) 및 Active Directory의 표시 이름 ("Bob 최소라")을 사용 하 여 사용자를 지정할 수 있습니다. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>전화 시스템을 사용할 수 있는 사용자에 대 한 줄 URI 및 다이얼 플랜 업데이트

이 섹션에서는 전화 시스템을 사용할 수 있는 사용자에 대 한 줄 URI 및 다이얼 플랜을 업데이트 하는 방법에 대해 설명 합니다. 
  
### <a name="to-update-the-line-uri"></a>줄 URI를 업데이트 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 시작 메뉴 또는 바탕 화면 바로 가기를 사용 하 여 비즈니스용 Skype 서버 제어판을 엽니다.
    
    > [!NOTE]
    > 브라우저 창을 연 다음 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 열 수도 있습니다. 
  
3. 왼쪽 탐색 모음에서 **사용자**를 클릭합니다.
    
4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.
    
5. 표에서 줄 URI를 변경 하려는 비즈니스용 Skype 사용자 계정을 클릭 합니다.
    
6. **줄 URI**를 클릭 하 고 정규화 된 고유 전화 번호를 입력 합니다 (예: tel-+ 14255550200). 그런 다음 **커밋을**클릭 합니다.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>온-프레미스 Windows PowerShell cmdlet을 사용 하 여 다이얼 플랜 업데이트

Windows PowerShell 및 [부여-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 사용자별 다이얼 플랜을 할당할 수 있습니다. 비즈니스용 Skype 서버 2015 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>단일 사용자에 게 사용자별 다이얼 플랜을 할당 하려면

- [부여-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 사용자 Ken Myer에 게 사용자별 다이얼 플랜 RedmondDialPlan를 할당 합니다.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>여러 사용자에 게 사용자별 다이얼 플랜을 할당 하려면

- 다음 명령은 Redmond의 도시에서 근무 하는 모든 사용자에 게 사용자별 다이얼 플랜 RedmondDialPlan를 할당 합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 다음을 참조 하십시오 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 온라인 사용자에 게는 전역 또는 사용자 다이얼 플랜을 사용할 수 있습니다. 사이트 다이얼 플랜은 온-프레미스를 호스트 하 고 온-프레미스 사이트에 할당 된 사용자 에게만 적용 되므로 사용할 수 없습니다. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>사용자별 다이얼 플랜을 할당 해제 하려면

- [부여-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 이전에 Ken Myer에 할당 된 사용자별 다이얼 플랜을 할당 해제 합니다. 사용자별 다이얼 플랜을 할당 하지 않으면 Ken Myer는 전역 다이얼 플랜 또는 해당 등록자 또는 PSTN 게이트웨이에 할당 된 서비스 범위 다이얼 플랜을 사용 하 여 자동으로 관리 됩니다. 서비스 범위 다이얼 플랜은 전역 다이얼 플랜 보다 우선 합니다.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>온-프레미스 Windows PowerShell cmdlet을 사용 하 여 음성 라우팅 정책 업데이트

이 섹션에서는 전화 시스템을 사용할 수 있는 사용자에 대 한 음성 라우팅 정책을 업데이트 하는 방법을 설명 합니다.
  
통화 경로를 지정 하려면 전화 시스템 사용자에 게 음성 라우팅 정책이 할당 되어 있어야 합니다. 이는 온-프레미스 비즈니스 음성 사용자와 음성 정책을 할당 하 여 호출이 성공적으로 경로를 사용 하도록 하는 것과는 다릅니다. 음성 라우팅 정책에는 전화 시스템 사용자에 대 한 인증 된 통화 및 경로를 정의 하는 PSTN 용도가 포함 되어야 합니다. 이러한 PSTN 용도를 기존 음성 정책에서 새 음성 라우팅 정책으로 복사할 수 있습니다. 자세한 내용은 [get-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)를 참조 하십시오.
  
> [!NOTE]
> 모든 전화 시스템 사용자에 게는 허용 되는 호출 기능을 정의 하는 BusinessVoice 라는 동일한 온라인 음성 정책이 할당 됩니다. 예를 들어 동시 벨 울림을 허용 합니다. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>단일 사용자에 게 사용자별 음성 라우팅 정책을 할당 하려면

- [Get-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 사용자 Ken Myer에 게 사용자별 음성 라우팅 정책 RedmondVoiceRoutingPolicy을 할당 합니다.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>여러 사용자에 게 사용자별 음성 라우팅 정책을 할당 하려면

- 다음 명령은 Redmond의 도시에서 근무 하는 모든 사용자에 게 사용자별 음성 라우팅 정책 RedmondVoiceRoutingPolicy를 할당 합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)를 참조 하십시오.
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 온라인 사용자에 게는 전역 또는 사용자 음성 라우팅 정책을 사용할 수 있습니다. 사이트 음성 라우팅 정책은 온-프레미스에 호스트 되 고 온-프레미스 사이트에 할당 된 사용자 에게만 적용 되므로 사용할 수 없습니다. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>사용자별 음성 라우팅 정책을 할당 해제 하려면

- Get-csvoiceroutingpolicy를 사용 하 여 이전에 Ken Myer에 할당 된 사용자별 음성 라우팅 정책을 할당 해제 합니다. 사용자별 음성 라우팅 정책이 할당 해제 되 면 Ken Myer는 전역 음성 라우팅 정책을 사용 하 여 자동으로 관리 됩니다.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    자세한 내용은 [Grant-get-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)를 참조 하세요.
    

