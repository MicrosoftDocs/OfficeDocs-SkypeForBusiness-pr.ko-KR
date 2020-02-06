---
title: 사용자가 Office 365 음성 사서함에서 전화 시스템과 Enterprise Voice 라인을 사용하도록 설정
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
description: 비즈니스용 Skype 사용자를 위한 Office 365 음성 서비스에서 전화 시스템을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: f4fdd2a9a3da58f6804fa65acf96ba2b8fac682e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802208"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>사용자가 Office 365 음성 사서함에서 전화 시스템과 Enterprise Voice 라인을 사용하도록 설정
 
비즈니스용 Skype 사용자를 위한 Office 365 음성 서비스에서 전화 시스템을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
  
온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템을 배포 하는 마지막 단계는 Office 365 및 보이스 메일에서 사용자의 전화 시스템을 사용 하도록 설정 하는 것입니다. 이러한 접근 권한 값을 사용 하려면 Office 365 전역 관리자 역할이 있는 사용자 여야 하며 원격 PowerShell을 실행할 수 있습니다. 비즈니스용 Skype Online에 Enterprise Voice가 설정 되어 있지 않은 모든 사용자 계정에 대해이 항목의 단계를 수행 해야 합니다.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Office 365 음성 서비스에서 전화 시스템 사용

Office 365 음성 및 음성 메일에서 전화 시스템용 사용자를 사용 하도록 설정 하려면 비즈니스용 Skype Online Connector가 서버에 배포 되어 있으며 사용자가 호스트 된 보이스 메일을 사용할 수 있도록 하는 등의 몇 가지 초기 단계를 수행 해야 합니다.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Office 365 음성 및 음성 메일에서 전화 시스템용 사용자를 사용 하도록 설정 하려면

1. 시작 하기 전에 비즈니스용 Skype Online 커넥터 (Windows PowerShell 모듈)가 프런트 엔드 서버에 배포 되어 있는지 확인 합니다. 그렇지 않은 경우 [다운로드 센터](https://www.microsoft.com/en-us/download/details.aspx?id=39366)에서 다운로드할 수 있습니다. [비즈니스용 Skype Online 관리를 위해 컴퓨터를 구성할](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)때이 모듈을 사용 하는 방법에 대 한 자세한 내용을 확인할 수 있습니다.
    
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

    비즈니스용 Skype Server에서 PowerShell을 실행 하는 경우 PowerShell을 열 때 로컬 비즈니스용 Skype cmdlet이 이미 로드 되어 있습니다. 온라인 cmdlet이 동일한 이름을 사용 하 여 온-프레미스 cmdlet을 덮어쓸 수 있도록 하려면-AllowClobber 매개 변수를 지정 해야 합니다.
    
8. Set-CsUser cmdlet을 사용 하 여 $EnterpriseVoiceEnabled를 할당 하 고 다음과 같이 사용자에 게 속성을 $HostedVoiceMail 합니다.
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 또한 SIP 주소, UPN (사용자 계정 이름), 도메인 이름 및 사용자 이름 (domain\username), Active Directory에서 표시 이름 ("Bob 최소라")을 기준으로 사용자를 지정할 수 있습니다. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Office 365에서 전화 시스템을 사용 하도록 설정 된 사용자에 대 한 줄 URI 및 다이얼 플랜 업데이트

이 섹션에서는 Office 365에서 전화 시스템을 사용 하도록 설정 된 사용자 용 줄 URI 및 다이얼 플랜을 업데이트 하는 방법에 대해 설명 합니다. 
  
### <a name="to-update-the-line-uri"></a>줄 URI를 업데이트 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 시작 메뉴 또는 바탕 화면 바로 가기를 사용 하 여 비즈니스용 Skype 서버 제어판을 엽니다.
    
    > [!NOTE]
    > 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype Server 제어판을 열 수도 있습니다. 
  
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. **사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.
    
5. 표에서 줄 URI를 변경 하려는 비즈니스용 Skype 사용자 계정을 클릭 합니다.
    
6. **줄 URI**를 클릭 하 고 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200). 그런 다음 **커밋을**클릭 합니다.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>온-프레미스 Windows PowerShell cmdlet을 사용 하 여 다이얼 플랜 업데이트

