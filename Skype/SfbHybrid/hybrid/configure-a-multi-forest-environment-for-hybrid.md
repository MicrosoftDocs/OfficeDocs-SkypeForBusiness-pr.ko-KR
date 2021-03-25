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
description: 다음 섹션에서는 하이브리드 시나리오에서 비즈니스용 Skype 기능을 제공하도록 리소스/사용자 포리스트 모델에 여러 포리스트가 있는 환경을 구성하는 방법에 대한 지침을 제공합니다.
ms.openlocfilehash: 2f4d0c84997dcc0d19439210e72eaf01a7a1ff26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119007"
---
# <a name="deploy-a-resource-forest-topology"></a>리소스 포리스트 토폴로지 배포
 
다음 섹션에서는 하이브리드 시나리오에서 비즈니스용 Skype 기능을 제공하도록 리소스/사용자 포리스트 모델에 여러 포리스트가 있는 환경을 구성하는 방법에 대한 지침을 제공합니다. 
  
![하이브리드용 다중 포리스트 환경](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>토폴로지 요구 사항

여러 사용자 포리스트가 지원됩니다. 다음 사항에 유의해야 합니다. 
    
- 하이브리드 구성에서 지원되는 Lync Server 및 비즈니스용 [](plan-hybrid-connectivity.md#server-version-requirements) Skype 서버 버전의 경우 비즈니스용 Skype 서버와 [Microsoft 365 또는 Office 365](plan-hybrid-connectivity.md)간의 하이브리드 연결 계획의 서버 버전 요구 사항을 참조하세요.
    
- Exchange Server 포리스트를 하나 이상의 포리스트에 배포할 수 있습니다. 비즈니스용 Skype 서버가 포함된 포리스트를 포함하거나 포함하지 않을 수 있습니다. 최신 누적 업데이트를 적용해야 합니다.
    
- 지원 기준 및 온라인과의 다양한 조합에 Exchange Server 및 제한 사항을 포함하여 비즈니스용 Skype와의 [](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 동시 사용에 대한 자세한 내용은 [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)의 기능 지원을 참조하세요.
    
  
## <a name="user-homing-considerations"></a>사용자 동시 사용 고려 사항

비즈니스용 Skype 사용자는 프레미스에 있는 Exchange를 프레미스 또는 온라인에 사용할 수 있습니다. 비즈니스용 Skype Online 사용자는 최적의 환경을 위해 Exchange Online을 사용해야 합니다. 그러나 이 필수는 아닙니다. Exchange on premises is not required to implement Skype for Business in either case.
  
## <a name="configure-forest-trusts"></a>포리스트 트러스트 구성

리소스 포리스트 토폴로지에서 비즈니스용 Skype 서버를 호스팅하는 리소스 포리스트는 해당 포리스트에 액세스할 사용자의 계정이 포함된 각 계정 포리스트를 신뢰해야 합니다. 사용자 포리스트가 여러 개 있는 경우 포리스트 간 인증을 사용하도록 설정하려면 이러한 각 포리스트 트러스트에 대해 이름 접미사 라우팅을 사용하도록 설정해야 합니다. 자세한 내용은 [Managing Forest Trusts를 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)) 다른 Exchange Server 배포한 경우 비즈니스용 Skype 사용자를 위한 기능을 제공하는 경우 Exchange를 호스팅하는 포리스트는 비즈니스용 Skype 서버를 호스팅하는 포리스트를 신뢰해야 합니다. 예를 들어 Exchange가 계정 포리스트에 배포된 경우 이 구성에는 계정과 비즈니스용 Skype 포리스트 간의 양측 트러스트가 실제로 필요합니다.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>비즈니스용 Skype를 호스팅하는 포리스트에 계정 동기화

비즈니스용 Skype 서버가 한 포리스트(리소스 포리스트)에 배포되지만 하나 이상의 다른 포리스트(계정 포리스트)에 있는 사용자에게 기능을 제공하는 경우 다른 포리스트의 사용자는 비즈니스용 Skype 서버가 배포된 포리스트에서 비활성화된 사용자 개체로 표시되어야 합니다. Microsoft Identity Manager와 같은 ID 관리 제품을 배포하고 구성하여 계정 포리스트의 사용자를 비즈니스용 Skype 서버가 배포된 포리스트로 프로비전하고 동기화해야 합니다. 사용자는 비즈니스용 Skype 서버를 호스팅하는 포리스트에 사용하지 않도록 설정된 사용자 개체로 동기화해야 합니다. Azure Active Directory Connect는 Skype에서 사용하기 위해 Azure AD에 연락처를 제대로 동기화하지 못하기 때문에 사용자를 Active Directory 연락처 개체로 동기화할 수 없습니다.
  
다중 포리스트 구성에 관계없이 비즈니스용 Skype 서버를 호스팅하는 포리스트는 동일한 포리스트에 있는 모든 활성화된 사용자에 대한 기능도 제공할 수 있습니다.
  
적절한 ID 동기화를 위해 다음 특성을 동기화해야 합니다. 
  
|**사용자 포리스트**|**리소스 포리스트**|
|:-----|:-----|
|선택한 계정 링크 특성  <br/> |선택한 계정 링크 특성  <br/> |
|메일  <br/> |메일  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
선택한 [계정 링크 특성이](/azure/active-directory/hybrid/plan-connect-design-concepts) 원본 앵커로 사용됩니다. 사용할 다른 변경이 불가능한 특성이 있는 경우 사용할 수 있습니다. AD FS 클레임 규칙을 편집하고 AAD Connect 구성 중에 특성을 선택해야 합니다.
  
포리스트 간에 UPNS를 동기화하지 않습니다. 테스트 중에 여러 포리스트에서 동일한 UPN을 사용할 수 없는 경우 각 사용자 포리스트에 대해 고유한 UPN을 사용하는 것이 필요하다는 것이 발견되었습니다. 따라서 UPN을 동기화하거나 동기화하지 않을 수 있는 두 가지 가능성이 제공될 수 있습니다. 
  
- 각 사용자 포리스트의 고유한 UPN이 리소스 포리스트의 연결된 비활성화된 개체와 동기화되지 않은 경우 사용자가 암호 저장 옵션을 선택한 경우 초기 로그인 시도에 대해 SSO(Single Sign-On)가 손상됩니다. 비즈니스용 Skype 클라이언트에서는 SIP/UPN 값이 동일한 것으로 가정합니다. 이 시나리오의 SIP 주소는 user@company.com 있지만 사용자 포리스트에서 활성화된 개체의 UPN이 실제로 user@contoso.company.com 때문에 초기 로그인 시도가 실패하고 자격 증명을 입력하라는 메시지가 표시됩니다. 올바른/실제 UPN을 입력하면 사용자 포리스트의 도메인 컨트롤러에 대해 인증 요청이 완료된 후 로그인에 성공합니다.
    
- 각 사용자 포리스트의 고유 UPN이 리소스 포리스트의 연결된 비활성화된 개체와 동기화된 경우 AD FS 인증이 실패합니다. 일치 규칙은 사용하지 않도록 설정되어 인증에 사용할 수 없는 리소스 포리스트의 개체에서 UPN을 찾을 수 있습니다. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Microsoft 365 또는 Office 365 조직 만들기

다음으로 배포에 사용할 Microsoft 365 또는 Office 365 조직을 프로비전해야 합니다. 자세한 내용은 Microsoft의 클라우드 서비스 에 대한 구독, 라이선스, 계정 및 [테넌트 를 참조하세요.](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings) 
  
## <a name="configure-active-directory-federation-services"></a>Active Directory Federation Services 구성

테넌트가 있는 경우 각 사용자 포리스트에서 AD FS(Active Directory Federation Services)를 구성해야 합니다. 이 경우 각 포리스트에 대해 고유한 SIP 및 SMTP 주소와 UPN(사용자 계정 이름)이 있는 것으로 가정합니다. AD FS는 선택 사항이며 여기에서 SSO(Single Sign-On)를 얻습니다. 암호 동기화가 있는 DirSync도 지원하며 AD FS 대신 사용할 수도 있습니다. 
  
SIP/SMTP 및 UPNS가 일치하는 배포만 테스트했습니다. 일치하는 SIP/SMTP/UPNS가 없는 경우 Exchange 통합 및 SSO와 같은 기능이 축소될 수 있습니다. 
  
각 포리스트의 사용자에 대해 고유한 SIP/SMTP/UPN을 사용하지 않는 한 AD FS가 배포된 위치와 관계없이 SSO 문제가 계속 발생할 수 있습니다. 
  
- 각 사용자 포리스트에 배포된 AD FS 팜이 있는 리소스/사용자 포리스트 간의 단 방법 또는 양측 트러스트는 모든 사용자가 공통 SIP/SMTP 도메인을 공유하지만 각 사용자 포리스트에 대해 고유한 UPN을 공유합니다. 
    
- 리소스 포리스트에만 배포된 AD FS 팜이 있는 리소스/사용자 포리스트 간의 양측 트러스트는 모든 사용자가 공통 SIP/SMTP 도메인을 공유하지만 각 사용자 포리스트에 대해 고유한 UPN을 공유합니다. 
    
각 사용자 포리스트에 AD FS 팜을 배치하고 각 포리스트에 대해 고유한 SIP/SMTP/UPN을 사용하여 두 문제를 해결합니다. 해당 특정 사용자 포리스트의 계정만 인증 시도 중에 검색 및 일치합니다. 이를 통해 보다 원활한 인증 프로세스를 제공할 수 있습니다. 
  
이 배포는 R2 AD FS의 Windows Server 2012 배포가 되기 전에 작동해야 합니다. 자세한 내용은 [Microsoft 365 또는 Office 365용 AD FS 2012 R2를](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)설치하는 방법을 참조하세요. 
  
배포한 후 앞에서 선택한 원본 앵커와 일치하게 클레임 규칙을 편집해야 합니다. AD FS MMC의 신뢰 파티 트러스트에서 **Microsoft 365 ID** 플랫폼 또는 Microsoft Office **365 ID 플랫폼을 마우스 오른쪽 단추로 클릭한** 다음 클레임 규칙 편집을 **선택합니다.** 첫 번째 규칙을 편집하고 ObjectSID를 **employeeNumber로 변경합니다.** 
  
![다중 포리스트 규칙 편집 화면](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>AAD Connect 구성

리소스 포리스트 토폴로지에서는 리소스 포리스트와 모든 계정 포리스트의 사용자 특성을 Azure AD로 동기화해야 합니다. 이렇게 하는 가장 간단하고 권장되는 방법은 Azure AD Connect가 사용자 계정  및 비즈니스용 Skype가 포함된 포리스트를 사용하도록 설정한 모든 포리스트에서 사용자 ID를 동기화하고 병합하는 것입니다. 자세한 내용은 비즈니스용 Skype 및 [Teams에 대한 Azure AD Connect 구성을 참조하세요.](configure-azure-ad-connect.md)

AAD Connect는 계정과 리소스 포리스트 간에는 프레미스에서 동기화를 제공하지 않습니다. 앞에서 설명한 대로 Microsoft Identity Manager 또는 유사한 제품을 사용하여 별도로 구성해야 합니다.
  
완료되면 AAD Connect가 결합 중이면 메타버스에서 개체를 보면 다음과 비슷한 것을 볼 수 있습니다. 
  
![다중 포리스트 메타버스 개체 화면](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
녹색으로 강조 표시된 특성은 Microsoft 365 또는 Office 365에서 병합된 것이고, 노란색은 사용자 포리스트에서, 파란색은 리소스 포리스트에서 비어 있습니다. 
  
이 사용자는 테스트 사용자로, AAD Connect가 Microsoft 365 또는 Office 365에서 sourceAnchor 및 cloudSourceAnchor를 식별한 경우 앞에서 선택한 employeeNumber인 1101을 볼 수 있습니다. 그런 다음 이 개체를 위의 개체에 병합할 수 있습니다. 
  
자세한 내용은 Azure Active Directory와 프레미스 [디렉터리 통합을 참조하세요.](/azure/active-directory/hybrid/whatis-hybrid-identity) 
  
AAD Connect는 다음을 제외하고 기본값을 사용하여 설치해야 합니다. 
  
1. Single Sign-In - AD FS가 이미 배포되어 작동 중: 구성 **안 를 선택합니다.**
    
2. Directories 연결: 모든 도메인을 추가합니다.
    
3. On-premises directories에서 사용자 식별: 여러 개의 여러 개의 **Director에** 있는 사용자 ID를 선택하고 **ObjectSID** 및 **msExchangeMasterAccountSID** 특성을 선택합니다.
    
4. Azure AD에서 사용자 식별: 원본 앵커: 좋은 [sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)특성 선택 , 사용자 계정 이름 - **userPrincipalName** 을 읽은 후 선택한 특성을 선택합니다.
    
5.  선택적 기능: Exchange 하이브리드를 배포할지 여부를 선택합니다.
    
    > [!NOTE]
    >  Exchange Online만 있는 경우 CNAME 리디렉션으로 인한 자동 검색 중에 OAuth 오류에 문제가 있을 수 있습니다. 이 문제를 해결하려면 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행하여 Exchange 자동 검색 URL을 설정해야 합니다.
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS 팜: 기존 Windows Server 2012 **R2 AD FS 팜** 사용을 선택하고 AD FS 서버의 이름을 입력합니다.
    
7.  마법사를 완료하고 필요한 유효성 검사를 수행하십시오.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 하이브리드 연결 구성

비즈니스용 Skype 하이브리드 구성에 대한 모범 사례를 따르하세요. 자세한 내용은 [하이브리드](plan-hybrid-connectivity.md) 연결 계획 및 하이브리드 연결 [구성을 참조하세요.](configure-hybrid-connectivity.md) 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>사용자에 대한 하이브리드 Exchange Server

필요한 경우 Exchange 하이브리드 구성에 대한 모범 사례를 따르는 것이 좋습니다. 자세한 내용은 하이브리드 [배포 Exchange Server 참조하세요.](/exchange/exchange-hybrid) 
