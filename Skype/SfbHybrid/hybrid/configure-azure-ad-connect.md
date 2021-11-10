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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: 하이브리드 환경에서 Azure AD 커넥트 구성하기 위한 지침입니다.
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887216"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype에 Azure AD Connect 구성

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Teams 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server 2013을 배포하는 조직은 온-프레미스 디렉터리를 커넥트 Azure AD 2013을 구성해야 Microsoft 365. 모든 비즈니스용 Skype 서버 조직은 적절한 msRTCSIP 특성이 Azure AD에 동기화되어 있어야 합니다. 이 문서에서 "비즈니스용 Skype 서버"에 대한 참조는 Lync Server 2013에도 적용됩니다.

> [!NOTE]
> - 모든 기능을 사용하려면 Teams 사용자도 비즈니스용 Skype 기존 비즈니스용 Skype 계정을 클라우드로 이동해야 합니다. 예를 들어 사용자 및 사용자와 상호 비즈니스용 Skype 기능 및 페더전 조직의 사용자와 통신하는 기능 등의 기능을 사용할 수 있습니다. 사내 사용자가 TeamsOnly 사용자로만 Teams 여전히 사용자를 클라우드로 이동하여 TeamsOnly 사용자로 Teams 전체 기능을 제공해야 합니다. 이 마이그레이션을 수행하려면 하이브리드를 사용하도록 설정할 수 커넥트 Azure AD 계정을 구성해야 합니다.
> - 사용자를 사내에서 클라우드로 곧 이동하지 않을 계획이면 Azure AD 커넥트 계정과 Teams 계정이 비즈니스용 Skype 서버 구성해야 합니다.
 

## <a name="background-information"></a>배경 정보

Azure Active Directory 커넥트 Active Directory를 사용자와 지속적으로 동기화하는 Microsoft 365. Your on-premises directory remains the authoritative source of identity, while changes from your on-premises environment are synchronized into Azure AD. 자세한 내용은 Azure AD 커넥트 [동기화를 참조하세요.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)  *조직의 사용자는 사내* 및 온라인디렉터에서 모두 표현됩니다.  이러한 계정을 Teams 또는 비즈니스용 Skype 모든 사용자를 Azure AD로 동기화해야 합니다. 또한 하이브리드 연결을 통해 비즈니스용 Skype 사용자와 온라인 사용자 간의 통신을 용이하게 할 수 있으며, Azure AD 구성도 커넥트.


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>비즈니스용 Skype 서버가 있는 경우 Azure AD 구성 

### <a name="general-requirements"></a>일반 요구 사항 

비즈니스용 Skype 서버 배포가 비즈니스용 Skype 서버 함께 사용하려면 Teams 배포의 특정 Active Directory 특성을 Azure AD를 사용하여 Azure AD에 동기화해야 커넥트. Azure AD 커넥트 설정은 기본적으로 동기화할 필수 특성을 구성하는 데 필요한 특성이 비즈니스용 Skype 서버 환경의 현재 상태 감지를 위해 자동으로 구성됩니다. 이러한 특성에는 사용자 계정 이름과 같은 일반 ID 특성과 비즈니스용 서버와 관련이 있는 "msRTCSIP"로 Skype 특성이 포함됩니다. 전체 특성 집합은 Azure AD 커넥트 [동기화:](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online)에 Azure Active Directory.

Azure AD 2013에서 동기화 설정을 사용자 지정하도록 선택한 커넥트 사용자 개체에 대해 다음 특성이 동기화되어 있어야 합니다.
</br>

|특성|설명|
|---|---|
|msRTCSIP-PrimaryUserAddress| 사용자의 sip 주소(사내 환경)|
|msRTCSIP-DeploymentLocator| 사용자가 사내 또는 클라우드에 있는지 나타냅니다.|
|msRTCSIP-UserEnabled| 사용자가 SIP 기능을 사용할 수 있는지 여부|
|||

</br>
</br>
또한, 사내 배포를 통해 전화 시스템 특성을 관리하는 경우 다음 특성도 동기화해야 합니다.

|특성|설명|
|:---|:---|
|msRTCSIP-Line| 사용자의 전화 번호|
|msRTCSIP-OptionFlags| 사용자가 음성 기능을 사용할 수 있도록 설정되어 있는지 나타냅니다.|
|msRTCSIP-OwnerUrn| 하이브리드 응용 프로그램 끝점을 식별하는 데 사용됩니다.|
|||

</br>
사용자 ID가 포함된 모든 포리스트와 사용자 ID가 포함된 모든 포리스트를 동기화하는 비즈니스용 Skype 서버. 사용자의 ID가 여러 포리스트 사이에 존재하는 경우 Azure AD Connect는 병합을 수행해야 합니다. 이 지침을 따른다면 Azure AD Connect에서 커넥터나 동기화 규칙을 수정하지 않으면 Azure AD Connect가 자동으로 올바른 특성을 동기화합니다. 
  
