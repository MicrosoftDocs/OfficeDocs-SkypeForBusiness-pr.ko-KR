---
title: 하이브리드 배포에서 오디오 회의 공급자에 대 한 페더레이션 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: '요약: 비즈니스용 Skype Online에서 오디오 회의 공급자에 대 한 페더레이션을 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185463"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>하이브리드 배포에서 오디오 회의 공급자에 대 한 페더레이션 구성

**요약:** 비즈니스용 Skype Online에서 오디오 회의 공급자의 페더레이션을 구성 하는 방법에 대해 알아봅니다.

하이브리드 배포에서 ACP (오디오 회의 공급자)를 사용 하려는 경우 (온-프레미스 온라인)에는 온-프레미스 배포와 ACP 파트너 간의 페더레이션을 허용 된 파트너 서버로 구성 해야 합니다. 이 경우에는 온-프레미스 배포의 페더레이션 도메인 목록에 ACP 파트너 도메인 및 Edge 서버 (액세스 프록시 라고도 함)를 추가 하 여 페더레이션을 구성할 수 있습니다. 그런 다음 ACP 파트너는 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다. 자세한 내용은 ACP 공급자에 게 문의 하세요. 그런 다음 ACP 파트너는 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다.

- **ACP 도메인 및 Edge 서버를 허용 되는 페더레이션 도메인으로 추가**

    ACP 도메인을 허용 된 파트너 서버 (허용 페더레이션 도메인)로 추가 하려면 [허용 되는 외부 도메인에 대 한 지원 구성](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)의 단계를 따르세요. Edge 서버의 경우 ACP 파트너의 Edge 서버의 FQDN을 추가 합니다. 해당 Edge 서버에 대 한 FQDN을 얻으려면 ACP 파트너에 게 문의 하 여 액세스 프록시로도 해당 사용자가 참조할 수 있도록 해야 할 수 있습니다.

- **ACP 파트너에 대 한 Edge 서버 풀의 FQDN 제공**

    ACP 파트너는 허용 되는 페더레이션 도메인으로 사용자의 Edge 서버 풀의 FQDN을 추가 하 여 온-프레미스 도메인을 허용 된 파트너 서버로 추가 하도록 페더레이션을 구성 해야 합니다.


