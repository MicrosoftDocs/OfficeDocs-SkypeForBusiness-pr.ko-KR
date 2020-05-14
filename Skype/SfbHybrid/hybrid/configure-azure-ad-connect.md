---
title: Azure AD Connect 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 하이브리드 환경에서 Azure AD Connect를 구성 하기 위한 지침입니다.
ms.openlocfilehash: 7a0c458692da1381f2ed3f52dfef8c1d360d74e2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221472"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype에 Azure AD Connect 구성
 
비즈니스용 Skype 서버 (또는 Lync Server)가 온-프레미스이 고 팀 또는 비즈니스용 Skype Online을 사용할 계획인 조직은이 문서에 설명 된 대로 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365와 동기화 하도록 Azure AD Connect를 구성 해야 합니다.  여기에는 비즈니스용 Skype 온-프레미스에서 팀으로 직접 이동 하는 조직이 포함 됩니다. 특히 비즈니스용 Skype 온-프레미스를 사용하는 조직은 올바른 msRTCSIP 특성이 Azure AD로 동기화되는지 확인해야 합니다. 

> [!NOTE]
> 비즈니스용 Skype 온-프레미스를 보유한 기존 Teams 사용자는 비즈니스용 Skype 사용자와 상호 운용하고 페더레이션된 조직의 사용자와 커뮤니케이션하기 위한 기능과 같은 모든 기능을 사용하려면 비즈니스용 Skype 온-프레미스 계정을 클라우드로 이동해야 합니다. 사용자가 Teams만 사용하는 경우에도 인프라에서 추가 기능을 제공 하려면 이 온라인 비즈니스용 Skype 계정이 필요합니다.  이 마이그레이션을 수행하려면 하이브리드를 사용할 수 있도록 Azure AD Connect가 올바르게 구성되어 있는지 확인해야 합니다.
 

## <a name="background-information"></a>배경 정보

Azure Active Directory Connect는 온-프레미스 Active Directory가 Microsoft 365 또는 Office 365과 지속적으로 동기화 되도록 합니다.  온-프레미스 디렉터리는 신뢰할 수 있는 ID 원본으로 유지되고 온-프레미스 환경의 변경 내용은 Azure AD로 동기화됩니다. 자세한 내용은 [AZURE AD Connect 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)를 참조 하세요.  모든 사용자를 온-프레미스에서 클라우드로 이동 하는 경우에도, 팀을 사용 하는 모든 사용자, 온-프레미스 비즈니스용 skype 또는 비즈니스용 Skype Online을 온-프레미스에서 Azure AD로 동기화 하 여 온-프레미스와 온라인 사용자 간의 통신을 보장 해야 합니다. *조직의 사용자는 온-프레미스와 온라인 디렉터리에서 모두 표시됩니다.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>비즈니스용 Skype 서버가 있는 경우 Azure AD 구성 

온-프레미스 Active Directory 포리스트를 하나 또는 여러 개 사용 하 고 있는지 여부에 상관 없이 azure ad [connect에 대 한 토폴로지에](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)설명 된 것 처럼 지원 되는 다양 한 토폴로지에 연결 될 수 있습니다.  비즈니스용 Skype 서버의 관점에서 다음과 같이 세 가지 주요 변형이 있습니다. 

1. 단일 포리스트, 신뢰할 수 있는 사용자 ID를 포함하고 비즈니스용 Skype 서버를 호스팅 

2. 여러 포리스트, 그 중 하나만 비즈니스용 Skype 서버를 호스팅하고 신뢰할 수 있는 사용자 ID(계정 포리스트)를 포함하는 하나 이상의 다른 포리스트. 

3. 여러 포리스트에 여러 비즈니스용 Skype 서버를 배포 특정 요구 사항이 충족 되 면 조직은 이러한 여러 배포를 단일 Microsoft 365 또는 Office 365 조 직으로 통합할 수 있습니다.

### <a name="single-forest"></a>단일 포리스트 

사용자 계정과 비즈니스용 Skype가 모두 단일 포리스트로 호스팅되는 경우 이 포리스트의 사용자를 Azure AD로 동기화하도록 Azure AD Connect가 구성되어 있는지 확인해야 합니다.  Azure AD Connect 설치 마법사에는 다양한 옵션이 있지만 적절한 특성이 Azure Active Directory에 자동으로 동기화됩니다. 고객은 기본 제공 되는 동기화 규칙 및/또는 구성을 관리 하는 커넥터 (설치 마법사에서 불가능)를 수정 하는 것이 좋습니다.  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>비즈니스용 Skype 배포가 하나인 여러 포리스트 

이 시나리오를 종종 리소스 포리스트 토폴로지라고 합니다. 사용자의 신뢰할 수 있는 ID는 하나 이상의 계정 포리스트에서 호스팅되고 비즈니스용 Skype는 별도의 리소스 포리스트로 배포됩니다(자체로 신뢰할 수 있는 사용자 ID를 호스트할 수도 있음). 일반적으로 비즈니스용 Skype 사용자의 신뢰할 수 있는 ID는 다음과 같은 경우 비즈니스용 Skype 서버와 동일한 포리스트 및/또는 다른 포리스트에 있을 수 있습니다. 

