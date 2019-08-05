---
title: Azure AD Connect 구성
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
description: 하이브리드 환경에서 Azure AD Connect를 구성 하기 위한 지침입니다.
ms.openlocfilehash: 9df0e42224d3186c3d7b5b1748412e9ec9121897
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185484"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>팀 및 비즈니스용 Skype에 대 한 Azure AD Connect 구성
 
비즈니스용 Skype Server (또는 Lync Server)가 온-프레미스이 고 팀 또는 비즈니스용 Skype Online을 사용할 계획인 조직에서는 Azure AD Connect를 구성 하 여 온-프레미스 디렉터리를 Office 365와 동기화 해야 합니다. 설명서.  여기에는 비즈니스용 Skype 온-프레미스에서 팀으로 직접 이동 하는 조직이 포함 됩니다. 특히 비즈니스용 Skype 온-프레미스를 사용 하는 조직은 올바른 msRTCSIP 특성이 Azure AD로 동기화 되어 있는지 확인 해야 합니다. 

> [!NOTE]
> 비즈니스용 Skype 온-프레미스를 사용 하는 기존 팀 사용자는 비즈니스용 skype 온-프레미스 계정을 클라우드로 이동 해야 업무용 사용자와의 상호 운용성과 같은 모든 기능을 이용할 수 있습니다. 페더레이션된 조직의 사용자와 통신 사용자가 팀만을 사용 하는 경우에도 인프라에서 추가 기능을 제공 하려면이 온라인 비즈니스용 Skype 계정이 필요 합니다.  이 마이그레이션을 수행 하려면 하이브리드을 사용할 수 있도록 Azure AD 연결이 올바르게 구성 되어 있는지 확인 해야 합니다.
 

## <a name="background-information"></a>배경 정보

Azure Active Directory Connect는 온-프레미스 Active Directory를 계속 해 서 Office 365와 동기화 합니다.  온-프레미스 디렉터리는 정식 id의 원본으로 유지 되며 온-프레미스 환경의 변경 내용이 Azure AD로 동기화 됩니다. 자세한 내용은 [AZURE AD Connect 동기화](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)를 참조 하세요.  모든 사용자를 온-프레미스에서 클라우드로 이동 하지 않는 경우에도 팀을 사용 하는 모든 사용자, 비즈니스용 Skype 온-프레미스 또는 비즈니스용 Skype Online을 온-프레미스에서 Azure AD로 동기화 하 여 온-프레미스와 온라인 사용자 간의 통신을 확인 해야 합니다. . *조직의 사용자는 온-프레미스 및 온라인 디렉터리에 모두 표시 됩니다.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>비즈니스용 Skype 서버를 사용 하는 경우 Azure AD 구성 

온-프레미스 Active Directory 포리스트 또는 여러 포리스트를 사용 하는 경우 azure [Ad connect의 토폴로지에서](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)설명 된 대로 Azure ad connect를 지원 되는 다양 한 토폴로지에서 사용할 수 있습니다.  비즈니스용 Skype 서버의 관점에서 세 가지 주요 변형이 있습니다. 

1. 신뢰할 수 있는 사용자 id와 비즈니스용 Skype 서버를 호스트 하는 단일 포리스트입니다. 

2. 여러 포리스트, 신뢰할 수 있는 사용자 id (계정 포리스트)를 포함 하는 하나 이상의 다른 포리스트 외에도 비즈니스용 Skype 서버를 호스트 하는 계정이 하나 이상 있습니다. 

3. 여러 포리스트에 비즈니스용 Skype 서버를 여러 개 배포 했습니다. 특정 요구 사항이 충족 되는 경우 조직은 이러한 여러 배포를 단일 Office 365 테 넌 트로 통합할 수 있습니다.

### <a name="single-forest"></a>단일 포리스트 

사용자 계정 및 비즈니스용 Skype가 모두 단일 포리스트에서 호스팅되는 경우이 포리스트의 사용자를 Azure AD로 동기화 하도록 Azure AD Connect가 구성 되어 있는지 확인 해야 합니다.  Azure AD Connect 설치 마법사에는 다양 한 옵션이 있지만 적절 한 특성이 Azure Active Directory로 자동으로 동기화 됩니다. 고객은 기본 제공 동기화 규칙 및/또는 구성을 관리 하는 커넥터 (설치 마법사에서는 불가능 함)를 수정 하는 것이 좋습니다.  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>하나의 비즈니스용 Skype 배포로 여러 포리스트 사용 

이 시나리오는 흔히 리소스 포리스트 토폴로지 라고도 합니다. 사용자의 신뢰할 수 있는 id는 하나 이상의 계정 포리스트에서 호스팅되며, 비즈니스용 Skype는 별도의 리소스 포리스트에 배포 됩니다 (자신에 게 권한이 있는 사용자 id를 호스트 하는 것도 해당). 일반적으로 비즈니스용 Skype 사용자의 권한 부여 id는 비즈니스용 Skype 서버 및/또는 다음의 다른 포리스트에 있는 것과 같은 포리스트에 있을 수 있습니다. 

