---
title: 직접 라우팅으로 미디어 우회 구성
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 이 항목에서는 전화 시스템 다이렉트 라우팅과 함께 미디어 바이패스를 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 2931194783e2055c468ec2d7ad1286b9fe1940ae
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572237"
---
# <a name="configure-media-bypass-with-direct-routing"></a>직접 라우팅으로 미디어 우회 구성

직접 라우팅으로 미디어 바이패스를 구성 하기 전에 [다이렉트 라우팅이 미디어 바이패스에 대 한 계획](direct-routing-plan-media-bypass.md)을 확인 해야 합니다.

미디어 바이패스를 설정 하려면 다음 조건을 충족 해야 합니다.

1.  선택 사항에 대 한 SBC (세션 경계 컨트롤러) 공급 업체가 미디어 바이패스를 지원 하는지 확인 하 고 SBC에서 bypass를 구성 하는 방법에 대 한 지침을 제공 합니다. 사용 중인 SBCs에 대 한 자세한 내용은 인증 페이지를 참조 하 고 미디어 바이패스에 대 한 지침을 제공 하세요.

2.  **CSOnlinePSTNGateway-id <sbc_FQDN>-MediaBypass $true**명령을 사용 하 여 트렁크에서 미디어 바이패스를 설정 해야 합니다.

3.  필요한 포트가 열려 있는지 확인 합니다. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>우회 되지 않은 trunks에서 우회 가능 trunks 마이그레이션

모든 사용자를 한 번에 전환 하거나 단계별 접근을 구현할 수 있습니다 (권장).

- **모든 사용자를 한 번에 전환 합니다.** 모든 조건이 충족 되는 경우 우회 모드를 켤 수 있습니다. 그러나 모든 프로덕션 사용자가 동시에 전환 됩니다. Trunks 및 포트를 구성할 때 초기에 몇 가지 문제가 발생할 수 있으므로 프로덕션 사용자 환경에 영향을 미칠 수 있습니다. 

- **단계적 접근. (권장)**.  동일한 SBC에 대해 다른 포트를 사용 하 여 새 트렁크를 만들고 테스트 한 다음 사용자가 새 트렁크를 가리키도록 온라인 음성 라우팅 정책을 변경 합니다. 

  이 방법을 사용 하는 것이 좋습니다. 전환 및 지속적으로 중단 되는 사용자 환경이 가능 합니다. 이 접근 방법에는 SBC, 새 FQDN 이름, 방화벽 구성 등의 구성이 필요 합니다. 참고 인증서가 두 trunks를 모두 지원 하는지 확인 해야 합니다. SAN에는 두 개의 이름 (**sbc1.contoso.com** 및 **sbc2.contoso.com**)이 있거나 와일드 카드 인증서가 있어야 합니다.

![무시할 수 없는 trunks에서 bypass trunks)로 마이그레이션](media/direct-routing-media-bypass-8.png)

Trunks를 구성 하 고 마이그레이션을 수행 하는 방법에 대 한 지침은 SBC 공급 업체의 설명서를 참조 하세요.

- [오디오 코드 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 문서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 커뮤니케이션 배포 문서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-시스템 (anynode) 배포 문서](https://www.anynode.de/anynode-and-microsoft-teams/)

직접 라우팅으로 인증 된 SBCs (세션 경계 컨트롤러) 목록은 [직접 라우팅에 대해 인증 된 세션 경계선 컨트롤러 목록을](direct-routing-border-controllers.md)참조 하세요.



## <a name="see-also"></a>참고 항목

[직접 라우팅으로 미디어 바이패스 계획](direct-routing-plan-media-bypass.md)



