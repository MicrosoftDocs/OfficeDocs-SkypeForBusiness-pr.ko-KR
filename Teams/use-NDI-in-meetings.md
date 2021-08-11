---
title: NDI를 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: NDI를 사용하는 방법을 Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eebbea6ce5d632d38e94465f05fd9f60a3300a4e060106e7ba2f6218433c5e8b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335818"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>NDI ® 기술을 사용하여 Microsoft Teams

 NewTek NDI®(Network Device Interface) 기술은 미디어 디바이스(예: 스튜디오 카메라 및 믹서)를 연결하는 최신 솔루션입니다. NDI® 기술은 물리적 연결을 사용하는 대신 로컬 머신을 포함하여 로컬 인트라넷을 통해 연결을 가능하게 합니다.

NDI® 기술은 스트림에 대한 라이브 콘텐츠를 생산하기 위한 표준 산업 솔루션이 됐고 전문 방송 세계에서 상당한 인식과 채택을 얻고 있습니다.

Skype NDI® 아웃 기능이 2018년 Skype 추가되었습니다. Microsoft Teams 기능을 사용하여 모임 환경을 개선합니다.

NDI® 기술은 로컬 네트워크로 제한되어 있으며, 브로드캐스트 솔루션이 아닌 프로덕션 워크플로의 일부로만 간주해야 합니다.

## <a name="turn-on-ndi-technology"></a>NDI ® 켜기

NDI® 기술은 사용자에게 두 단계를 설정해야 합니다.

1. 테넌트 관리자는 CsTeamsMeetingPolicy에서 'AllowNDIStreaming' 속성을 사용하도록 설정해야 합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 이 변경이 채워진 후 최종 사용자는 권한 에서 특정 클라이언트에 ® NDI® 기술을 **켜야**  >  **설정 합니다.**

사용자가 모임에 참가하면 모임이 브로드캐스트 중이라 는 메시지를 볼 수 있습니다. 사용자가 브로드캐스트에 포함되지 않는 경우 모임에서 삭제해야 합니다.

다음 이미지는 사용자가 모임에서 볼 수 있는 배너 Teams 보여줍니다.

![그는 ® 모임에 표시하는 기술 Teams 배너입니다.](media/NDI-disclosure.png)

배너에는 Microsoft 개인 정보 취급 [방침에 대한 링크가 있습니다.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® 세션당만 활성화됩니다. 다음 로그인에서 사용자는 NDI를 사용하려면 먼저 활성화해야 ®.

## <a name="supported-locales-and-user-types"></a>지원되는 지역 및 사용자 유형

NDI® 기술은 모든 로케일에서 지원됩니다. 다음 사용자는 NDI® 기술 스트림에 포함되지만 모든 사용자가 NDI® 기술 스트림에 액세스할 수 있는 것은 없습니다.

- 테넌트 내 – 링/tenantId/userId를 기반으로 배달되는 전체 지원(모임 정책에 의해 제어)
- 페더링 – 스트림 액세스 없음(NDI® 기술이 있는<sup>경우에도) 1</sup>
- Premium - 스트림 액세스 없음
- 익명 – 스트림 액세스 없음
- 게스트 – 스트림 액세스 없음  

<sup>1</sup> 디바이스에는 기본적으로 ® NDI 및 기술 설정이 있습니다. 모임 참가자가 NDI가 있는 디바이스를 ® 경우 NDI® 기술을 켜야 합니다.
