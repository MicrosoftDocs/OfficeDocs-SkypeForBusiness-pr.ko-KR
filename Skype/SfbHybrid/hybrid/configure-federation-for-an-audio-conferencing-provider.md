---
title: 하이브리드 배포에서 오디오 회의 공급자에 대한 페더링 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 비즈니스용 Skype 온라인에서 오디오 회의 공급자에 대한 페더링을 구성하는 비즈니스용 Skype 있습니다.'
ms.openlocfilehash: 25bd691186d5d37dc272b420e68bb71a7d181de1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597892"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>하이브리드 배포에서 오디오 회의 공급자에 대한 페더링 구성

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**요약:** 비즈니스용 Skype Online에서 오디오 회의 공급자에 대한 페더링을 구성하는 비즈니스용 Skype 대해 알아보도록 합니다.

하이브리드 배포에서 ACP(오디오 회의 공급자)를 사용하려는 경우(온라인과의 사내에서) 페더링을 구성하려면 사내 배포와 ACP 파트너 간의 페더링을 허용 파트너 서버로 구성해야 합니다. ACP 파트너 도메인 및 에지 서버(액세스 프록시라고도 부를 수 있습니다)를 On-프레미스 배포에 대한 페더전된 도메인 목록에 추가하여 페더더전을 구성할 수 있습니다. 그런 다음 ACP 파트너는 허용되는 페더티된 도메인 목록에 사내 에지 서버 풀의 FQDN을 추가해야 합니다. 추가 세부 정보는 ACP 공급자에 문의하십시오. 그런 다음 ACP 파트너는 허용되는 페더티된 도메인 목록에 사내 에지 서버 풀의 FQDN을 추가해야 합니다.

- **ACP 도메인 및 에지 서버를 허용된 페더러트 도메인으로 추가**

    ACP 도메인을 허용된 파트너 서버(허용된 페더화 도메인)로 추가하려면 [Configure Support for Allowed External Domains의 단계를 따릅니다.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains) 에지 서버의 경우 ACP 파트너의 에지 서버의 FQDN을 추가합니다. ACP 파트너에게 문의하여 에지 서버의 FQDN을 얻어야 할 수 있습니다. ACP를 액세스 프록시로도 지칭할 수 있습니다.

- **ACP 파트너에게 에지 서버 풀의 FQDN 제공**

    ACP 파트너는 에지 서버 풀의 FQDN을 허용된 페더티드 도메인으로 추가하여 허용 파트너 서버로 사내 도메인을 추가하도록 페더ATION을 구성해야 합니다.