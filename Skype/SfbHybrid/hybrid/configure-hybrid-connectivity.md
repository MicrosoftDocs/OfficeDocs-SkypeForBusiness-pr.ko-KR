---
title: 하이브리드 연결 구성 | 2019 비즈니스용 Skype 서버 배포
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: 비즈니스용 Skype 서버 하이브리드 연결을 구현하기 위한 Teams.
ms.openlocfilehash: ffc1205ca91f81e9b9361e4603318bc1a8fcf76c
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887176"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>사용자 및 사용자 비즈니스용 Skype 서버 하이브리드 Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**요약:** 이 항목을 통해 사용자 및 사용자 간의 하이브리드 연결을 구성하는 비즈니스용 Skype 서버 Teams.  하이브리드 연결을 사용하면 사용자가 클라우드 서비스로 Teams 이동하고 사용자가 클라우드 서비스를 활용할 수 있습니다.
  
이 항목의 단계를 수행하기 전에 Plan [hybrid connectivity between 비즈니스용 Skype 서버 Teams.](plan-hybrid-connectivity.md)
  
다음 표에는 하이브리드 연결을 구성하는 데 비즈니스용 Skype 작업이 나열되어 있으며 자세한 내용은 관련 문서에 대한 링크를 제공합니다.
  
|단계|설명|
|:-----|:-----|
|Microsoft 365 테넌트 계정을 만듭니다.   <br/> |자세한 내용은 Microsoft 365 에서 [Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> 환경을 사용할 준비가 되어 있는지 확인 Microsoft 365 시스템 요구 [사항을 참조하세요.](https://products.office.com/office-system-requirements)  <br/> 설정에 대한 자세한 내용은 Microsoft 365 [시작을 Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|조직에 도메인을 Microsoft 365 소유권을 확인 합니다.  <br/> | 조직에 도메인을 추가하고 Microsoft 365 단계에 따라 도메인의 유효성을 검사해야 Microsoft 365. 이 유효성 검사는 사용자가 도메인의 소유자를 확인하는 것입니다. <br/> 도메인을 Microsoft 365 조직에 추가하려면 [도메인을](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)추가하여 조직에 Microsoft 365. 하이브리드가 되는 조직에 대한 DNS 의미와 관련하여 아래 지침을 [검토해야 합니다.](#dns-implications-for-on-premises-organizations-that-become-hybrid) <br/> |
|Active Directory 동기화를 설정합니다.  <br/> |Active Directory 동기화를 사용하면 각 사용자 계정 및 그룹의 동기화된 버전을 만들 수 있도록 Microsoft 365 Active Directory가 계속해서 동기화됩니다.  <br/> <br> **중요:** 사용자가 프레미스로 이동되지 않은 경우에도 조직의 모든 비즈니스용 Skype 사용자에 대해 Active Directory 계정을 동기화해야 Teams. 모든 사용자를 동기화하지 않는 경우 조직의 온라인 사용자와의 통신이 예상대로 작동하지 않을 수 있습니다. 자세한 내용은 [Configure Azure AD 커넥트 for hybrid environments을 참조하세요.](configure-azure-ad-connect.md)         |
| 비즈니스용 Skype 하이브리드 구성 | 세 가지 기본 단계가 있습니다. <br><br> 1. 프레미스 환경과 페더미스를 연결하도록 Microsoft 365. <br> 2. 공유 SIP 주소 공간을 신뢰하고 Microsoft 365 SIP 주소 공간을 사용하도록 Microsoft 365.<br> 3. 조직에서 공유 SIP 주소 Microsoft 365 사용하도록 설정 <br><br> 또한, Exchange 있는 경우 Exchange 환경과 온라인 환경 간에 OAuth를 구성할 수 있습니다. <br> <br>자세한 내용은 [하이브리드 구성을 비즈니스용 Skype 참조하세요.](configure-federation-with-skype-for-business-online.md)
|파일럿 사용자를 이동합니다.  <br/> |사용자 환경 준비 및 구성 단계를 완료한 후 Teams 사용자 이동을 시작할 수 Microsoft 365 있습니다. 자세한 내용은 [Move users from on premises to Teams.](move-users-from-on-premises-to-Teams.md)  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>하이브리드가 되는 사내 조직에 대한 DNS 의미

기본적으로 테넌트는 TeamsOnly 모드로 만들어집니다. 관리자는 이 구성을 변경할 수 없습니다. 그러나 하이브리드 조직은 TeamsOnly 모드가 아니어도 되어야 합니다. 이는 해당 사용자의 사내 사용자에 대한 페더전이 중단될 수 있기 때문에입니다. Teams 테넌트 전체 TeamsOnly 구성이 새 하이브리드 테넌트에 적용되지 않도록 하는 기본 제공 메커니즘이 있으며, 또한 하이브리드가 되는 기존 테넌트에서 테넌트 전체 TeamsOnly 구성이 제거됩니다. 이 메커니즘은 확인된 Microsoft 365 도메인에 대한 LyncDiscover DNS 레코드의 값을 기반으로 합니다(비즈니스용 Skype 서버 온-프레미스 배포에는 대부분의 경우 해당 레코드가 있기 때문에).

새 Microsoft 365 구독이 처음 처리되는 경우 다음이 발생합니다.
- 아직 확인된 도메인이 Microsoft 365 경우 테넌트가 TeamsOnly 모드로 만들어집니다. 값은 Microsoft에서만 설정할 수 있는 TeamsUpgradeOverridePolicy를 통해 설정됩니다. 정책 값이 UpgradeToTeams이면 TeamsUpgradePolicy 값보다 우선합니다.
- 확인된 Microsoft 365 도메인이 있지만 검색된 공용 DNS LyncDiscover 레코드가 없는 경우 또는 검색된 모든 LyncDiscover 레코드가 Microsoft 365(sipfed.online.lync.com, sipfed.online.gov.skypeforbusiness.us 등)을 향한 경우 테넌트가 TeamsUpgradeOverridePolicy를 통해 TeamsOnly 모드로 만들어집니다.
- 확인된 하나 이상의 Microsoft 365 도메인에서 LyncDiscover 레코드가 검색되고 해당 레코드가 Microsoft 365 다른 지점을 지정하면 테넌트가 아일랜드 모드로 만들어집니다.

기존 Microsoft 365 테넌트가 다시 프로비전되는 경우(일반적으로 확인된 도메인 또는 구독 세부 정보 변경) 다음이 발생합니다.
- 확인된 하나 이상의 Microsoft 365 도메인에 대해 LyncDiscover 레코드가 발견되고 해당 레코드가 Microsoft 365 지정하지 않는 경우 테넌트 전체 TeamsOnly 모드(TeamsUpgradeOverridePolicy를 통해)가 제거됩니다. 테넌트 모드는 기본적으로 아일랜드 모드인 TeamsUpgradePolicy의 테넌트 수준에서 지정된 것으로 되풀이됩니다.


이 자동 검색 메커니즘에는 몇 가지 제한이 있습니다.
- 조직에 공용 DNS 레코드가 없는 경우 TeamsOnly 모드는 레코드를 검색할 수 Microsoft 365 이후 제거되지 않습니다. 조직에 공용 DNS 비즈니스용 Skype 서버 없는 사내 배포가 있는 경우 테넌트가 다운그레이드된 경우 Microsoft 지원에 문의해야 합니다.
- 이미 확인된 도메인이 이미 있는 도메인에  공용 DNS 레코드를 Microsoft 365 이 DNS 변경은 검색되지 않습니다. TeamsOnly 모드는 제거되지 않습니다. TeamsOnly 모드는 테넌트가 다시 프로비전되는 경우만 제거됩니다. 일반적으로 확인된 도메인 또는 구독에 변경이 Microsoft 365 발생합니다.  
