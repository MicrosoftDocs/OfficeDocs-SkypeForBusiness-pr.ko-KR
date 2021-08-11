---
title: Azure AD 커넥트
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
description: 하이브리드 환경에서 Azure AD 커넥트 구성하기 위한 지침입니다.
ms.openlocfilehash: e9e043e8cded2e9e55741cd0abe37488c4b621c6fb7cbfc5e9fd1e35917f8b84
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292485"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype에 Azure AD Connect 구성

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
온-프레미스를 비즈니스용 Skype 서버(또는 Lync Server)를 사용하려면 Teams Azure AD 커넥트 온-프레미스 디렉터리를 온-프레미스 디렉터리와 동기화하도록 구성해야 Microsoft 365. 이 요구 사항에는 조직에서 직접 비즈니스용 Skype 프레미스에서 Teams. 모든 비즈니스용 Skype 조직은 적절한 msRTCSIP 특성이 Azure AD에 동기화되어 있어야 합니다.

> [!NOTE]
> Teams 사용자도 비즈니스용 Skype 있는 기존 비즈니스용 Skype 계정이 클라우드로 이동되어 비즈니스용 Skype 사용자와 상호 연결하고 페더러 조직의 사용자와 통신하는 등의 모든 기능을 사용하려면 해당 비즈니스용 Skype 계정을 클라우드로 이동해야 합니다. 사용자가 Teams만 사용하는 경우에도 인프라에서 추가 기능을 제공 하려면 이 온라인 비즈니스용 Skype 계정이 필요합니다. 이 마이그레이션을 수행하려면 하이브리드를 사용할 수 있도록 Azure AD Connect가 올바르게 구성되어 있는지 확인해야 합니다.
 

## <a name="background-information"></a>배경 정보

Azure Active Directory 커넥트 Active Directory를 사용자와 지속적으로 동기화하는 Microsoft 365. 온-프레미스 디렉터리는 신뢰할 수 있는 ID 원본으로 유지되고 온-프레미스 환경의 변경 내용은 Azure AD로 동기화됩니다. 자세한 내용은 Azure AD 커넥트 [동기화를 참조하세요.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)  

모든 사용자를 사내에서 클라우드로 이동하지 않는 경우 Teams 또는 비즈니스용 Skype 모든 사용자를 Azure AD로 동기화하여 모든 사용자를 Azure AD로 동기화해야 합니다. *조직의 사용자는 온-프레미스와 온라인 디렉터리에서 모두 표시됩니다.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>비즈니스용 Skype 서버가 있는 경우 Azure AD 구성 

하나의 프레미스 Active Directory 포리스트 또는 여러 포리스트가 있는 경우 Azure AD 커넥트 Azure AD 포리스트에 대한 토폴로지에서 설명된 다양한 지원되는 토폴로지에서 [사용할 수](/azure/active-directory/hybrid/plan-connect-topologies)커넥트. 이러한 비즈니스용 Skype 서버 세 가지 변형이 있습니다. 

1. 단일 포리스트, 신뢰할 수 있는 사용자 ID를 포함하고 비즈니스용 Skype 서버를 호스팅 

2. 여러 포리스트, 그 중 하나만 비즈니스용 Skype 서버를 호스팅하고 신뢰할 수 있는 사용자 ID(계정 포리스트)를 포함하는 하나 이상의 다른 포리스트. 

3. 여러 포리스트에 여러 비즈니스용 Skype 서버를 배포 특정 요구 사항을 충족하면 조직에서 이러한 여러 배포를 단일 조직으로 통합할 Microsoft 365 있습니다.

### <a name="single-forest"></a>단일 포리스트 

사용자 계정과 비즈니스용 Skype가 모두 단일 포리스트로 호스팅되는 경우 이 포리스트의 사용자를 Azure AD로 동기화하도록 Azure AD Connect가 구성되어 있는지 확인해야 합니다.  Azure AD Connect 설치 마법사에는 다양한 옵션이 있지만 적절한 특성이 Azure Active Directory에 자동으로 동기화됩니다. 고객은 구성을 관리하는 기본 제공 동기화 규칙 및/또는 커넥터(설치 마법사에서 사용할 수 없는)를 수정하지 않는 것이 좋습니다.  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>비즈니스용 Skype 배포가 하나인 여러 포리스트 

이 시나리오를 종종 리소스 포리스트 토폴로지라고 합니다. 사용자의 신뢰할 수 있는 ID는 하나 이상의 계정 포리스트에서 호스팅되고 비즈니스용 Skype는 별도의 리소스 포리스트로 배포됩니다(자체로 신뢰할 수 있는 사용자 ID를 호스트할 수도 있음). 일반적으로 비즈니스용 Skype 사용자의 신뢰할 수 있는 ID는 다음과 같은 경우 비즈니스용 Skype 서버와 동일한 포리스트 및/또는 다른 포리스트에 있을 수 있습니다. 

