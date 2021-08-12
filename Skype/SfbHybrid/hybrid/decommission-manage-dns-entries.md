---
title: 사내 환경을 해제할 때 DNS 항목 관리
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: On-premises 비즈니스용 Skype 해제할 때 DNS 항목을 관리하는 방법에 대한 지침입니다.
ms.openlocfilehash: 0dabf9790b1e579d136fef459308af450e879b110474b2877513855c8e78cf29
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315174"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>조직이 모든 사용자만 사용할 수 있도록 DNS Teams 업데이트

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이전에 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server를 배포한 조직에는 온-프레미스 배포를 비즈니스용 Skype DNS 항목이 있을 수 있습니다. 이러한 레코드는 조직에 사용자가 있는 경우 비즈니스용 Skype 필요합니다. 그러나 조직에 온-프레미스 비즈니스용 Skype 또는 Lync Server 사용자가 더 이상 없는 경우 이러한 원본 레코드는 온-프레미스 배포에 더 이상 필요하지 않습니다. 이러한 **DNS** 항목은 온-프레미스에서 Microsoft 365 마이그레이션의 일부로 Microsoft 365(또는 경우에 따라 제거됨)를 지정하기 위해 업데이트해야 Teams Only. *Microsoft는 사용자 대신 이러한 DNS 레코드를 업데이트할 수 없습니다.*

전체 테넌트에 TeamsOnly를 부여하려고 할 때 Teams DNS를 검사하여 아래에 나열된 이러한 DNS 레코드가 조직의 확인된 각 도메인에 Microsoft 365 있는지 여부를 확인할 수 있습니다. 레코드가 발견되어 레코드가 다른 레코드를 Microsoft 365 경우 테넌트 공존 모드를 TeamsOnly로 변경하려고 하면 디자인에 실패합니다. 이렇게 하면 테넌트에 TeamsOnly 모드를 실수로 적용하는 하이브리드 조직이 방지됩니다. 이렇게 하면 조직의 모든 비즈니스용 Skype 사용자에 대한 페더넌트가 중단됩니다(Teams 또는 비즈니스용 Skype).


## <a name="how-to-identify-stale-dns-records"></a>부실한 DNS 레코드를 식별하는 방법

조직에서 모든 DNS 레코드만 Teams DNS 레코드를 식별하려면 Teams 관리 센터를 사용하여 공존 모드를 TeamsOnly로 변경할 수 있습니다. 업그레이드 **에서 Org 전체**  ->  **Teams 로 이동하십시오.** 조직이 모든 DNS 레코드를 Teams 오류 메시지에 포함됩니다.  DNS 레코드가 발견되지 않으면 조직의 공존 모드가 TeamsOnly로 변경됩니다.   

또는 아래 표시된 Teams PowerShell을 사용하여 동일한 작업을 할 수 있습니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>업데이트할 DNS 레코드

조직에 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server에서 호스팅되는 사용자가 더 이상 없는 경우 다음을 실행해야 합니다.

- 아래 비즈니스용 Skype DNS 레코드 목록을 업데이트하여 Microsoft 365 배포를 지정합니다. SIP 도메인이 두 개 이상 있는 경우 확인된 도메인에 있는 각 SIP 도메인에 대해 Microsoft 365 합니다.

- SIP 비즈니스용 Skype 더 이상 사용되지 않으면 DNS 레코드를 제거합니다. 

다음 레코드를 찾은 각 도메인에서 다음과 같이 업데이트합니다.

| 레코드 유형 | 이름 | TTL | 우선 순위 | 가중치 | 포트 | 값 |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  해당 없음 |   해당 없음 |   해당 없음 |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    해당 없음 |   해당 없음  | 해당 없음 |    sipdir.online.lync.com |
|||||||

또한 meet 또는 dialin(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다. 마지막으로 내부 네트워크에서 비즈니스용 Skype DNS 레코드를 제거해야 합니다.

> [!Note] 
> 드문 경우지만 DNS를 조직에 대한 Microsoft 365 설정으로 변경하면 다른 조직에서 페더링 구성을 업데이트할 때까지 일부 다른 조직과의 페더링이 중지될 수 있습니다.
>
> - 이전 Direct Federation 모델(허용 파트너 서버라고도 지칭)을 사용하는 페더러된 조직은 조직에 대해 허용되는 도메인 항목을 업데이트하여 프록시 FQDN을 제거해야 합니다. 이 레거시 페더전 모델은 DNS SRV 레코드를 기반으로 하지 않습니다. 따라서 조직이 클라우드로 이동하면 이러한 구성이 최신이 됩니다.
> 
> - sipfed.online.lync에 대해 호스팅 공급자를 사용하도록 설정하지 않은 페더링된 조직입니다. <span> com은 구성을 업데이트하여 사용하도록 설정해야 합니다. 이 상황은 페더러드 조직이 전적으로 사내에 있으며 하이브리드 또는 온라인 테넌트와 페더러이트한 적이 없는 경우만 가능합니다. 이 경우 호스팅 공급자를 사용하도록 설정해야 이러한 조직과의 페더링이 작동하지 않습니다.
>
> 페더더러 파트너 중 한 자가 직접 페더ation을 사용 중일 수 있는 것으로 의심되거나 온라인 또는 하이브리드 조직과 페더러이트되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 통신을 해당 파트너에게 보내는 것이 좋은 제안입니다.
  




