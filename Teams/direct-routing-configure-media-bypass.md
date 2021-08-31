---
title: 직접 라우팅을 위한 미디어 바이패스 구성
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 모든 사용자를 한 전화 시스템 단계적 접근(권장)을 구현하여 전화 시스템 직접 라우팅을 사용하여 미디어 우회를 구성하는 Microsoft Teams 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0f0ad9d25157058c048b0f12cf72b3755e65e11
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728687"
---
# <a name="configure-media-bypass-with-direct-routing"></a>직접 라우팅을 위한 미디어 바이패스 구성

직접 라우팅을 통해 미디어 우회를 구성하기 전에 직접 라우팅을 사용하는 미디어 우회 계획 [을 읽어야 합니다.](direct-routing-plan-media-bypass.md)

미디어 우회를 설정하려면 다음 조건을 충족해야 합니다.

1.    선택의 세션 경계 컨트롤러(SBC) 공급업체가 미디어 우회를 지원하고 SBC에서 우회를 구성하는 방법에 대한 지침을 제공해야 합니다. 인증 페이지를 참조하여 미디어 우회를 지원하는 SBC에 대해 알아보고 지침을 참조하세요.

2.    **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass**$true.

3.    필요한 포트가 열립니다. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>비우회 트렁크에서 우회 사용 트렁크로 마이그레이션

모든 사용자를 한 번씩 전환하거나 단계적 접근(권장)을 구현할 수 있습니다.

- **모든 사용자를 한 번씩 전환합니다.** 모든 조건이 충족된 경우 우회 모드를 켜면 됩니다. 그러나 모든 프로덕션 사용자가 동시에 전환됩니다. 트렁크 및 포트를 구성할 때 처음에 몇 가지 문제가 있을 수 있기 때문에 프로덕션 사용자 환경이 영향을 받을 수 있습니다. 

- **단계적 접근 방식입니다. (권장)**.  동일한 SBC에 대한 새 트렁크를 만들고(다른 포트를 사용하여) 테스트하고, 사용자가 새 트렁크를 지적할 수 있도록 온라인 음성 라우팅 정책을 변경합니다. 

  이 방법은 더 원활한 전환 및 사용자 환경을 원활하게 할 수 있기 때문에 권장되는 접근 방식입니다. 이 접근 방식에는 SBC 구성, 새 FQDN 이름 및 방화벽 구성이 필요합니다. 인증서가 두 트렁크를 모두 지원하는지 확인해야 합니다. SAN에서 두 개의 이름(sbc1.contoso.com 및 **sbc2.contoso.com)** 또는 와일드카드 인증서가 필요합니다.

![비우회 트렁크에서 우회 지원 트렁크로 마이그레이션합니다.](media/direct-routing-media-bypass-8.png)

트렁크를 구성하고 마이그레이션을 수행하는 방법에 대한 지침은 SBC 공급업체의 설명서를 참조하세요.

- [AudioCodes 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 설명서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 통신 배포 설명서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems(anynode) 배포 설명서](https://www.anynode.de/anynode-and-microsoft-teams/)

직접 라우팅에 대해 인증된 SBC(세션 테두리 컨트롤러) 목록은 직접 라우팅에 대해 인증된 세션 브로더 컨트롤러 목록을 [참조하세요.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>관련 항목

[직접 라우팅을 통해 미디어 우회 계획](direct-routing-plan-media-bypass.md)



