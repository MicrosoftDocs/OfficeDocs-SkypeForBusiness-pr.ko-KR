---
title: 직접 라우팅 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
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
description: Microsoft Phone System Direct 라우팅을 구성하여온-프레미스 전화 통신 인프라를 Microsoft Teams에 연결하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122242"
---
# <a name="configure-direct-routing"></a>직접 라우팅 구성

Microsoft Phone System 직접 라우팅을 사용하면온-프레미스 전화 통신 인프라를 Microsoft Teams에 연결할 수 있습니다. 이 문서에서는 지원되는 SBC(On-Premises Session Border Controller)를 직접 라우팅에 연결하는 데 필요한 고급 단계와 PSTN(공용 전환 전화 네트워크)에 연결하는 직접 라우팅을 사용하도록 Teams 사용자를 구성하는 방법을 나열합니다. 이 문서는 관련 문서에 연결하여 자세한 내용을 제공합니다.  

직접 라우팅이 조직에 적합한 솔루션인지 여부에 대한 자세한 내용은 전화 시스템 직접 라우팅 [을 참조하세요.](direct-routing-landing-page.md) 필요한 구성 및 배포 계획에 대한 자세한 내용은 직접 라우팅 계획 [을 참조하세요.](direct-routing-plan.md)

> [!Tip]
> 또한 다음 세션을 통해 직접 라우팅의 이점, 계획을 세우는 방법 및 배포 방법: Microsoft Teams의 직접 라우팅에 대해 자세히 알아보는 방법을 볼 [수 있습니다.](https://aka.ms/teams-direct-routing)

이 문서에서 설명하는 단계를 완료하려면 관리자는 PowerShell cmdlet에 익숙해야 합니다. PowerShell 사용에 대한 자세한 내용은 에 대한 컴퓨터 [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

이 문서의 단계를 수행하기 전에 Microsoft는 SBC 공급업체에서 권장하는 SBC가 이미 구성되어 있는지 확인하는 것이 좋습니다. 

- [AudioCodes 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 설명서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 통신 배포 설명서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems(anynode) 배포 설명서](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 배포 설명서](https://www.metaswitch.com/products/core-network/perimeta-sbc)

지원되는 SBC의 전체 목록은 직접 라우팅에 대해 인증된 세션 테두리 컨트롤러 [목록을 참조하세요.](direct-routing-border-controllers.md)

Microsoft Phone System을 구성하고 사용자가 직접 라우팅을 사용할 수 있도록 설정하려면 다음 단계를 수행합니다. 

- **1단계.** [Microsoft Phone System을 사용하여 SBC 연결 및 연결 유효성 검사](direct-routing-connect-the-sbc.md)
- **2단계.** [직접 라우팅, 음성 및 음성메일에 사용자를 사용하도록 설정](direct-routing-enable-users.md)
- **3단계.** [음성 라우팅 구성](direct-routing-voice-routing.md)
- **4단계.** [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md) 

여러 테넌트에 대한 SBC를 구성하는 경우 여러 테넌트에 대한 SBC 구성 [을 읽어야 합니다.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>관련 항목

[전화 시스템 직접 라우팅](direct-routing-landing-page.md)

[직접 라우팅 계획](direct-routing-plan.md)