Windows PowerShell 및 [권한 부여-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 사용자 단위 다이얼 플랜을 할당할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 2015 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>사용자 당 다이얼 플랜을 단일 사용자에 게 할당 하려면

- [권한 부여-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 사용자 단위 다이얼 플랜 RedmondDialPlan을 사용자: 진구 Myer에 할당 합니다.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>사용자 단위 다이얼 플랜을 여러 사용자에 게 할당 하려면

- 다음 명령을 사용 하 여 사용자 단위 다이얼 플랜 RedmondDialPlan을 Redmond의 구/군/시로 근무 하는 모든 사용자에 게 할당 합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet에 대 한 설명서를 참조 하세요.
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 온라인 사용자에 게 전역 또는 사용자 다이얼 플랜을 사용할 수 있습니다. 사이트 다이얼 플랜은 온-프레미스에서 호스트 되 고 온-프레미스 사이트에 할당 된 사용자 에게만 적용 되므로 사용할 수 없습니다. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>사용자 단위 다이얼 플랜을 할당 취소 하려면

- [허용-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 이전에: 진구 Myer에 할당 된 사용자 단위 다이얼 플랜을 할당 취소 합니다. 사용자 단위 다이얼 플랜의 할당을 해제 한 후에는: 진구 Myer이 전역 다이얼 플랜 또는 해당 레지스트라 또는 PSTN 게이트웨이에 할당 된 서비스 범위 다이얼 플랜을 사용 하 여 자동으로 관리 됩니다. 서비스 범위 다이얼 플랜은 전역 다이얼 플랜에 우선권을 갖습니다.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>온-프레미스 Windows PowerShell cmdlet을 사용 하 여 음성 라우팅 정책 업데이트

이 섹션에서는 Office 365에서 전화 시스템을 사용 하도록 설정 된 사용자에 대 한 음성 라우팅 정책을 업데이트 하는 방법에 대해 설명 합니다.
  
Office 365에서 전화를 거는 통화에 대 한 음성 라우팅 정책이 사용자에 게 할당 되어 있어야 연결 경로가 성공적으로 전달 됩니다. 이는 전화를 성공적으로 라우팅하도록 허용 하기 위해 음성 정책을 할당 해야 하는 온-프레미스 비즈니스 음성 사용자와 다릅니다. 음성 라우팅 정책에는 Office 365 사용자에서 전화 시스템에 대 한 인증 된 통화 및 경로를 정의 하는 PSTN 사용이 포함 되어야 합니다. 기존 음성 정책에서 이러한 PSTN 용도를 새 음성 라우팅 정책으로 복사할 수 있습니다. 자세한 내용은 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)를 참조 하세요.
  
> [!NOTE]
> Office 365 사용자의 모든 전화 시스템에는 허용 되는 통화 기능을 정의 하는 BusinessVoice 이라는 동일한 온라인 음성 정책이 할당 됩니다. 예를 들어 동시 벨 울림을 허용 합니다. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>단일 사용자에 게 사용자 단위 음성 라우팅 정책을 할당 하려면

- [CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 사용자 단위 음성 라우팅 정책 RedmondVoiceRoutingPolicy을 User: 진구 Myer에 할당 합니다.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>사용자 단위 음성 라우팅 정책을 여러 사용자에 게 할당 하려면

- 다음 명령을 사용 하 여 사용자 단위 음성 라우팅 정책을 Redmond의 구/군/시로 근무 하는 모든 사용자에 게 RedmondVoiceRoutingPolicy를 할당 합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)를 참조 하세요.
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 온라인 사용자에 게 글로벌 또는 사용자 음성 라우팅 정책을 사용할 수 있습니다. 사이트 음성 라우팅 정책은 온-프레미스에 호스트 되 고 온-프레미스 사이트에 할당 된 사용자 에게만 적용 되므로 사용할 수 없습니다. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>사용자 단위 음성 라우팅 정책을 할당 취소 하려면

- CsVoiceRoutingPolicy를 사용 하 여 이전에: 진구 Myer에 할당 된 사용자 단위 음성 라우팅 정책을 할당 취소 합니다. 사용자 단위 음성 라우팅 정책을 할당 하지 않으면: 진구 Myer는 전역 음성 라우팅 정책을 사용 하 여 자동으로 관리 됩니다.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    자세한 내용은 [허용-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)을 참조 하세요.
    

