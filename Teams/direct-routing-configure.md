---
title: 직접 라우팅 구성
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 온-프레미스 전화 통신 인프라를 Teams Phone System에 연결하도록 Microsoft 직접 라우팅을 구성하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf6a180b558edad23450fad3991ee2c646f6cf55
ms.sourcegitcommit: 830357674103c0c5c99bd73d40261afe02a2da49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2022
ms.locfileid: "67291404"
---
# <a name="configure-direct-routing"></a>직접 라우팅 구성

직접 라우팅을 사용하면 온-프레미스 전화 통신 인프라를 Microsoft Teams에 연결할 수 있습니다. 이 문서에서는 지원되는 온-프레미스 SBC(세션 테두리 컨트롤러)를 직접 라우팅에 연결하는 데 필요한 개략적인 단계와 직접 라우팅을 사용하여 PSTN(공중 전화망)에 연결하도록 Teams 사용자를 구성하는 방법을 나열합니다. 이 문서에서는 관련 문서에 연결하여 세부 정보를 확인합니다.  

직접 라우팅이 조직에 적합한 솔루션인지 여부에 대한 자세한 내용은 [PSTN 연결 옵션을](pstn-connectivity.md) 참조하세요. 필수 구성 요소 및 배포 계획에 대한 자세한 내용은 [직접 라우팅 계획을](direct-routing-plan.md) 참조하세요.

이 문서에 설명된 단계를 완료하려면 관리자가 PowerShell cmdlet에 대해 잘 알고 있어야 합니다. PowerShell 사용에 대한 자세한 내용은 [Windows PowerShell 컴퓨터 설정을 참조하세요](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

이 문서의 단계를 수행하기 전에 SBC 공급업체에서 권장하는 대로 SBC가 이미 구성되어 있는지 확인하는 것이 좋습니다. 

- [AudioCodes 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 설명서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 통신 배포 설명서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems(anynode) 배포 설명서](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 배포 설명서](https://www.metaswitch.com/products/core-network/perimeta-sbc)

지원되는 SCC의 전체 목록은 [직접 라우팅에 대해 인증된 세션 테두리 컨트롤러를 참조하세요](direct-routing-border-controllers.md).

전화 시스템을 구성하고 사용자가 직접 라우팅을 사용할 수 있도록 하려면 다음 단계를 수행합니다. 

- **1단계.** [SBC를 전화 시스템에 연결하고 연결의 유효성을 검사합니다.](direct-routing-connect-the-sbc.md)
- **2단계.** [사용자가 직접 라우팅, 음성 및 음성 메일을 사용하도록 설정](direct-routing-enable-users.md)
- **3단계.** [통화 라우팅 구성](direct-routing-voice-routing.md)
- **4단계.** [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md) 

여러 테넌트에 대해 SBC를 구성하는 경우 여러 테넌트에 [대한 SBC 구성](direct-routing-sbc-multiple-tenants.md)을 읽어도 됩니다.

## <a name="support-boundaries"></a>지원 경계
Microsoft는 인증 디바이스로 사용하는 경우에만 직접 라우팅을 사용하는 전화 시스템을 지원합니다. 문제가 있는 경우 먼저 SBC 공급업체의 고객 지원에 문의해야 합니다. 필요한 경우 SBC 공급업체에서 내부 채널을 통해 Microsoft로 문제를 에스컬레이션합니다. Microsoft에는 인증되지 않은 디바이스에서 직접 라우팅을 통해 전화 시스템에 연결할 경우 지원을 거부할 권리가 있습니다. Microsoft에서 고객의 직접 라우팅 문제가 공급업체의 SBC 장치와 관련된 것으로 판단되면 고객은 SBC 공급업체에 다시 참여를 요청해야 합니다.

## <a name="related-topics"></a>관련 주제

[음성 솔루션 계획](cloud-voice-landing-page.md)

[PSTN 연결 옵션](pstn-connectivity.md)

[직접 라우팅 계획](direct-routing-plan.md)