- 계정 포리스트에서 권한이 있는 ID를 가지는 사용자는 리소스 포리스트(배포되는 위치)에서 비즈니스용 Skype 서버 개체로 표시됩니다. 리소스 포리스트의 msRTCSIP-OriginatorSID 특성은 계정 포리스트의 SID와 일치해야 합니다. 자세한 내용은 [Configure a multi-forest environment for hybrid](configure-a-multi-forest-environment-for-hybrid.md)비즈니스용 Skype.

- 비즈니스용 Skype 서버를 호스트하는 리소스 포리스트가 계정 포리스트를 신뢰합니다.  

- 계정 포리스트에서) 및 비즈니스용 Skype(리소스 포리스트)에 대한 모든 관련 사용자 개체 및 특성은 Azure AD 포리스트를 통해 올바른 값으로 Azure AD에 커넥트.  

  다중 포리스트의 사내 시나리오에서 Azure [](configure-a-multi-forest-environment-for-hybrid.md)AD로 적절한 개체 및 특성 동기화를 구현하기 위해 Microsoft는 Azure AD 커넥트 사용하여 사용자 계정을 사용하도록 설정한 모든 포리스트와 사용자 계정이 포함된 포리스트에서 동기화하는 비즈니스용 Skype. 모든 포리스트에서 동기화한다고 가정한다면 Azure AD Connect를 구성하여 이러한 ID를 병합하고 Azure AD에 동기화해야 합니다. Azure AD Connect는 이 시나리오를 처리할 수 있도록 설계 되었으며 ID 조인에 대한 앵커 설정을 포함하여 설정 마법사에서 기본 제공되는 옵션을 제공합니다. 다음을 선택하십시오. 사용자 **ID는** 여러 개의 > **개체SID 및 msExchangeMasterAccountSID** 특성을 사용하여 일치합니다.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>여러 포리스트에 여러 비즈니스용 Skype 서버 배포 

이 시나리오에는 포리스트가 여러 개 있으며 각 포리스트에는 비즈니스용 Skype 서버 단일 포리스트가 Microsoft 365 있습니다. AAD 비즈니스용 Skype 서버 포함하는 각 포리스트를 해당 조직의 Azure AD로 동기화할 수 커넥트. 주어진 시간에 비즈니스 용 Skype 하이브리드에 대해 하나의 포리스트만 구성할 수 있습니다. 포리스트에서 하이브리드를 사용하도록 설정하기 전에 [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)을 사용하여 다른 모든 포리스트의 모든 SIP 도메인을 사용하지 않도록 설정해야 합니다. 자세한 내용은 에 대한 클라우드 통합 및 Teams [비즈니스용 Skype.](cloud-consolidation.md)

## <a name="general-requirements"></a>일반 요구 사항 

Teams 서비스를 사용하려면 올바른 Active Directory 특성이 존재하고 Azure AD에 채워야 합니다. 사용자 ID가 포함된 모든 포리스트와 사용자 ID가 포함된 모든 포리스트를 동기화하는 비즈니스용 Skype 서버.

 사용자의 ID가 여러 포리스트 사이에 존재하는 경우 Azure AD Connect는 병합을 수행해야 합니다. 이 지침을 따른다면 Azure AD Connect에서 커넥터나 동기화 규칙을 수정하지 않으면 Azure AD Connect가 자동으로 올바른 특성을 동기화합니다. 
  
사용자 ID 및 비즈니스용 Skype 서버 배포를 포함하는 모든 포리스트에서 동기화하지 않는 경우 Teams 또는 비즈니스용 Skype(Teams 또는 온라인)를 사용하는 모든 사용자에 대해 관련 ID 및 비즈니스용 Skype 특성이 Azure AD에 올바르게 채워야 합니다. 이 경우 추가 사내 디렉터리 동기화가 필요할 수 있습니다. 자세한 내용은 Azure AD 커넥트 동기화: 에 동기화된 [특성을 Azure Active Directory.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

이러한 시나리오에서는 Azure AD에 특성을 채우기 위한 적절한 구성을 보장하는 것은 고객의 책임입니다. 다음 사항에 유의해야 합니다. 

- Azure AD로 동기화하는 데 표준이 아닌 구성을 사용하면 구성이 잘못되어 온라인 디렉터리에서 데이터가 손상될 수 있으므로 위험합니다.

- 제품이 계속 발전함에 따라 Microsoft는 모든 관련 포리스트가 동기화되는 표준 동기화 구성을 계속해서 확인합니다. 사용자 지정 동기화 구성을 한 고객은 해당 구성이 Azure AD에 올바른 특성과 값을 제공하도록 해야 합니다. 

## <a name="related-information"></a>관련 정보

- [하이브리드 ID](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD 커넥트 동기화: 동기화 이해 및 사용자 지정](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect에 대한 토폴로지](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD 커넥트 동기화: Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)