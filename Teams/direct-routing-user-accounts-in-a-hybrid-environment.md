---
title: PSTN을 사용하는 하이브리드 환경의 사용자 계정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 사용자 만들기의 다양한 조합과 지원되거나 지원되지 않는 조합에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676420"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 연결이 포함된 하이브리드 환경의 사용자 계정

## <a name="about-the-environment"></a>환경 정보

이 문서는 다음을 모두 포함하는 환경에 적용됩니다.

- 비즈니스용 Skype 서버 또는 Lync Server 2013
- Microsoft 365 또는 Office 365 조직
- 비즈니스용 Skype 서버 비즈니스용 Skype Online 또는 Microsoft Teams 테넌트 간에 구성된 하이브리드 연결
- 클라이언트와 주고 받는 PSTN(공중 전화망) 통화를 만들고 받을 수 있는 사용자


다른 환경(예: 비즈니스용 Skype 클라우드 커넥터 버전)이 있거나, 하이브리드가 구성되지 않았거나, 사용자가 PSTN 호출에 대해 사용하도록 설정되지 않은 경우 지원 가능성 매트릭스가 달라집니다.

## <a name="about-the-combinations-and-the-supportability-statement"></a>조합 및 지원 가능성 설명 정보

PSTN 연결이 있는 비즈니스용 Skype 하이브리드 환경은 사용자 서비스가 제공되는 위치와 사용자 계정을 프로비전 및 관리하는 방법에 대한 유연성을 제공합니다. 그러나 다양한 옵션이 지원되지 않는 조합을 만들 수 있습니다. 이 섹션에서는 사용자 만들기의 다양한 조합과 지원 가능성 설명에 대해 설명합니다.

**정의:**

- **Enterprise Voice:** 온-프레미스 비즈니스용 Skype 사용자 계정을 사용하는 사용자에게 PSTN에 대한 액세스를 제공하는 옵션입니다. 온-프레미스 비즈니스용 Skype 중재 서버는 PSTN에 대한 상호 연결을 제공합니다.
- **하이브리드 음성 연결:** 비즈니스용 Skype Online 계정을 사용하여 사용자에게 PSTN에 대한 액세스를 제공하는 옵션입니다. 온-프레미스 비즈니스용 Skype 중재 서버는 PSTN에 대한 상호 연결을 제공합니다.
- **직접 라우팅:** Microsoft Teams 클라이언트를 사용하여 온라인 비즈니스용 Skype 계정, Microsoft Teams 라이선스가 있는 사용자에게 PSTN에 대한 액세스를 제공하는 옵션입니다. SBC는 Microsoft의 온-프레미스 소프트웨어 없이 Microsoft 365 또는 Office 365 SIP 프록시에 연결됩니다.

**환경은 다음 조합을 지원합니다.**

- **시나리오 1:** 비즈니스용 Skype 온-프레미스의 사용자 계정이며 Enterprise Voice 비즈니스용 Skype 클라이언트를 사용합니다.
- **시나리오 2:** 온라인 비즈니스용 Skype 사용자 계정으로 하이브리드 음성 연결이 있는 비즈니스용 Skype 클라이언트를 사용합니다.
- **시나리오 3:** Microsoft Teams 라이선스를 사용하여 온라인 비즈니스용 Skype 사용자 계정으로 Teams 클라이언트를 사용합니다.

### <a name="supportability-matrix"></a>지원 가능성 매트릭스

|에서 만든 사용자 개체|사용자의 비즈니스용 Skype 서비스 공급자|사용자의 클라이언트|음성 옵션|지원|
|---|---|---|---|---|
|온-프레미스 AD|온-프레미스|비즈니스용 Skype|Enterprise Voice|예|
|온-프레미스 AD|온라인|비즈니스용 Skype|하이브리드 음성 연결|예|
|온-프레미스 AD|온라인|Microsoft Teams|직접 라우팅|예|
|**지원되지 않는 조합**|||||
|Azure AD|온-프레미스/온라인|비즈니스용 Skype/Microsoft Teams|Enterprise Voice/하이브리드 음성 연결/직접 라우팅|아니요. 먼저 온-프레미스 AD에서 사용자 개체를 만들어야 합니다.|
|온-프레미스 AD|온-프레미스|Microsoft Teams|Enterprise Voice/하이브리드 음성 연결/직접 라우팅|아니요, Microsoft Teams 클라이언트는 온-프레미스 비즈니스용 Skype 지원되지 않습니다.|
|온-프레미스 AD|온라인|비즈니스용 Skype|직접 라우팅|아니요, 직접 라우팅은 비즈니스용 Skype 클라이언트에서 지원되지 않습니다.|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN을 사용하는 하이브리드 환경에 대한 지원 가능성 설명

모든 사용자의 경우 사용자 개체를 온-프레미스 AD에서 만들고 Azure AD 커넥트 도구를 사용하여 Azure AD 동기화 **해야 합니다**. 하이브리드 구성의 Azure AD 사용자 개체를 직접 만든 경우 Teams/비즈니스용 Skype 대한 사용자 사용은 **지원되지 않습니다**. Teams 직접 사용하도록 설정되는 신입 사원과 같은 신규 사용자의 경우 사용자는 온-프레미스 비즈니스용 Skype 관리 도구를 사용하여 비즈니스용 Skype 사용하도록 설정해야 합니다. Enterprise Voice 사용하여 온-프레미스 풀에서 먼저 사용하도록 설정하지 않고 온라인 비즈니스용 Skype 또는 Teams 사용자를 만드는 **것은 지원되지 않습니다**. 이에 대한 자세한 내용은 [비즈니스용 Skype 서버 온-프레미스 PSTN 연결을 사용하여 계획 전화 시스템](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity) 살펴보세요.
