---
title: 하이브리드 배포에서 오디오 회의 공급자를 위한 페더레이션 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 비즈니스용 Skype Online에서 오디오 회의 공급자를 위한 페더레이션을 구성 하는 방법을 알아봅니다.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726888"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>하이브리드 배포에서 오디오 회의 공급자를 위한 페더레이션 구성

**요약:** 비즈니스용 Skype Online에서 오디오 회의 공급자를 위한 페더레이션을 구성 하는 방법을 알아봅니다.

하이브리드 배포에서 ACP (오디오 회의 공급자)를 사용 하려는 경우 (온-프레미스 online) 온-프레미스 배포와 ACP 파트너 간의 페더레이션을 허용 된 파트너 서버로 구성 해야 합니다. 온-프레미스 배포의 페더레이션 도메인 목록에 ACP 파트너 도메인 및에 지 서버 (액세스 프록시 라고도 함)를 추가 하 여 페더레이션을 구성할 수 있습니다. 그러면 ACP 파트너가 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다. 자세한 내용은 ACP provider에 문의 하세요. 그러면 ACP 파트너가 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다.

- **ACP 도메인 및에 지 서버를 허용 되는 페더레이션 도메인으로 추가**

    ACP 도메인을 허용 되는 파트너 서버 (페더레이션 도메인)로 추가 하려면 [허용 되는 외부 도메인에 대 한 지원 구성](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)의 단계를 수행 합니다. 에 지 서버의 FQDN을 추가 합니다. 해당에 지 서버에 대 한 FQDN을 가져오려면 ACP 파트너에 게 문의 하 여 액세스 프록시로 서이를 참조 해야 할 수도 있습니다.

- **에 지 서버 풀의 FQDN을 ACP 파트너에 게 제공**

    ACP 파트너는 허용 되는 페더레이션 도메인으로에 지 서버 풀의 FQDN을 추가 하 여 온-프레미스 도메인이 허용 되는 파트너 서버로 추가 되도록 페더레이션을 구성 해야 합니다.


