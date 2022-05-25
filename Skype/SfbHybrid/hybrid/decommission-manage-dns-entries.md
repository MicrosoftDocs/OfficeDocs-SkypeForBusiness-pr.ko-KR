---
title: 온-프레미스 환경을 서비스 해제할 때 DNS 항목 관리
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
description: 온-프레미스 비즈니스용 Skype 환경을 서비스 해제할 때 DNS 항목을 관리하는 방법에 대한 지침입니다.
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671884"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>조직이 모두 Teams만 될 수 있도록 DNS 항목을 업데이트합니다.

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이전에 비즈니스용 Skype 서버 또는 Lync Server의 온-프레미스 배포가 있었던 조직에는 온-프레미스 비즈니스용 Skype 배포를 가리키는 DNS 항목이 여전히 있을 수 있습니다. 조직에 온-프레미스 비즈니스용 Skype 사용자가 포함된 경우 이러한 레코드가 필요합니다. 그러나 조직에 온-프레미스 비즈니스용 Skype 또는 Lync Server 사용자가 더 이상 없으면 이러한 원본 레코드는 더 이상 온-프레미스 배포에 필요하지 않으며 이러한 DNS 항목은 온-프레미스에서 Teams 전용으로 마이그레이션하는 과정의 일부로 **Microsoft 365(또는 경우에 따라 제거됨)을 가리키도록 업데이트해야 합니다**. *Microsoft는 사용자 대신 이러한 DNS 레코드를 업데이트할 수 없습니다.*

전체 테넌트에 TeamsOnly를 부여하려고 할 때 Teams DNS를 확인하여 아래에 나열된 이러한 DNS 레코드가 조직의 각 Microsoft 365 확인된 도메인에 있는지 확인합니다. 레코드가 발견되고 Microsoft 365 이외의 항목을 가리키는 경우 테넌트 공존 모드를 TeamsOnly로 변경하려는 시도는 의도적으로 실패합니다. 이렇게 하면 온-프레미스 사용자가 있는 하이브리드 조직에서 실수로 TeamsOnly 모드를 테넌트에 적용할 수 없습니다. 이렇게 하면 조직의 모든 온-프레미스 비즈니스용 Skype 사용자(Teams 또는 비즈니스용 Skype 사용)에 대한 페더레이션이 중단됩니다.

## <a name="how-to-identify-stale-dns-records"></a>부실 DNS 레코드를 식별하는 방법

조직이 모든 Teams만 되는 것을 방지하는 DNS 레코드를 식별하려면 Teams 관리 센터를 사용하여 공존 모드를 TeamsOnly로 변경할 수 있습니다. **Teams** >  **Teams 업그레이드 설정** 으로 이동합니다. 조직이 Teams 않도록 하는 모든 DNS 레코드만 오류 메시지에 포함됩니다.  DNS 레코드를 찾을 수 없는 경우 조직의 공존 모드가 TeamsOnly로 변경됩니다.

또는 아래와 같이 Teams PowerShell을 사용하여 동일한 작업을 수행할 수 있습니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>업데이트할 DNS 레코드

조직에 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server에 호스트된 사용자가 더 이상 없는 경우 다음을 수행해야 합니다.

- 온-프레미스 배포 대신 Microsoft 365 가리키도록 아래의 비즈니스용 Skype DNS 레코드 목록을 업데이트합니다. 둘 이상의 SIP 도메인이 있는 경우 Microsoft 365 확인된 도메인인 각 SIP 도메인에 대해 이 작업을 수행해야 합니다.

- SIP 도메인이 더 이상 사용되지 않는 경우 비즈니스용 Skype DNS 레코드를 제거합니다.

다음 레코드를 찾을 수 있는 각 도메인에서 다음과 같이 업데이트합니다.

|레코드 유형|이름|TTL|우선 순위|가중치|포트|값|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|해당 없음|해당 없음|해당 없음|webdir.online.lync.com|
|CNAME|sip|3600|해당 없음|해당 없음|해당 없음|sipdir.online.lync.com|

또한 모임 또는 다이얼린(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다. 마지막으로 내부 네트워크의 비즈니스용 Skype 대한 모든 DNS 레코드를 제거해야 합니다.

> [!NOTE]
> 드물게 DNS를 온-프레미스에서 조직의 Microsoft 365 가리키도록 변경하면 다른 조직에서 페더레이션 구성을 업데이트할 때까지 다른 조직과의 페더레이션이 중지될 수 있습니다.
>
> - 이전 직접 페더레이션 모델(허용된 파트너 서버라고도 함)을 사용하는 페더레이션된 조직은 프록시 FQDN을 제거하기 위해 해당 조직에 대해 허용된 도메인 항목을 업데이트해야 합니다. 이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 조직이 클라우드로 이동하면 이러한 구성이 만료됩니다.
>
> - sipfed.online.lync<span>에 대해 사용하도록 설정된 호스팅 공급자가 없는 페더레이션된 조직 com은 해당 구성을 업데이트하여 사용하도록 설정해야 합니다. 이 상황은 페더레이션된 조직이 순전히 온-프레미스이고 하이브리드 또는 온라인 테넌트와 페더레이션된 적이 없는 경우에만 가능합니다. 이러한 경우 이러한 조직과의 페더레이션은 호스팅 공급자를 사용하도록 설정할 때까지 작동하지 않습니다.
>
> 페더레이션된 파트너가 직접 페더레이션을 사용하고 있거나 온라인 또는 하이브리드 조직과 페더레이션되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 통신을 보내는 것이 좋습니다.
