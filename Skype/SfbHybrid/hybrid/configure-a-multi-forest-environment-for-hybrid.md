---
title: 리소스 포리스트 토폴로지 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 다음 섹션에서는 리소스/사용자 포리스트 모델에서 여러 포리스트가 있는 환경을 구성 하 여 하이브리드 시나리오에서 비즈니스용 Skype 기능을 제공 하는 방법에 대 한 지침을 제공 합니다.
ms.openlocfilehash: 7ef895648c044dc5d1f3f907ad4f75d950a4253a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185481"
---
# <a name="deploy-a-resource-forest-topology"></a>리소스 포리스트 토폴로지 배포
 
다음 섹션에서는 리소스/사용자 포리스트 모델에서 여러 포리스트가 있는 환경을 구성 하 여 하이브리드 시나리오에서 비즈니스용 Skype 기능을 제공 하는 방법에 대 한 지침을 제공 합니다. 
  
![하이브리드 용 다중 포리스트 환경](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>토폴로지 요구 사항

여러 사용자 포리스트가 지원 됩니다. 다음 사항에 유의 하세요. 
    
- 하이브리드 구성에서 지원 되는 Lync Server 버전 및 비즈니스용 Skype Server의 경우 비즈니스용 [Skype server 및 Office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md)의 [서버 버전 요구 사항을](plan-hybrid-connectivity.md#server-version-requirements) 참조 하세요.
    
- Exchange Server를 하나 이상의 포리스트에 배포할 수 있으며,이는 비즈니스용 Skype 서버를 포함 하는 포리스트를 포함 하거나 포함할 수 없습니다. 최신 누적 업데이트를 적용 했는지 확인 합니다.
    
- 다양 한 온-프레미스 및 온라인의 조합에 대 한 지원 기준 및 제한을 포함 하 여 Exchange Server와 공존 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 및 Exchange 통합 계획](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)의 [기능 지원을](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 참조 하세요.
    
  
## <a name="user-homing-considerations"></a>사용자가가을 때의 고려 사항

온-프레미스 비즈니스용 Skype 사용자는 구내 또는 온라인에서 Exchange를 가질 수 있습니다. 비즈니스용 Skype Online 사용자는 최적의 환경을 위해 Exchange Online을 사용 해야 합니다. 그러나 이것은 필요 하지 않습니다. 두 경우 모두 비즈니스용 Skype를 구현 하는 데는 구내 교환이 필요 하지 않습니다.
  
## <a name="configure-forest-trusts"></a>포리스트 트러스트 구성

리소스 포리스트 토폴로지에서 비즈니스용 Skype 서버를 호스트 하는 리소스 포리스트는 액세스 하는 사용자의 계정이 포함 된 각 계정 포리스트를 신뢰 해야 합니다. 여러 사용자 포리스트가 있는 경우 포리스트 간 인증을 사용 하도록 설정 하려면 이러한 각 포리스트 트러스트에 대해 이름 접미사 라우팅이 사용 하도록 설정 되어 있어야 합니다. 지침은 [포리스트 트러스트 관리](https://technet.microsoft.com/en-us/library/cc772440.aspx)를 참조 하세요. 다른 포리스트에 배포 된 Exchange Server가 비즈니스용 Skype 사용자를 위한 기능을 제공 하는 경우 Exchange를 호스팅하는 포리스트는 비즈니스용 Skype 서버를 호스팅하는 포리스트를 신뢰 해야 합니다. 예를 들어 계정 포리스트에서 Exchange를 배포한 경우이는 해당 구성에서 계정 및 비즈니스용 Skype 포리스트가 필요한 양방향 트러스트를 의미 합니다.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>비즈니스용 Skype 호스팅 포리스트로 계정 동기화

비즈니스용 Skype Server를 한 포리스트 (리소스 포리스트)에 배포 하는 경우 하나 이상의 다른 포리스트 (계정 포리스트)의 사용자에 게 기능을 제공 하는 경우, 다른 포리스트의 사용자는 사용 하지 않는 사용자 개체로 표시 되어야 하는 포리스트에 대해 Skype 비즈니스 서버가 배포 되었습니다. 사용자를 계정 포리스트에서 비즈니스용 Skype 서버가 배포 되는 포리스트로 구축 하 고 동기화 하도록 Microsoft Id 관리자와 같은 id 관리 제품을 배포 하 고 구성 해야 합니다. 사용자는 비즈니스용 Skype 서버를 사용 하지 않는 사용자 개체로 서 호스팅 포리스트로 동기화 되어야 합니다. Azure Active Directory Connect는 Skype에서 사용할 수 있도록 Azure AD에 연락처를 제대로 동기화 하지 않으므로 Active Directory 연락처 개체로 동기화 할 수 없습니다.
  
다중 포리스트 구성에 관계 없이 비즈니스용 Skype 서버를 호스트 하는 포리스트는 동일한 포리스트에 있는 사용 가능한 모든 사용자에 대 한 기능을 제공할 수도 있습니다.
  
적절 한 id 동기화를 얻으려면 다음 특성을 동기화 해야 합니다. 
  
|**사용자 포리스트**|**리소스 포리스트**|
|:-----|:-----|
|선택한 계정 링크 특성  <br/> |선택한 계정 링크 특성  <br/> |
|편집  <br/> |편집  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[선택한 계정 링크 특성이](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) 원본 앵커로 사용 됩니다. 다른 변경 불가능 한 특성을 사용 하려는 경우에는이 작업을 수행할 수 있습니다. AD FS 클레임 규칙을 편집 하 고 AAD Connect 구성 중에 특성을 선택 하세요.
  
포리스트 간의 Upn을 동기화 하지 마세요. 여러 포리스트에 대해 동일한 UPN을 사용할 수 없기 때문에 각 사용자 포리스트에 대해 고유한 UPN을 사용 해야 하는 테스트 중에 발견 했습니다. 결과적으로 UPN을 동기화 하거나 동기화 하지 않도록 두 가지 가능성을 제공 합니다. 
  
- 각 사용자 포리스트의 고유한 UPN이 리소스 포리스트의 연결 된 비활성 개체와 동기화 되지 않은 경우 최소한 초기 로그인 시도에 대 한 SSO (single sign-on)가 중단 됩니다 (사용자가 암호 저장 옵션을 선택 했다고 가정). 비즈니스용 Skype 클라이언트에서 SIP/UPN 값이 동일한 것으로 가정 합니다. 이 시나리오의 SIP 주소는 user@company.com, 사용자 포리스트에 있는 사용 개체의 UPN은 사실 user@contoso.company.com, 초기 로그인 시도가 실패 하 고 사용자에 게 자격 증명을 입력 하 라는 메시지가 표시 됩니다. 정확한/실제 UPN을 입력 하면 사용자 포리스트의 도메인 컨트롤러에 대해 인증 요청이 완료 되 고 로그인이 성공적으로 수행 됩니다.
    
- 각 사용자 포리스트의 고유한 UPN이 리소스 포리스트의 연결 된 비활성 개체와 동기화 된 경우 AD FS 인증이 실패 합니다. 일치 규칙은 리소스 포리스트의 개체에서 UPN을 찾고, 사용 하지 않도록 설정 되었으며 인증에 사용할 수 없습니다. 
    
## <a name="create-an-office-365-tenant"></a>Office 365 테 넌 트 만들기

다음에는 배포에 사용할 Office 365 테 넌 트를 프로 비전 해야 합니다. 자세한 내용은 [Microsoft의 클라우드 서비스에 대 한 구독, 라이선스, 계정 및 테 넌 트](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)를 참조 하세요. 
  
## <a name="configure-active-directory-federation-services"></a>Active Directory Federation Services 구성

테 넌 트가 있으면 각 사용자 포리스트에서 AD FS (Active Directory Federation Services)를 구성 해야 합니다. 여기에서는 각 포리스트에 대 한 고유한 SIP 및 SMTP 주소와 UPN (사용자 계정 이름)이 있다고 가정 합니다. AD FS는 선택 사항이 며 SSO (single sign-on)를 가져오는 데 사용 됩니다. 암호 동기화를 사용 하는 DirSync도 지원 되며 AD FS 대신 사용할 수도 있습니다. 
  
SIP/SMTP 및 Upn이 일치 하는 배포만 테스트 되었습니다. 일치 하는 SIP/SMTP/Upn을 사용 하지 않으면 Exchange 통합 및 SSO 문제 등의 기능을 줄일 수 있습니다. 
  
각 포리스트의 사용자에 대해 고유한 SIP/SMTP/UPN을 사용 하지 않는 경우에도 AD FS 배포 위치에 관계 없이 SSO 문제를 실행할 수 있습니다. 
  
- AD FS 팜을 사용 하는 리소스/사용자 포리스트 간 단방향 또는 양방향 트러스트 각 사용자 포리스트에는 모든 사용자가 공용 SIP/SMTP 도메인을 공유 하지만 각 사용자 포리스트에 대 한 고유한 UPN이 있습니다. 
    
- AD FS 팜을 사용 하는 리소스/사용자 포리스트 간 양방향 트러스트, 모든 사용자는 리소스 포리스트에만 배포 되 고 각 사용자 포리스트에 대 한 고유한 UPN은 공용 SIP/SMTP 도메인을 공유 합니다. 
    
각 사용자 포리스트에 AD FS 팜을 배치 하 고 각 포리스트에 대해 고유한 SIP/SMTP/UPN을 사용 하 여 두 가지 문제를 모두 해결 합니다. 특정 사용자 포리스트의 계정만 검색 하 여 인증을 시도 하는 동안 일치 시킬 수 있습니다. 이렇게 하면 보다 원활한 인증 프로세스를 제공 하는 데 도움이 됩니다. 
  
이는 Windows Server 2012 R2 AD FS의 표준 배포 이며 계속 하기 전에 작업 해야 합니다. 지침은 [Office 365 용 AD FS 2012 R2를 설치 하는 방법을](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)참조 하세요. 
  
배포 된 후에는 이전에 선택한 원본 앵커와 일치 하도록 클레임 규칙을 편집 해야 합니다. AD FS MMC의 신뢰 당사자 트러스트에서 **Microsoft Office 365 Id 플랫폼**을 마우스 오른쪽 단추로 클릭 한 다음 **클레임 규칙 편집**을 클릭 합니다. 첫 번째 규칙을 편집 하 고 ObjectSID를 **employeeNumber**로 변경 합니다. 
  
![다중 포리스트 규칙 편집 화면](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>AAD Connect 구성

리소스 포리스트 토폴로지에서는 리소스 포리스트 및 계정 포리스트 모두의 사용자 특성이 Azure AD로 동기화 되어야 합니다. 이 작업을 수행 하는 가장 간단 하 고 권장 되는 방법은 사용자 계정 및 비즈니스용 Skype가 포함 된 포리스트를 사용 하도록 설정한 *모든* 포리스트의 사용자 Id를 Azure AD Connect와 병합 하는 것입니다. 자세한 내용은 [비즈니스용 Skype 및 팀에 대 한 AZURE AD Connect 구성을](configure-azure-ad-connect.md)참조 하세요.

AAD Connect는 계정 및 리소스 포리스트 간에 온-프레미스 동기화를 제공 하지 않습니다. 앞에서 설명한 대로 Microsoft Id 관리자 또는 유사한 제품을 사용 하 여 개별적으로 구성 해야 합니다.
  
완료 및 AAD 연결이 병합 되는 경우 메타 버스에서 개체를 보면 다음과 비슷한 항목이 표시 됩니다. 
  
![다중 포리스트 메타 버스 개체 화면](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
녹색으로 강조 표시 된 특성은 Office 365에서, 노란색은 사용자 포리스트에서, 파란색은 리소스 포리스트를 사용 하 여 통합 되었습니다. 
  
이는 테스트 사용자 이며, 이전에 선택한 employeeNumber 1101에서 사용자 및 Office 365의 리소스 포리스트 개체 (예, 지정 된 경우)의 원본 앵커와 cloudSourceAnchor를 확인 했음을 확인할 수 있습니다. 그런 다음이 개체를 위의 표시 되는 항목에 병합할 수 있습니다. 
  
자세한 내용은 온 [-프레미스 디렉터리와 Azure Active Directory 통합](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)을 참조 하세요. 
  
다음과 같은 경우를 제외 하 고는 기본 설정을 사용 하 여 AAD 연결을 설치 해야 합니다. 
  
1. AD FS를 이미 배포 하 여 작동 하는 Single sign-on: **구성 안 함**을 선택 합니다.
    
2. 디렉터리 연결: 모든 도메인을 추가 합니다.
    
3. 온-프레미스 디렉터리에서 사용자 식별: **여러 디렉터리에 있는 사용자 id**를 선택 하 고 **ObjectSID** 및 **msExchangeMasterAccountSID** 특성을 선택 합니다.
    
4. Azure AD의 사용자 식별: 원본 앵커: [올바른 sourceAnchor 특성](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/), 사용자 계정 이름 **userPrincipalName**를 선택 하 여 선택한 특성을 선택 합니다.
    
5.  선택적 기능: Exchange 하이브리드 배포 여부를 선택 합니다.
    
    > [!NOTE]
    >  Exchange Online만 사용 하는 경우 CNAME 리디렉션 때문에 자동 검색 중에 OAuth 오류에 문제가 있을 수 있습니다. 이를 해결 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하 여 Exchange 자동 검색 URL을 설정 해야 합니다.
  
    Set-CsOAuthConfiguration-ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  AD FS 팜: **기존 Windows Server 2012 R2 AD fs 팜 사용** 을 선택 하 고 ad fs 서버의 이름을 입력 합니다.
    
7.  마법사를 완료 하 고 필요한 유효성 검사를 수행 합니다.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 하이브리드 연결 구성

비즈니스용 Skype 하이브리드 구성에 대 한 모범 사례를 따릅니다. 자세한 내용은 [하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요. 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Exchange Server에 대 한 하이브리드 연결 구성

필요한 경우 Exchange 하이브리드 구성에 대 한 모범 사례를 따릅니다. 자세한 내용은 [Exchange Server 하이브리드 배포](https://docs.microsoft.com/en-us/exchange/exchange-hybrid)를 참조 하세요. 
  

