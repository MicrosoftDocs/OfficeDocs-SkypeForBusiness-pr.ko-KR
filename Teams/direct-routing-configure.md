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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 온-프레미스 전화 통신 인프라를 Microsoft 팀에 연결 하기 위해 Microsoft 전화 시스템 직접 라우팅을 구성 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1c19bfcd4c220ff6b6c53d8731149eaa8b6b4b1
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031774"
---
# <a name="configure-direct-routing"></a>직접 라우팅 구성

Microsoft 전화 시스템 다이렉트 라우팅을 사용 하 여 온-프레미스 전화 통신 인프라를 Microsoft 팀에 연결할 수 있습니다. 이 문서에는 지원 되는 온-프레미스 세션 경계 컨트롤러 (SBC)를 다이렉트 라우팅과 연결 하는 데 필요한 상위 단계와 팀 사용자가 PSTN (공개 통신 네트워크)에 연결 하기 위해 직접 라우팅을 사용 하도록 구성 하는 방법에 대 한 개요가 나와 있습니다. 이 문서는 관련 문서에 대 한 자세한 내용 링크를 제공 합니다.  

직접 라우팅이 조직에 적합 한 솔루션 인지 여부에 대 한 자세한 내용은 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참조 하세요. 필수 구성 요소 및 배포 계획에 대 한 자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md)을 참조 하세요.

> [!Tip]
> 또한 다음 세션을 시청 하 여 다이렉트 라우팅의 이점과이를 위해 계획 하는 방법, 그리고 배포 하는 방법에 대해 알아볼 수 있습니다. [Microsoft 팀의 직접적인 라우팅](https://aka.ms/teams-direct-routing).

이 문서에서 설명 하는 단계를 완료 하려면 관리자가 PowerShell cmdlet에 대해 잘 알고 있어야 합니다. PowerShell을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요. 

이 문서의 단계를 수행 하기 전에 sbc 공급 업체에서 권장 하는 것으로 SBC가 이미 구성 되어 있는지 확인 하는 것이 좋습니다. 

- [오디오 코드 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 문서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 커뮤니케이션 배포 문서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-시스템 (anynode) 배포 문서](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 배포 설명서](https://www.metaswitch.com/products/core-network/perimeta-sbc)

지원 되는 SBCs의 전체 목록은 [직접 라우팅으로 인증 된 세션 경계 컨트롤러 목록을](direct-routing-border-controllers.md)참조 하세요.

Microsoft 전화 시스템을 구성 하 고 사용자가 직접 라우팅을 사용할 수 있도록 설정 하려면 다음 단계를 따릅니다. 

- **1 단계.** [Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인](direct-routing-connect-the-sbc.md)
- **2 단계.** [사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정](direct-routing-enable-users.md)
- **3 단계.** [음성 라우팅 구성](direct-routing-voice-routing.md)
- **4 단계.** [숫자를 대체 형식으로 번역](direct-routing-translate-numbers.md) 

여러 테 넌 트에 대 한 SBC를 구성 하는 경우에는 [여러 테 넌 트에 대 한 Sbc 구성을](direct-routing-sbc-multiple-tenants.md)읽어 볼 수도 있습니다.


## <a name="related-topics"></a>관련 주제

[전화 시스템 직접 라우팅](direct-routing-landing-page.md)

[직접 라우팅 계획](direct-routing-plan.md)

