---
title: Microsoft Teams에서 NDI 사용
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams에서 NDI를 사용하는 방법을 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337017"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Microsoft Teams에서 NDI® 기술 사용

 NewTek NDI®(네트워크 디바이스 인터페이스) 기술은 미디어 디바이스(예: 스튜디오 카메라 및 믹서)를 연결하기 위한 최신 솔루션입니다. NDI® 기술을 사용하면 물리적 연결을 사용하는 대신 로컬 머신을 포함하여 로컬 인트라넷을 통해 연결을 사용할 수 있습니다.

NDI® 기술은 스트림용 라이브 콘텐츠를 생성하기 위한 표준 산업 솔루션이 됐고 전문 브로드캐스트 세계에서 상당한 인지도와 채택을 얻게 됩니다.

Skype는 이전에 2018년 후반에 NDI® 기능을 Skype에 추가했습니다. Microsoft Teams는 이 기능을 사용하여 모임 환경을 개선합니다.

NDI® 기술은 로컬 네트워크로 제한되어 있으며 브로드캐스트 솔루션이 아닌 프로덕션 워크플로의 일부로만 간주해야 합니다.

## <a name="turn-on-ndi-technology"></a>NDI 및 ® 켜기

NDI® 기술을 사용하려면 사용자에 대해 두 단계를 켜야 합니다.

1. 테넌트 관리자는 CsTeamsMeetingPolicy에서 'AllowNDIStreaming' 속성을 사용하도록 설정해야 합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 이 변경이 채워진 후 최종 사용자는 설정 권한에서 특정 클라이언트에 대한 NDI® 기술을  >  **켜야 합니다.**

사용자가 모임에 참가하면 모임이 브로드캐스트 중입니다. 사용자가 브로드캐스트에 포함하지 못하게 하려는 경우 모임에서 삭제해야 합니다.

다음 이미지는 사용자가 Teams 모임에서 볼 수 있는 배너 메시지를 보여줍니다.

![Teams ® 표시하는 기술 배너입니다.](media/NDI-disclosure.png)

배너에는 Microsoft 개인 정보 취급 방침에 [대한 링크가 있습니다.](https://aka.ms/teamsprivacy)

## <a name="supported-locales-and-user-types"></a>지원되는 지역 및 사용자 유형

NDI® 기술은 모든 로케일에서 지원됩니다. 다음 사용자는 NDI® 기술 스트림에 포함되지만 일부 사용자가 NDI 및 기술 스트림에 액세스할 ® 없습니다.

- 테넌트 내 – 링/tenantId/userId(모임 정책에 의해 제어)에 따라 제공된 전체 지원
- 페더링 – 스트림 액세스 없음(NDI® 기술이 있는<sup>경우에도) 1</sup>
- 프리미엄 - 스트림 액세스 없음
- 익명 – 스트림 액세스 없음
- 게스트 - 스트림 액세스 없음  

<sup>1개</sup> 디바이스에는 기본적으로 ® NDI 및 기술 설정이 있습니다. 모임 참가자가 NDI® 디바이스를 사용하는 경우 NDI 및 ® 켜야 합니다.
