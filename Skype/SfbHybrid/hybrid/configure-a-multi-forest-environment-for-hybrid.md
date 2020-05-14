---
title: 리소스 포리스트 토폴로지 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 다음 섹션에서는 하이브리드 시나리오에서 비즈니스용 Skype 기능을 제공 하기 위해 리소스/사용자 포리스트 모델에 여러 포리스트가 포함 된 환경을 구성 하는 방법에 대 한 지침을 제공 합니다.
ms.openlocfilehash: cf3a162001756661afd0f204e9968713d9db0f5b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221482"
---
# <a name="deploy-a-resource-forest-topology"></a>리소스 포리스트 토폴로지 배포
 
다음 섹션에서는 하이브리드 시나리오에서 비즈니스용 Skype 기능을 제공 하기 위해 리소스/사용자 포리스트 모델에 여러 포리스트가 포함 된 환경을 구성 하는 방법에 대 한 지침을 제공 합니다. 
  
![하이브리드에 대 한 다중 포리스트 환경](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>토폴로지 요구 사항

여러 사용자 포리스트를 지원 합니다. 다음 사항에 유의해야 합니다. 
    
- 하이브리드 구성에서 지원 되는 Lync Server 및 비즈니스용 Skype [서버에 대](plan-hybrid-connectivity.md#server-version-requirements) 한 자세한 내용은 [Plan Hybrid Connectivity To 비즈니스용 Skype 서버 및 Microsoft 365 또는 Office 365](plan-hybrid-connectivity.md)을 참조 하십시오.
    
- Exchange Server는 비즈니스용 Skype 서버가 포함 된 포리스트를 포함 하거나 포함할 수 없는 하나 이상의 포리스트에 배포 될 수 있습니다. 최신 누적 업데이트를 적용 했는지 확인 합니다.
    
- 지원 기준 및 온-프레미스 및 온라인의 다양 한 조합에 포함 된 제한 사항을 비롯 하 여 Exchange Server와의 공존에 대 한 자세한 내용은 [비즈니스용 Skype 및 Exchange 통합 계획](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)에서 [기능 지원을](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 참조 하세요.
    
  
## <a name="user-homing-considerations"></a>사용자에 대 한 고려 사항

온-프레미스 비즈니스용 Skype 사용자는 온-프레미스 또는 온라인으로 Exchange를 사용할 수 있습니다. 비즈니스용 Skype Online 사용자는 최적의 환경을 위해 Exchange Online을 사용 해야 합니다. 그러나 필수는 아닙니다. 두 경우 모두에서 비즈니스용 Skype를 구현 하는 데 Exchange 온-프레미스를 사용할 필요는 없습니다.
  
## <a name="configure-forest-trusts"></a>포리스트 트러스트 구성

리소스 포리스트 토폴로지에서 비즈니스용 Skype 서버를 호스트 하는 리소스 포리스트는 사용자가 액세스할 수 있는 계정을 포함 하는 각 계정 포리스트를 신뢰 해야 합니다. 여러 사용자 포리스트가 있는 경우 포리스트 간 인증을 사용 하도록 설정 하려면 이러한 각 포리스트 트러스트에 대해 이름 접미사 라우팅을 사용 하도록 설정 하는 것이 중요 합니다. 자세한 내용은 [포리스트 트러스트 관리](https://technet.microsoft.com/library/cc772440.aspx)를 참조 하십시오. 다른 포리스트에 배포 된 Exchange Server가 비즈니스용 Skype 사용자에 게 기능을 제공 하는 경우 Exchange를 호스팅하는 포리스트는 비즈니스용 Skype 서버를 호스트 하는 포리스트를 신뢰 해야 합니다. 예를 들어 Exchange가 계정 포리스트에 배포 된 경우이는 계정 및 비즈니스용 Skype 포리스트가 해당 구성에 필요한 것을 의미 합니다.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>비즈니스용 Skype를 호스트 하는 포리스트에서 계정 동기화

비즈니스용 Skype 서버가 하나의 포리스트 (리소스 포리스트)에 배포 되었지만 하나 이상의 다른 포리스트 (계정 포리스트)에 있는 사용자에 게 기능을 제공 하는 경우에는 다른 포리스트의 사용자가 비즈니스용 Skype 서버를 배포 하는 포리스트에서 사용 하지 않도록 설정 된 사용자 개체로 표시 되어야 합니다. 계정 포리스트에서 비즈니스용 Skype 서버가 배포 되는 포리스트로 프로 비전 하 고 사용자를 동기화 하기 위해 Microsoft Identity Manager와 같은 id 관리 제품을 배포 하 고 구성 해야 합니다. 사용자는 비즈니스용 Skype를 호스트 하는 포리스트에서 사용 하지 않도록 설정 된 사용자 개체로 동기화 해야 합니다. Azure Active Directory Connect가 Skype와 함께 사용할 수 있도록 azure AD에 연락처를 올바르게 동기화 하지 않으므로 Active Directory 연락처 개체로 동기화 할 수 없습니다.
  
다중 포리스트 구성에 관계 없이 비즈니스용 Skype 서버를 호스트 하는 포리스트는 동일한 포리스트에 있는 사용 가능한 모든 사용자에 대 한 기능을 제공할 수도 있습니다.
  
적절 한 id 동기화를 얻으려면 다음 특성을 동기화 해야 합니다. 
  
|**사용자 포리스트**|**리소스 포리스트**|
|:-----|:-----|
|선택한 계정 링크 특성  <br/> |선택한 계정 링크 특성  <br/> |
|메일  <br/> |메일  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |Msrtcsip-gateways-OriginatorSID  <br/> |
   
[선택한 계정 링크 특성이](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) 원본 앵커로 사용 됩니다. 변경할 수 없는 다른 특성을 사용 하려는 경우에는이 작업을 수행 하면 됩니다. AD FS 클레임 규칙을 편집 하 고 AAD 연결 구성 중에 특성을 선택 해야 합니다.
  
포리스트 간에 Upn을 동기화 하지 않습니다. 여러 포리스트에서 동일한 UPN을 사용할 수 없으므로 각 사용자 포리스트에 대해 고유한 UPN을 사용 해야 하는 테스트 중에 발견 되었습니다. 따라서 UPN을 동기화 하거나 동기화 하지 않는 두 가지 가능성이 있습니다. 
  
- 각 사용자 포리스트의 고유 UPN이 리소스 포리스트의 연결 된 비활성 개체와 동기화 되지 않은 경우 최소 초기 로그인 시도에 대해 SSO (single sign-on)가 중단 됩니다 (사용자가 암호 저장 옵션을 선택 했다고 가정). 비즈니스용 Skype 클라이언트에서는 SIP/UPN 값이 동일한 것으로 가정 합니다. 이 시나리오에서 SIP 주소는 user@company.com 이지만 사용자 포리스트에 있는 enabled 개체의 UPN이 사실 user@contoso.company.com 경우 초기 로그인 시도가 실패 하 고 사용자에 게 자격 증명을 입력 하 라는 메시지가 표시 됩니다. 정확한/실제 UPN을 입력 하면 사용자 포리스트의 도메인 컨트롤러에 대해 인증 요청이 완료 되 고 로그인이 성공적으로 수행 됩니다.
    
- 각 사용자 포리스트의 고유 UPN이 리소스 포리스트의 연결 된 비활성 개체와 동기화 된 경우 AD FS 인증이 실패 합니다. 일치 규칙은 리소스 포리스트에서 사용 하지 않도록 설정 되었으며 인증에 사용할 수 없는 개체에서 UPN을 찾습니다. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Microsoft 365 또는 Office 365 조 직 만들기

다음에는 배포에 사용할 Microsoft 365 또는 Office 365 조 직을 프로 비전 해야 합니다. 자세한 내용은 [구독, 라이선스, 계정 및 Microsoft 클라우드 서비스에 대 한 테 넌 트](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)를 참조 하세요. 
  
## <a name="configure-active-directory-federation-services"></a>Active Directory Federation Services 구성

테 넌 트가 있으면 각 사용자 포리스트에서 AD FS (Active Directory Federation Services)를 구성 해야 합니다. 여기에서는 각 포리스트에 고유한 SIP 및 SMTP 주소와 UPN (사용자 계정 이름)을 사용 한다고 가정 합니다. AD FS는 선택적 이며 SSO (single sign-on)를 가져오기 위해 여기에 사용 됩니다. 암호 동기화를 사용한 DirSync도 지원 되며 AD FS 대신 사용 될 수도 있습니다. 
  
SIP/SMTP 및 Upn이 일치 하는 배포만 테스트 되었습니다. 일치 하는 SIP/SMTP/Upn으로 인해 Exchange 통합 및 SSO와 관련 된 문제 등의 기능이 저하 될 수 있습니다. 
  
각 포리스트의 사용자에 대해 고유한 SIP/SMTP/UPN을 사용 하는 경우가 아니면 AD FS가 배포 되는 위치에 관계 없이 SSO 문제가 계속 발생할 수 있습니다. 
  
- 각 사용자 포리스트에 배포 된 AD FS 팜이 있는 리소스/사용자 포리스트 간의 단방향 또는 양방향 트러스트 모든 사용자는 일반 SIP/SMTP 도메인을 공유 하지만 각 사용자 포리스트에 대해 고유한 UPN을 사용 합니다. 
    
- AD FS 팜이 포함 된 리소스/사용자 포리스트 간 양방향 트러스트 (리소스 포리스트에만 배포 됨) 모든 사용자는 일반 SIP/SMTP 도메인을 공유 하지만 각 사용자 포리스트에 대해 고유한 UPN을 사용 합니다. 
    
각 사용자 포리스트에 AD FS 팜을 배치 하 고 각 포리스트에 고유한 SIP/SMTP/UPN을 사용 하 여 두 가지 문제를 해결 합니다. 해당 특정 사용자 포리스트의 계정만 인증 시도 중에 검색 되어 일치 합니다. 이렇게 하면 보다 원활한 인증 프로세스를 제공 하는 데 도움이 됩니다. 
  
이 작업은 Windows Server 2012 R2 AD FS의 표준 배포가 며 계속 하기 전에 작동 해야 합니다. 자세한 내용은 [AD FS 2012 R2 For Microsoft 365 또는 Office 365을 설치 하는 방법을](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)참조 하십시오. 
  
배포한 후에는 이전에 선택한 원본 앵커와 일치 하도록 클레임 규칙을 편집 해야 합니다. AD FS MMC의 신뢰 당사자 트러스트에서 **microsoft 365 Id 플랫폼** 또는 **Microsoft Office 365 id 플랫폼**을 마우스 오른쪽 단추로 클릭 한 다음 **클레임 규칙 편집**을 선택 합니다. 첫 번째 규칙을 편집 하 고 ObjectSID를 **employeeNumber**로 변경 합니다. 
  
![다중 포리스트 규칙 편집 화면](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>AAD 연결 구성

리소스 포리스트 토폴로지에서 리소스 포리스트와 모든 계정 포리스트에서 사용자 특성을 Azure AD로 동기화 해야 합니다. 이 작업을 수행 하는 가장 간단 하 고 권장 방법은 사용자 계정 및 비즈니스용 Skype를 포함 하는 포리스트를 사용 하도록 설정한 *모든* 포리스트에서 Azure AD Connect를 동기화 하 고 사용자 id를 병합 하는 것입니다. 자세한 내용은 [비즈니스용 Skype 및 팀에 대 한 AZURE AD Connect 구성](configure-azure-ad-connect.md)를 참조 하세요.

AAD 연결은 계정 및 리소스 포리스트 간에 온-프레미스 동기화를 제공 하지 않습니다. 앞에서 설명한 대로 Microsoft Identity Manager 또는 유사 제품을 사용 하 여 별도로 구성 해야 합니다.
  
완료 및 AAD 연결이 병합 되는 경우 메타 버스에서 개체를 살펴보면 다음과 비슷한 항목이 표시 됩니다. 
  
![다중 포리스트 메타 버스 개체 화면](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
녹색으로 강조 표시 된 특성은 Microsoft 365 또는 Office 365에서 병합 되었으며, 노란색은 사용자 포리스트에서, 파란색은 리소스 포리스트를 사용 하는 것입니다. 
  
이는 테스트 사용자이 고, 이전에 선택한 employeeNumber 인 1101 경우 AAD Connect가 사용자의 출처 앵커와 cloudSourceAnchor 및 Microsoft 365 또는 Office 365의 리소스 포리스트 개체를 확인 했음을 확인할 수 있습니다. 그런 다음 위에 표시 된 것과이 개체를 병합할 수 있습니다. 
  
자세한 내용은 [Azure Active Directory를 사용 하 여 온-프레미스 디렉터리 통합](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)을 참조 하세요. 
  
다음을 제외 하 고는 기본 설정을 사용 하 여 AAD 연결을 설치 해야 합니다. 
  
1. Single sign-on with AD FS가 이미 배포 및 작동 중입니다. **구성 안 함**을 선택 합니다.
    
2. 디렉터리 연결: 모든 도메인을 추가 합니다.
    
3. 온-프레미스 디렉터리에서 사용자 식별: **여러 디렉터리에 있는 사용자 id**를 선택 하 고 **ObjectSID** 및 **msExchangeMasterAccountSID** 특성을 선택 합니다.
    
4. Azure AD에서 사용자 식별: 원본 앵커: 선택한 특성을 선택한 후에 [적절 한 원본 anchor 특성](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), 사용자 계정 이름- **userPrincipalName**을 선택 합니다.
    
5.  선택적 기능: Exchange 하이브리드 배포 여부를 선택 합니다.
    
    > [!NOTE]
    >  Exchange Online만 있는 경우 CNAME 리디렉션 때문에 자동 검색 중에 OAuth 오류에 문제가 있을 수 있습니다. 이를 해결 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하 여 Exchange 자동 검색 URL을 설정 해야 합니다.
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS 팜: **기존 Windows Server 2012 R2 AD fs 팜 사용** 을 선택 하 고 ad fs 서버 이름을 입력 합니다.
    
7.  마법사를 완료 하 고 필요한 유효성 검사를 수행 합니다.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 하이브리드 연결 구성

비즈니스용 Skype 하이브리드 구성에 대 한 모범 사례를 따릅니다. 자세한 내용은 [하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요. 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Exchange Server에 대 한 하이브리드 연결 구성

필요한 경우 Exchange 하이브리드 구성에 대 한 모범 사례를 따릅니다. 자세한 내용은 [Exchange Server 하이브리드 배포](https://docs.microsoft.com/exchange/exchange-hybrid)를 참조 하세요. 
  
