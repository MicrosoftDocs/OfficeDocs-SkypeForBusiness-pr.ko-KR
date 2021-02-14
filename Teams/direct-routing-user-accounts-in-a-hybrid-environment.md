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
description: 사용자 만들기의 다양한 조합과 지원되거나 지원되지 않는 조합에 대해 자세히 배워야 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7b41eb474d7574aa23b5fa195219794ed715424
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690874"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 연결이 포함된 하이브리드 환경의 사용자 계정

## <a name="about-the-environment"></a>환경 정보를

이 문서는 다음이 모두 있는 환경에 적용됩니다. 
 
- 비즈니스용 Skype Server 또는 Lync Server 2013 
- Microsoft 365 또는 Office 365 조직 
- 비즈니스용 Skype Server와 비즈니스용 Skype Online 또는 Microsoft Teams 테넌트 간에 구성된 하이브리드 연결 
- 클라이언트와의 PSTN(Public Switched Telephone Network) 통화를 걸고 받을 수 있는 사용자

 
다른 환경(예: 비즈니스용 Skype Cloud Connector Edition)이 있는 경우 하이브리드가 구성되지 않은 경우 또는 사용자가 PSTN 통화에 대해 사용하도록 설정되지 않은 경우 지원 가능성 매트릭스가 다릅니다.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>조합 및 지원 가능성 설명  

PSTN 연결이 있는 비즈니스용 Skype 하이브리드 환경은 사용자 서비스가 제공되는 위치 및 사용자 계정이 프로비전 및 관리되는 방식에 대한 유연성을 제공합니다. 하지만 옵션이 풍부하면 일부 비지원 조합이 생성될 수 있습니다. 이 섹션에서는 사용자 만들기의 다양한 조합과 지원 가능성 설명을 설명합니다.


**정의:**   
- **Enterprise Voice:** 비즈니스용 Skype 사용자 계정이 있는 사용자를 위해 PSTN에 대한 액세스를 제공하는 옵션입니다. 비즈니스용 Skype 중재 서버는 PSTN에 대한 상호 연결 기능을 제공합니다.  
- **하이브리드 음성 연결:** 비즈니스용 Skype Online 계정을 사용하는 사용자를 위해 PSTN에 대한 액세스를 제공하는 옵션입니다. 비즈니스용 Skype 중재 서버는 PSTN에 대한 상호 연결 기능을 제공합니다. 
- **직접 라우팅:** Microsoft Teams 클라이언트를 사용하여 온라인 비즈니스용 Skype 계정, Microsoft Teams 라이선스가 있는 사용자를 위해 PSTN에 대한 액세스를 제공하는 옵션입니다. SBC는 Microsoft의 모든 On-프레미스 소프트웨어 없이도 Microsoft 365 또는 Office 365의 SIP 프록시에 연결됩니다.

  
**환경은 다음 조합을 지원합니다.**
- **시나리오 1:** 비즈니스용 Skype의 사용자 계정과 비즈니스용 Skype 클라이언트를 Enterprise Voice
- **시나리오 2:** 비즈니스용 Skype의 사용자 계정으로, 하이브리드 음성 연결과 함께 비즈니스용 Skype 클라이언트를 사용하게 됩니다.
- **시나리오 3:** Microsoft Teams 라이선스가 있는 비즈니스용 Skype의 사용자 계정 및 Teams 클라이언트 사용
 
### <a name="supportability-matrix"></a>지원 가능성 매트릭스


|**에서 만든 사용자 개체**  |**사용자의 비즈니스용 Skype 서비스 공급자**|**사용자의 클라이언트**|**음성 옵션**|**지원**|
| ------------ | --------- | --------- | --------- | -------- |
|프레미스 AD| 프레미스 |비즈니스용 Skype   | Enterprise Voice   |예|
|프레미스 AD|온라인| 비즈니스용 Skype  | 하이브리드 음성 연결   |예 |
|프레미스 AD|온라인 |Microsoft Teams |직접 라우팅  |예 |
|**비지원 조합**    | |         |         |      |
|Azure AD| On premises/online | 비즈니스용 Skype/Microsoft Teams|Enterprise Voice/하이브리드 음성 연결/직접 라우팅  |아니요, 사용자 개체는 먼저 On-프레미스 AD에서 만들어야 합니다. |
|프레미스 AD  |프레미스| Microsoft Teams| Enterprise Voice/하이브리드 음성 연결/직접 라우팅   |아니요, Microsoft Teams 클라이언트는 비즈니스용 Skype에서 지원되지 않습니다. |     
|프레미스 AD  |온라인 |비즈니스용 Skype  | 직접 라우팅  |아니요, 직접 라우팅은 비즈니스용 Skype 클라이언트에서 지원되지 않습니다.  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN을 통해 하이브리드 환경에 대한 지원 가능성 설명

모든 사용자의 경우 사용자  개체는 Azure AD Connect 도구를 사용하여 Azure AD에 동기화되어 있어야 합니다. 사용자 개체가 하이브리드 구성에서  Azure AD에서 직접 만들어진 경우 Teams/비즈니스용 Skype 사용자를 사용하도록 설정하는 것은 지원되지 않습니다. Teams에 대해 직접 활성화될 신입 직원과 같은 신규 사용자의 경우 사용자는 비즈니스용 Skype 관리 도구를 사용하여 비즈니스용 Skype를 사용하도록 설정해야 합니다. 온라인 비즈니스용 Skype 또는 Teams에서 사용자를 만들기 위해 먼저 사용자 계정이 있는 Enterprise Voice **지원되지 않습니다.** 이에 대한 자세한 내용은 비즈니스용 Skype Server에서 프레미스 PSTN 연결을 통해 휴대폰 시스템 [계획에 대해 살펴봐야 합니다.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
