---
title: PSTN 연결을 사용 하는 하이브리드 환경의 사용자 계정
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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 사용자 만들기와 지원 또는 지원 되지 않는 조합에 대 한 다양 한 조합에 대해 알아봅니다.
ms.openlocfilehash: c8473fcaf6fb8b5b24f68d934cd3451ebeb8e038
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182351"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 연결을 사용 하는 하이브리드 환경의 사용자 계정

## <a name="about-the-environment"></a>환경에 대 한 정보

이 문서는 다음이 모두 있는 환경에 적용 됩니다. 
 
- 비즈니스용 Skype 서버 또는 Lync Server 2013 
- Office 365 테 넌 트 
- 비즈니스용 Skype 서버와 비즈니스용 Skype Online 또는 Microsoft 팀 테 넌 트 간에 하이브리드 연결이 구성 되었습니다. 
- 클라이언트와의 PSTN (공개 교환 네트워크) 전화를 걸고 받을 수 있는 사용자

 
다른 환경 (예: 비즈니스용 Skype 클라우드 커넥터 에디션)이 있는 경우 하이브리드이 구성 되지 않았거나 사용자가 PSTN 호출을 사용할 수 있도록 설정 되지 않은 경우 지원 가능 행렬이 달라 집니다.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>조합 및 지원 가능성 문에 대 한 정보  

PSTN 연결을 사용 하는 비즈니스용 Skype 하이브리드 환경에서는 사용자 서비스가 제공 되는 위치와 사용자 계정이 어떻게 프로 비전 되 고 관리 되는지에 대 한 유연성을 제공 합니다. 그러나 여러 옵션을 선택 하면 지원 되지 않는 조합이 생성 될 것입니다. 이 섹션에서는 사용자 만들기의 다양 한 조합에 대해 설명 하 고 그 뒤에 지원 문을 사용 합니다.


**용어**   
- **엔터프라이즈 음성:** 온-프레미스 비즈니스용 Skype 사용자 계정을 사용 하는 사용자를 위해 PSTN에 대 한 액세스를 제공 하는 옵션입니다. 온-프레미스 비즈니스용 Skype 중재 서버는 PSTN에 interconnectivity을 제공 합니다.  
- **하이브리드 음성 연결:** 비즈니스용 Skype Online 계정이 있는 사용자의 PSTN에 대 한 액세스를 제공 하는 옵션입니다. 온-프레미스 비즈니스용 Skype 중재 서버는 PSTN에 interconnectivity을 제공 합니다. 
- **다이렉트 라우팅:** Microsoft 팀 클라이언트를 사용 하 여 온라인 비즈니스용 Skype 계정, Microsoft 팀 라이선스가 있는 사용자에 게 PSTN에 대 한 액세스를 제공 하는 옵션입니다. SBC는 Microsoft의 온-프레미스 소프트웨어를 사용할 필요 없이 Office 365의 SIP 프록시에 연결 되어 있습니다.

  
**환경에서 지원 되는 조합은 다음과 같습니다.**
- **시나리오 1:** 비즈니스용 Skype 온-프레미스의 사용자 계정이 며 엔터프라이즈 음성이 포함 된 비즈니스용 Skype 클라이언트 사용
- **시나리오 2:** 비즈니스용 Skype online의 사용자 계정-하이브리드 음성 연결이 있는 비즈니스용 Skype 클라이언트 사용
- **시나리오 3:** Microsoft 팀 라이선스를 사용 하 여 비즈니스용 Skype online의 사용자 계정이 팀 클라이언트를 사용할 수 있습니다.
 
### <a name="supportability-matrix"></a>지원 가능성 행렬


|**에서 만든 사용자 개체**  |**사용자의 비즈니스용 Skype 서비스 공급자**|**사용자의 클라이언트**|**음성 옵션**|**지원**|
| ------------ | --------- | --------- | --------- | -------- |
|온-프레미스 광고| 온-프레미스 |비즈니스용 Skype   | Enterprise Voice   |'|
|온-프레미스 광고|온라인| 비즈니스용 Skype  | 하이브리드 음성 연결   |' |
|온-프레미스 광고|온라인 |Microsoft 팀 |직접 라우팅  |' |
|**지원 되지 않는 조합**    | |         |         |      |
|Azure AD| 온-프레미스/온라인 | 비즈니스용 Skype/Microsoft 팀|엔터프라이즈 음성/하이브리드 음성 연결/직접 라우팅  |아니요, 먼저 온-프레미스 광고에 사용자 개체를 만들어야 합니다. |
|온-프레미스 광고  |온-프레미스| Microsoft 팀| 엔터프라이즈 음성/하이브리드 음성 연결/직접 라우팅   |아니요, Microsoft 팀 클라이언트는 온-프레미스 비즈니스용 Skype에서 지원 되지 않습니다. |     
|온-프레미스 광고  |온라인 |비즈니스용 Skype  | 직접 라우팅  |아니요, 다이렉트 라우팅이 비즈니스용 skype 클라이언트에서 지원 되지 않으며, 비즈니스용 Skype에서 Enterprise Voice에 대 한 사용자를 먼저 사용 하도록 설정 해야 합니다.  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN이 있는 하이브리드 환경에 대 한 지원 가능성 문

모든 사용자는 온-프레미스 광고에서 사용자 개체를 만들고 Azure AD Connect 도구를 사용 하 여 Azure AD와 동기화 **해야 합니다** . 사용자 개체가 하이브리드 구성의 Azure AD에서 직접 만들어진 경우 팀에서 비즈니스용 Skype를 사용 하도록 설정 하는 **것은 지원 되지 않습니다** . 팀에 게 직접 사용할 수 있는 신규 고용 같은 새 사용자의 경우, 사용자는 온-프레미스 비즈니스용 skype 관리 도구를 사용 하 여 비즈니스용 Skype를 사용 하도록 설정 해야 합니다. Enterprise Voice를 사용 하 여 온-프레미스 풀을 사용 하지 않고 비즈니스용 Skype 또는 팀에서 사용자를 만드는 **것은 지원 되지 않습니다**. 이에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 계획 전화 시스템](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)을 참조 하세요.