- 계정 포리스트에서 신뢰할 수 있는 ID를 가진 사용자가 리소스 포리스트(비즈니스용 Skype 서버를 배포되는)에서 비활성 사용자 개체로 표시되고 리소스 포리스트의 msRTCSIP-OriginatorSID 특성은 계정 포리스트의 SID와 일치합니다. 자세한 내용은 [하이브리드 비즈니스용 Skype에 대 한 다중 포리스트 환경 구성을](configure-a-multi-forest-environment-for-hybrid.md)참조 하세요.

- 비즈니스용 Skype 서버를 호스트하는 리소스 포리스트가 계정 포리스트를 신뢰합니다.  

- ID(계정 포리스트)와 비즈니스용 Skype(리소스 포리스트)에 대한 모든 관련 사용자 개체 및 특성은 Azure AD Connect를 통해 올바른 값으로 Azure AD에 동기화됩니다.  

 [다중 포리스트 온-프레미스 시나리오](configure-a-multi-forest-environment-for-hybrid.md)에서 azure ad에 적절 한 개체 및 특성 동기화를 구현 하기 위해 Microsoft는 Azure ad Connect를 사용 하 여 사용자 계정 및 비즈니스용 Skype를 포함 하는 포리스트를 사용 하는 모든 포리스트에서 동기화를 수행 하는 것이 좋습니다.  모든 포리스트에서 동기화한다고 가정한다면 Azure AD Connect를 구성하여 이러한 ID를 병합하고 Azure AD에 동기화해야 합니다. Azure AD Connect는 이 시나리오를 처리할 수 있도록 설계 되었으며 ID 조인에 대한 앵커 설정을 포함하여 설정 마법사에서 기본 제공되는 옵션을 제공합니다.  사용자 id가 여러 디렉터리에 있는 경우 다음을 선택 합니다. --> ObjectSID 및 msExchangeMasterAccountSID 특성을 사용 하 여 일치 합니다.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>여러 포리스트에 여러 비즈니스용 Skype 서버 배포 

이 시나리오에는 각각 비즈니스용 Skype 서버를 포함 하는 여러 포리스트가 있고 단일 Microsoft 365 또는 Office 365 조 직이 있습니다.  비즈니스용 Skype 서버가 포함 된 각 포리스트는 AAD 연결을 사용 하 여 해당 조직에 대해 Azure AD로 동기화 할 수 있습니다. 주어진 시간에 비즈니스 용 Skype 하이브리드에 대해 하나의 포리스트만 구성할 수 있습니다. 포리스트에서 hybrid를 사용 하도록 설정 하기 전에 다른 모든 포리스트의 모든 SIP 도메인을 [disable-csonlineSipDomain](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain)을 사용 하 여 사용 하지 않도록 설정 해야 합니다. 이러한 환경을 Microsoft 365 또는 Office 365로 통합 하는 방법에 대 한 자세한 내용은 [팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)을 참조 하세요.

## <a name="general-requirements"></a>일반 요구 사항 

팀 및 비즈니스용 Skype Online 서비스 둘 다에는 올바른 Active Directory 특성이 존재 하 고 Azure AD에 채워져 있어야 합니다.  Microsoft의 일반적인 권장 사항은 사용자 id가 포함 된 모든 포리스트와 비즈니스용 Skype 서버가 포함 된 모든 포리스트를 동기화 하는 것입니다.

 사용자의 ID가 여러 포리스트 사이에 존재하는 경우 Azure AD Connect는 병합을 수행해야 합니다. 이 지침을 준수 하는 경우 azure AD Connect에서 커넥터 또는 동기화 규칙을 수정 하지 않는 경우에 자동으로 올바른 특성이 동기화 됩니다. 
  
사용자 id 및 비즈니스용 Skype 서버 배포를 포함 하는 모든 포리스트에서 동기화 하지 않는 경우에도 해당 하는 id 및 비즈니스용 Skype 특성은 팀 또는 비즈니스용 skype (온-프레미스 또는 온라인)를 사용 하는 모든 사용자의 Azure AD에 올바르게 채워졌는지 확인 해야 하며,이 경우 추가 온-프레미스 디렉터리 동기화가 필요 합니다. 자세한 내용은 [AZURE AD Connect sync: 특성을 Azure Active Directory에 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)됨을 참조 하세요.

이러한 시나리오에서 특성을 Azure AD로 채우기 위한 적절 한 구성을 보장 해야 하는 고객의 책임입니다. 다음 사항에 유의해야 합니다. 

- Azure AD로 동기화하는 데 표준이 아닌 구성을 사용하면 구성이 잘못되어 온라인 디렉터리에서 데이터가 손상될 수 있으므로 위험합니다.

- 제품이 계속 발전함에 따라 Microsoft는 모든 관련 포리스트가 동기화되는 표준 동기화 구성을 계속해서 확인합니다. 사용자 지정 동기화 구성을 한 고객은 해당 구성이 Azure AD에 올바른 특성과 값을 제공하도록 해야 합니다. 

## <a name="related-information"></a>관련 정보

- [하이브리드 id 란](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connect 동기화: 동기화 이해 및 사용자 지정](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect에 대한 토폴로지](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect 동기화: 특성이 Azure Active Directory와 동기화 됨](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