사용자 ID 및 비즈니스용 Skype 서버 배포를 포함하는 모든 포리스트에서 동기화하지 않는 경우 Teams 또는 비즈니스용 Skype(Teams 또는 온라인)를 사용하는 모든 사용자에 대해 관련 ID 및 비즈니스용 Skype 특성이 Azure AD에 올바르게 채워야 합니다. 이 경우 추가 사내 디렉터리 동기화가 필요할 수 있습니다. 자세한 내용은 Azure AD 커넥트 동기화: 에 동기화된 [특성을 Azure Active Directory.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

Azure AD에 특성을 채우기 위한 적절한 구성을 보장하는 것은 고객의 책임입니다. 다음 사항에 유의해야 합니다. 

- Azure AD와 동기화하기 위해 비표준 구성을 사용하는 것은 위험합니다. 비호위 구성으로 인해 온라인 디렉터리에서 데이터가 손상될 수 있습니다.

- 제품이 계속 발전함에 따라 Microsoft는 모든 관련 포리스트가 동기화되는 표준 동기화 구성을 계속해서 확인합니다. 사용자 지정 동기화 구성을 한 고객은 해당 구성이 Azure AD에 올바른 특성과 값을 제공하도록 해야 합니다. 

하나의 프레미스 Active Directory 포리스트 또는 여러 포리스트가 있는 경우 Azure AD 커넥트 Azure AD 포리스트에 대한 토폴로지에서 설명된 다양한 지원되는 토폴로지에서 [사용할 수](/azure/active-directory/hybrid/plan-connect-topologies)커넥트. 이러한 비즈니스용 Skype 서버 세 가지 변형이 있습니다. 

1. 단일 포리스트, 신뢰할 수 있는 사용자 ID를 포함하고 비즈니스용 Skype 서버를 호스팅 

2. 여러 포리스트, 그 중 하나만 비즈니스용 Skype 서버를 호스팅하고 신뢰할 수 있는 사용자 ID(계정 포리스트)를 포함하는 하나 이상의 다른 포리스트. 

3. 여러 포리스트에 여러 비즈니스용 Skype 서버를 배포 특정 요구 사항을 충족하면 조직에서 이러한 여러 배포를 단일 조직으로 통합할 Microsoft 365 있습니다.

### <a name="single-forest"></a>단일 포리스트 

사용자 계정과 비즈니스용 Skype가 모두 단일 포리스트로 호스팅되는 경우 이 포리스트의 사용자를 Azure AD로 동기화하도록 Azure AD Connect가 구성되어 있는지 확인해야 합니다.  기본적으로 적절한 특성은 자동으로 해당 속성과 Azure Active Directory. 고객은 구성을 관리하는 기본 제공 동기화 규칙 및/또는 커넥터(설치 마법사에서 사용할 수 없는)를 수정하지 않는 것이 좋습니다.  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>비즈니스용 Skype 배포가 하나인 여러 포리스트 

이 시나리오를 종종 리소스 포리스트 토폴로지라고 합니다. 사용자의 신뢰할 수 있는 ID는 하나 이상의 계정 포리스트에서 호스팅되고 비즈니스용 Skype는 별도의 리소스 포리스트로 배포됩니다(자체로 신뢰할 수 있는 사용자 ID를 호스트할 수도 있음). 일반적으로 비즈니스용 Skype 사용자의 신뢰할 수 있는 ID는 다음과 같은 경우 비즈니스용 Skype 서버와 동일한 포리스트 및/또는 다른 포리스트에 있을 수 있습니다. 

- 계정 포리스트에서 권한이 있는 ID를 가지는 사용자는 리소스 포리스트(배포되는 위치)에서 비즈니스용 Skype 서버 개체로 표시됩니다. 리소스 포리스트의 msRTCSIP-OriginatorSID 특성은 계정 포리스트의 SID와 일치해야 합니다. 자세한 내용은 [Configure a multi-forest environment for hybrid](configure-a-multi-forest-environment-for-hybrid.md)비즈니스용 Skype.

- 비즈니스용 Skype 서버를 호스트하는 리소스 포리스트가 계정 포리스트를 신뢰합니다.  

- 계정 포리스트에서) 및 비즈니스용 Skype(리소스 포리스트)에 대한 모든 관련 사용자 개체 및 특성은 Azure AD 포리스트를 통해 올바른 값으로 Azure AD에 커넥트.  

  다중 포리스트의 사내 시나리오에서 Azure [](configure-a-multi-forest-environment-for-hybrid.md)AD로 적절한 개체 및 특성 동기화를 구현하기 위해 Azure AD 커넥트 사용하여 사용자 계정을 사용하도록 설정한 모든 포리스트와 사용자 계정이 포함된 포리스트를 동기화하는 것이 비즈니스용 Skype. 모든 포리스트에서 동기화한다고 가정한다면 Azure AD Connect를 구성하여 이러한 ID를 병합하고 Azure AD에 동기화해야 합니다. Azure AD Connect는 이 시나리오를 처리할 수 있도록 설계 되었으며 ID 조인에 대한 앵커 설정을 포함하여 설정 마법사에서 기본 제공되는 옵션을 제공합니다. 다음을 선택하십시오. 사용자 **ID는** 여러 개의 > **개체SID 및 msExchangeMasterAccountSID** 특성을 사용하여 일치합니다.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>여러 포리스트에 여러 비즈니스용 Skype 서버 배포 

이 시나리오에는 포리스트가 여러 개 있으며 각 포리스트에는 비즈니스용 Skype 서버 단일 포리스트가 Microsoft 365 있습니다. Azure AD 비즈니스용 Skype 서버 사용하여 해당 조직의 Azure AD로 동기화할 수 커넥트. 주어진 시간에 비즈니스 용 Skype 하이브리드에 대해 하나의 포리스트만 구성할 수 있습니다. 포리스트에서 하이브리드를 사용하도록 설정하기 전에 [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)을 사용하여 다른 모든 포리스트의 모든 SIP 도메인을 사용하지 않도록 설정해야 합니다. 자세한 내용은 에 대한 클라우드 통합 및 Teams [비즈니스용 Skype.](cloud-consolidation.md)


## <a name="related-information"></a>관련 정보

- [하이브리드 ID](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connect 동기화: 동기화 이해 및 사용자 지정](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect에 대한 토폴로지](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD 커넥트 동기화: Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
