---
title: Teams PowerShell 모듈의 애플리케이션 기반 인증
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리에 사용되는 Teams PowerShell 모듈의 애플리케이션 기반 인증에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 479dd64d6eece46335545e79e8f618b797e85f77
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795067"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Teams PowerShell 모듈의 애플리케이션 기반 인증

애플리케이션 기반 인증은 현재 Teams PowerShell 모듈에서 버전 4.7.1-preview 이상이 있는 미리 보기의 제한된 cmdlet 집합에 대해 지원됩니다. 현재 이 인증 모드는 상용 환경에서만 지원됩니다. 비즈니스용 Skype Online에서 지역 호스팅 모임에 대해 이전에 사용하도록 설정되었거나 사용하도록 설정된 고객에게는 지원되지 않습니다.


## <a name="cmdlets-supported"></a>지원되는 Cmdlet

모든 비 \*Cs cmdlet(예: Get-Team), Get-CsTenant, Get-CsOnlineUser & Get-CsOnlineVoiceUser 이미 지원됩니다. 다른 cmdlet은 점진적으로 롤아웃됩니다. 


## <a name="examples"></a>예제

다음 예제에서는 Azure AD 앱 기반 인증에서 Teams PowerShell 모듈을 사용하는 방법을 보여 줍니다. 

- 인증서 지문을 사용하여 연결:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  CertificateThumbprint 매개 변수를 사용하는 경우 명령을 실행하는 컴퓨터에 인증서를 설치해야 합니다. 인증서는 사용자 인증서 저장소에 설치해야 합니다.
  
- 액세스 토큰을 사용하여 연결:
  
  액세스 토큰은 login.microsoftonline.com 엔드포인트를 통해 검색할 수 있습니다. "MS Graph" 및 "Skype 및 Teams 테넌트 관리 API" 리소스라는 두 개의 액세스 토큰이 필요합니다.

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>어떻게 작동하나요?

Teams PowerShell 모듈은 애플리케이션 ID, 테넌트 ID 및 인증서 지문을 사용하여 앱 기반 토큰을 가져옵니다. Azure AD 내에 프로비전된 애플리케이션 개체에는 액세스 토큰에 반환되는 디렉터리 역할이 할당되어 있습니다. 세션의 RBAC(역할 기반 액세스 제어)는 토큰에서 사용할 수 있는 디렉터리 역할 정보를 사용하여 구성됩니다.


## <a name="setup-application-based-authentication"></a>애플리케이션 기반 인증 설정

애플리케이션 개체를 사용하는 인증에는 초기 온보딩이 필요합니다. 애플리케이션 및 서비스 주체는 서로 교환하여 사용되지만, 서비스 주체는 클래스의 인스턴스와 같은 반면 애플리케이션은 클래스 개체와 같습니다. [Azure Active Directory의 Application 및 서비스 주체 개체에서 이러한 개체에](/azure/active-directory/develop/app-objects-and-service-principals) 대해 자세히 알아볼 수 있습니다.

Azure Ad에서 애플리케이션을 만들기 위한 개략적인 단계는 아래에 설명되어 있습니다. 자세한 단계는 이 문서를 참조 [하세요](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Azure AD 애플리케이션 등록
2. 애플리케이션에 API 권한 할당
   - -Cs cmdlet의 경우 \*API 권한이 필요하지 않습니다.
   - 비 \*Cs cmdlet의 경우 필요한 Microsoft Graph API 권한은 , `Group.ReadWrite.All`, `AppCatalog.ReadWrite.All`, `Channel.Delete.All``TeamSettings.ReadWrite.All`, , `ChannelSettings.ReadWrite.All``ChannelMember.ReadWrite.All`입니다`User.Read.All`.  
3. 자체 서명된 인증서 생성
4. Azure AD 애플리케이션에 인증서 연결
5. 애플리케이션에 Azure AD 역할 할당

애플리케이션에 적절한 RBAC 역할이 할당되어야 합니다. 앱은 Azure AD 프로비전되므로 지원되는 기본 제공 역할을 사용할 수 있습니다.
 
