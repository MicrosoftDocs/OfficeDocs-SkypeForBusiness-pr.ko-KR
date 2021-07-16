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
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458995"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>조직이 모든 사용자만 사용할 수 있도록 DNS Teams 업데이트

이전에 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server를 배포한 조직에는 온-프레미스 배포를 비즈니스용 Skype DNS 항목이 있을 수 있습니다. 이러한 레코드는 조직에 사용자가 있는 경우 비즈니스용 Skype 필요합니다. 그러나 조직에 더 이상 온-프레미스 비즈니스용 Skype Lync Server 사용자가 없는 경우 이러한 레코드는 더 이상 필요하지 않습니다. 또한 실제로, 마이그레이션을 완료하는 일부로, Teams 레코드를 업데이트하여 Microsoft 365 제거해야 합니다. Microsoft는 이 단계를 취할 수 없습니다.

전체 테넌트에 TeamsOnly를 부여하려고 할 Teams DNS를 확인하여 조직에 대한 이러한 DNS 레코드가 있는지 여부를 확인할 수 있습니다. 레코드가 발견되어 레코드가 다른 레코드를 Microsoft 365 경우 테넌트 공존 모드를 TeamsOnly로 변경하려고 하면 디자인에 실패합니다. 이 디자인은 테넌트에 TeamsOnly 모드를 실수로 적용하지 못하게 하는 하이브리드 조직을 방지하기 위한 것입니다. 이렇게 하면 모든 비즈니스용 Skype 사용자(Teams 또는 테넌트 사용 여부에 비즈니스용 Skype)에 대한 페더넌트가 중단됩니다.

또한 전체 테넌트에 TeamsOnly를 부여할 수 있도록 이러한 레코드를 업데이트해야 합니다.

> [!Note] 
> 드문 경우지만 DNS를 조직에 대한 Microsoft 365 설정으로 변경하면 다른 조직에서 페더링 구성을 업데이트할 때까지 일부 다른 조직과의 페더링이 중지될 수 있습니다.
>
> - 이전 Direct Federation 모델(허용 파트너 서버라고도 지칭)을 사용하는 페더러된 조직은 조직에 대해 허용되는 도메인 항목을 업데이트하여 프록시 FQDN을 제거해야 합니다. 이 레거시 페더전 모델은 DNS SRV 레코드를 기반으로 하지 않습니다. 따라서 조직이 클라우드로 이동하면 이러한 구성이 최신이 됩니다.
> 
> - sipfed.online.lync에 대해 호스팅 공급자를 사용하도록 설정하지 않은 페더링된 조직입니다. <span> com은 구성을 업데이트하여 사용하도록 설정해야 합니다. 이 상황은 페더러드 조직이 전적으로 사내에 있으며 하이브리드 또는 온라인 테넌트와 페더러이트한 적이 없는 경우만 가능합니다. 이 경우 호스팅 공급자를 사용하도록 설정해야 이러한 조직과의 페더링이 작동하지 않습니다.
>
> 페더더러 파트너 중 한 자가 직접 페더ation을 사용 중일 수 있는 것으로 의심되거나 온라인 또는 하이브리드 조직과 페더러이트되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 통신을 해당 파트너에게 보내는 것이 좋은 제안입니다.

## <a name="how-to-identify-stale-dns-records"></a>부실한 DNS 레코드를 식별하는 방법

조직에서 모든 DNS 레코드만 Teams DNS 레코드를 식별하려면 Teams 관리 센터를 사용하여 공존 모드를 TeamsOnly로 변경할 수 있습니다. 업그레이드 **에서 Org 전체**  ->  **Teams 로 이동하십시오.** 조직이 모든 DNS 레코드를 Teams 오류 메시지에 포함됩니다.  DNS 레코드가 발견되지 않으면 조직의 공존 모드가 TeamsOnly로 변경됩니다. 

## <a name="how-to-remove-stale-dns-records"></a>부실한 DNS 레코드를 제거하는 방법

조직에 더 이상 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server 사용자가 없는 경우 다음을 실행해야 합니다.

- DNS 비즈니스용 Skype 업데이트하여(Microsoft 365 배포 대신) DNS 레코드를 업데이트합니다.

- SIP 비즈니스용 Skype 더 이상 사용되지 않으면 DNS 레코드를 제거합니다. 

다음 레코드를 찾은 각 도메인에서 다음과 같이 업데이트합니다.

| 레코드 유형 | 이름 | TTL | 우선 순위 | 가중치 | 포트 | 값 |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1  | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1    | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  해당 없음 |   해당 없음 |   해당 없음 |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    해당 없음 |   해당 없음  | 해당 없음 |    sipdir.online.lync.com |
|||||||




