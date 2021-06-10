---
title: PSTN을 통해 하이브리드 환경의 사용자 계정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 사용자 만들기의 다양한 조합과 지원되거나 지원되지 않는 조합에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096328"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 연결이 포함된 하이브리드 환경의 사용자 계정

## <a name="about-the-environment"></a>환경에 대해

이 문서는 다음과 같은 모든 환경이 있는 환경에 적용됩니다. 
 
- 비즈니스용 Skype 서버 또는 Lync Server 2013 
- Microsoft 365 또는 Office 365 조직 
- 온라인 또는 비즈니스용 Skype 서버 비즈니스용 Skype 테넌트 간에 구성된 하이브리드 Microsoft Teams 연결 
- 클라이언트에서 PSTN(공용 전환 전화 네트워크)을 호출하고 받을 수 있는 사용자

 
다른 환경(예: 비즈니스용 Skype 클라우드 커넥터 버전) 하이브리드가 구성되지 않은 경우 또는 사용자가 PSTN 호출에 대해 사용하도록 설정되지 않은 경우 지원 매트릭스가 다릅니다.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>조합 및 지원 가능성 문에 대해  

PSTN 비즈니스용 Skype 하이브리드 환경은 사용자 서비스가 제공되는 위치 및 사용자 계정 프로비전 및 관리 방법에 대한 유연성을 제공합니다. 그러나 옵션이 풍부하면 몇 가지 비지원 조합이 생성될 수 있습니다. 이 섹션에서는 사용자 만들기의 다양한 조합과 지원 가능성 문을 설명합니다.


**정의:**   
- **Enterprise Voice:** 프레미스 및 사용자 계정을 사용하는 사용자를 위해 PSTN에 비즈니스용 Skype 옵션입니다. 프레미스 비즈니스용 Skype 미디어 서버는 PSTN에 상호 연결 기능을 제공합니다.  
- **하이브리드 음성 연결:** 온라인 계정이 있는 사용자를 위해 PSTN에 비즈니스용 Skype 옵션입니다. 프레미스 비즈니스용 Skype 미디어 서버는 PSTN에 상호 연결 기능을 제공합니다. 
- **직접 라우팅:** 온라인 계정, 비즈니스용 Skype 사용자에 대한 PSTN에 대한 액세스를 Microsoft Teams 클라이언트를 사용하여 Microsoft Teams 옵션입니다. SBC는 Microsoft의 모든 Microsoft 365 Office 365 SIP 프록시에 연결됩니다.

  
**환경은 다음 조합을 지원합니다.**
- **시나리오 1:** 프레미스 비즈니스용 Skype 사용자 계정과 함께 비즈니스용 Skype 클라이언트를 Enterprise Voice
- **시나리오 2:** 온라인 비즈니스용 Skype 사용자 계정으로 하이브리드 음성 비즈니스용 Skype 클라이언트를 사용할 것입니다.
- **시나리오 3:** 온라인에서 비즈니스용 Skype 라이선스가 Microsoft Teams 사용자 계정과 클라이언트 Teams 사용
 
### <a name="supportability-matrix"></a>지원성 매트릭스


|**에서 만든 사용자 개체**  |**사용자의 비즈니스용 Skype 서비스 공급자**|**사용자의 클라이언트**|**음성 옵션**|**지원되는**|
| ------------ | --------- | --------- | --------- | -------- |
|ON-프레미스 AD| On-Premises |비즈니스용 Skype   | Enterprise Voice   |예|
|ON-프레미스 AD|온라인| 비즈니스용 Skype  | 하이브리드 음성 연결   |예 |
|ON-프레미스 AD|온라인 |Microsoft Teams |직접 라우팅  |예 |
|**비지원 조합**    | |         |         |      |
|Azure AD| 온라인 프레미스/온라인 | 비즈니스용 Skype/Microsoft Teams|Enterprise Voice/하이브리드 음성 연결/직접 라우팅  |아니요, 사용자 개체는 먼저 ON-프레미스 AD에서 만들어야 합니다. |
|ON-프레미스 AD  |On-Premises| Microsoft Teams| Enterprise Voice/하이브리드 음성 연결/직접 라우팅   |아니요, Microsoft Teams 클라이언트가 프레미스에서 지원되지 비즈니스용 Skype |     
|ON-프레미스 AD  |온라인 |비즈니스용 Skype  | 직접 라우팅  |아니요, 직접 라우팅은 클라이언트에서 지원되지 비즈니스용 Skype 없습니다.  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN을 통해 하이브리드 환경에 대한 지원 가능성 문

모든 사용자의 경우 사용자  개체를 On-프레미스 AD에서 만들어 Azure AD 커넥트 사용하여 Azure AD에 동기화해야 합니다. 사용자 개체가 하이브리드 구성에서 Azure AD에서 직접 Teams/비즈니스용 Skype 사용자를 사용하도록 설정하는 것은 지원되지 않습니다.  새 고용과 같은 새 사용자에 대해 직접 사용하도록 설정될 Teams, 사용자는 비즈니스용 Skype 관리 도구를 사용하여 비즈니스용 Skype 사용하도록 비즈니스용 Skype 있어야 합니다. 온라인 비즈니스용 Skype 또는 Teams 사용자 만들기는 Enterprise Voice **지원되지 않습니다.** 이에 대한 자세한 내용은 에서 전화 시스템 [PSTN](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)연결을 통해 계획 비즈니스용 Skype 서버.