- 계정 포리스트 (들)에서 신뢰할 수 있는 id를 가진 사용자는 사용 되지 않는 사용자 개체로 표시 되며 리소스 포리스트에서는 리소스 포리스트 (비즈니스용 Skype 서버의 msRTCSIP-OriginatorSID 특성은 해당 SID와 일치 합니다. 계정 포리스트. 자세한 내용은 [하이브리드 비즈니스용 Skype에 대 한 다중 포리스트 환경 구성을](configure-a-multi-forest-environment-for-hybrid.md)참조 하세요.

- 비즈니스용 Skype 서버를 호스트 하는 리소스 포리스트는 계정 포리스트를 신뢰 합니다.  

- 계정 포리스트에서, 그리고 비즈니스용 Skype (리소스 포리스트에서)에 대 한 모든 관련 사용자 개체와 특성은 Azure AD Connect를 통해 올바른 값으로 Azure AD로 동기화 됩니다.  

 [다중 포리스트 온-프레미스 시나리오](configure-a-multi-forest-environment-for-hybrid.md)에서 azure ad로 적절 한 개체 및 특성 동기화를 구현 하기 위해 Microsoft는 Azure ad Connect를 사용 하 여 사용자 계정 및 포리스트를 사용 하는 모든 포리스트에서 동기화 하는 것이 좋습니다. 비즈니스용 Skype가 포함 되어 있습니다.  모든 포리스트에서 동기화 하는 경우 Azure AD Connect를 구성 하 여 해당 id를 병합 하 고 Azure AD와 동기화 해야 합니다. Azure AD Connect는이 시나리오를 처리 하도록 디자인 되었으며, 설정에 대 한 앵커 설정을 포함 하 여 설치 마법사에 기본 제공 옵션을 제공 합니다.  사용자 id가 여러 디렉터리에 존재 하도록 하려면 다음을 선택 합니다. --> ObjectSID 및 msExchangeMasterAccountSID 특성을 사용 하 여 일치 합니다.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>여러 포리스트에 있는 여러 개의 비즈니스용 Skype 서버 배포 

이 시나리오에는 각각 비즈니스용 Skype 서버를 포함 하는 여러 개의 포리스트와 단일 Office 365 테 넌 트가 있습니다.  비즈니스용 Skype 서버를 포함 하는 각 포리스트는 AAD Connect를 사용 하 여 해당 테 넌 트에 대해 Azure AD로 동기화 될 수 있습니다. 대부분의 비즈니스용 Skype는 주어진 시간에 하나의 포리스트로만 구성할 수 있습니다. 포리스트에서 하이브리드를 사용 하도록 설정 하기 전에 다른 모든 포리스트의 모든 SIP 도메인을 [disable-Cson회선 Ipdomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)을 사용 하 여 사용 하지 않도록 설정 해야 합니다. 이러한 환경을 Office 365에 통합 하는 방법에 대 한 자세한 내용은 [팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)을 참조 하세요.

## <a name="general-requirements"></a>일반 요구 사항 

팀과 비즈니스용 Skype Online 서비스는 모두 올바른 Active Directory 특성이 존재 하 고 Azure AD에 채워져 있어야 합니다.  Microsoft의 일반적인 권장 사항은 사용자 id를 포함 하는 모든 포리스트와 비즈니스용 Skype 서버를 포함 하는 모든 포리스트를 동기화 하는 것입니다.

 사용자의 id가 여러 포리스트에 있는 경우 Azure AD Connect는 병합을 수행 해야 합니다. 이 지침을 따라 azure AD connect에서 커넥터 또는 동기화 규칙을 수정 하지 않은 경우에는 Azure AD Connect가 올바른 특성을 자동으로 동기화 합니다. 
  
사용자 id 및 비즈니스용 Skype 서버 배포를 포함 하는 모든 포리스트에서 동기화 하지 않은 경우에도 팀 또는 Skype를 사용 하는 모든 사용자의 관련 id 및 비즈니스용 Skype 특성이 Azure AD에 올바르게 입력 되어 있는지 확인 해야 합니다. 비즈니스용 (온-프레미스 또는 온라인)--추가 온-프레미스 디렉터리 동기화가 필요할 수 있습니다. 자세한 내용은 [AZURE AD Connect 동기화: Azure Active Directory와 동기화 된 특성](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)을 참조 하세요.

이러한 시나리오에서는 특성을 Azure AD로 채우는 적절 한 구성을 고객의 책임으로 유지 해야 합니다. 다음 사항에 유의 하세요. 

- Azure AD로 동기화 하는 데 비표준 구성을 사용 하는 것은 구성이 잘못 될 수 있기 때문에 위험한 이유 이며,이로 인해 온라인 디렉터리에서 데이터가 손상 될 수 있습니다.

- 제품이 발전 함에 따라 Microsoft는 모든 관련 포리스트가 동기화 되는 표준 동기화 구성을 계속 확인할 수 있습니다. 사용자 지정 동기화 구성을 사용 하는 고객은 해당 구성이 Azure AD로 올바른 특성 및 값을 제공 하는지 확인 해야 합니다. 

## <a name="related-information"></a>관련 정보

- [하이브리드 id 란?](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect 동기화: 동기화 이해 및 사용자 지정](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect에 대 한 토폴로지](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect 동기화: 특성이 Azure Active Directory와 동기화 됨](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
