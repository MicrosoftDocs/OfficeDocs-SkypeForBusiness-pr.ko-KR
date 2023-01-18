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
ms.openlocfilehash: 60d9bf64233db3f5e615c0904c6eb376f187266c
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812845"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Teams PowerShell 모듈의 애플리케이션 기반 인증

애플리케이션 기반 인증은 이제 버전 4.7.1-preview 이상이 있는 Teams PowerShell 모듈에서 지원됩니다. 현재 이 인증 모드는 상용 환경에서만 지원됩니다.


## <a name="cmdlets-supported"></a>지원되는 Cmdlet

아래에 언급된 cmdlet을 제외하고 이제 모든 cmdlet이 지원됩니다. 

  - New-Team
  - [가져오기| 설정| 새로 만들기| Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>예제

다음 예제에서는 Azure AD 앱 기반 인증에서 Teams PowerShell 모듈을 사용하는 방법을 보여 줍니다. 

- 인증서 지문을 사용하여 연결:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  CertificateThumbprint 매개 변수를 사용하는 경우 명령을 실행하는 컴퓨터에 인증서를 설치해야 합니다. 인증서는 사용자 인증서 저장소에 설치해야 합니다.
  
- 인증서 개체를 사용하여 연결:

  ```powershell
  Connect-MicrosoftTeams -Certificate <%X509Certificate2 object%> -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Certificate 매개 변수를 사용하는 경우 명령을 실행하는 컴퓨터에 인증서를 설치할 필요가 없습니다. 스크립트를 실행할 때 & 인증서를 원격으로 저장할 수 있습니다. Certificate 매개 변수는 Teams PowerShell 모듈 버전 4.9.2-preview 이상에서 사용할 수 있습니다.
  
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

Teams PowerShell 모듈은 애플리케이션 ID, 테넌트 ID 및 인증서 지문을 사용하여 앱 기반 토큰을 가져옵니다. Azure AD 내에서 프로비전된 애플리케이션 개체에는 액세스 토큰에 반환되는 디렉터리 역할이 할당되어 있습니다. 세션의 RBAC(역할 기반 액세스 제어)는 토큰에서 사용할 수 있는 디렉터리 역할 정보를 사용하여 구성됩니다.


## <a name="setup-application-based-authentication"></a>애플리케이션 기반 인증 설정

애플리케이션 개체를 사용하는 인증에는 초기 온보딩이 필요합니다. 애플리케이션 및 서비스 주체는 서로 바꿔서 사용되지만 애플리케이션은 클래스 개체와 같고 서비스 주체는 클래스의 인스턴스와 같습니다. 이러한 개체에 대한 자세한 내용은 [Azure Active Directory의 애플리케이션 및 서비스 주체 개체에서](/azure/active-directory/develop/app-objects-and-service-principals) 확인할 수 있습니다.

Azure Ad에서 애플리케이션을 만들기 위한 샘플 단계는 아래에 설명되어 있습니다. 자세한 단계는 이 [문서를 참조하세요](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Azure AD 애플리케이션 등록
2. 애플리케이션에 API 권한 할당
   - -Cs cmdlet의 경우 \*필요한 Microsoft Graph API 권한은 입니다`Organization.Read.All`.
   - 비 \*Cs cmdlet의 경우 필요한 Microsoft Graph API 권한은 , , `User.Read.All`, `Group.ReadWrite.All`, `AppCatalog.ReadWrite.All``TeamSettings.ReadWrite.All`, `Channel.Delete.All`, , `ChannelSettings.ReadWrite.All`, `ChannelMember.ReadWrite.All`입니다`Organization.Read.All`.  
3. 자체 서명된 인증서 생성
4. 인증서를 Azure AD 애플리케이션에 연결
5. 애플리케이션에 [Azure AD 역할](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) 할당

애플리케이션에 적절한 RBAC 역할이 할당되어야 합니다. 앱은 Azure AD 프로비전되므로 지원되는 기본 제공 역할을 사용할 수 있습니다.
 
