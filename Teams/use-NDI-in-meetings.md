---
title: 모임 콘텐츠 브로드캐스트
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: NDI 및 SDI를 사용하여 모임 콘텐츠를 브로드캐스트하는 Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941883"
---
# <a name="broadcast-meeting-content"></a>모임 콘텐츠 브로드캐스트 



Teams 네트워크 디바이스 인터페이스(NewTek NDI®) 및 SDI(직렬 디지털 인터페이스) : Teams 모임 콘텐츠를 브로드캐스트하기 위한 두 가지 옵션을 제공합니다.

- NewTek NDI® 기술은 미디어 디바이스(예: 스튜디오 카메라 및 믹서)를 연결하는 최신 솔루션입니다. NDI® 기술은 물리적 연결을 사용하는 대신 로컬 머신을 포함하여 로컬 인트라넷을 통해 연결을 가능하게 합니다.

  NDI® 기술은 스트림에 대한 라이브 콘텐츠를 생산하기 위한 표준 산업 솔루션이 됐고 전문 방송 세계에서 상당한 인식과 채택을 얻고 있습니다.

- SDI는 1989년부터 브로드캐스트 프로덕션에 사용되었습니다. 대부분의 레거시 스튜디오 하드웨어 장치에서 지원됩니다. AJA Video Systems 및 Blackmagic Design의 하드웨어 디바이스는 SDI를 사용하는 레거시 브로드캐스트 디바이스에 대한 연결을 제공합니다.

> [!NOTE]
> 비디오 하드웨어 아웃 기능은 SDI가 현재 미리 보기 릴리스에서 지원됩니다.

NDI® 및 SDI 기술은 모든 로케일에서 지원됩니다.

NDI 및 SDI를 사용하는 액세스는 기능을 활성화하려는 사용자의 모임 정책에 따라 결정됩니다. 가장 안전한 솔루션의 경우 로컬 스트리밍 매개 변수를 전역 설정으로 설정하지 않습니다.


## <a name="enable-broadcast-features"></a>브로드캐스트 기능 사용

사용자의 NDI® 및 SDI 브로드캐스트 기능을 사용하도록 설정하려면:

1. 테넌트 관리자는 최종 사용자가 모임 정책에 대해 로컬 스트리밍을 사용하도록 설정해야 합니다. 

2. 최종 사용자는 특정 클라이언트에 대한 로컬 스트리밍을 켜야 합니다.


최종 사용자를 사용하도록 설정하려면 다음과 같이 Teams 관리 센터 또는 Teams 수 있습니다.

Teams 관리 센터에서 오디오 > 비디오 > 모임 정책으로 **&** **NDI 스트리밍** 허용을 선택합니다.

PowerShell을 사용 의 경우 다음과 Set-CsTeamsMeetingPolicy cmdlet을 사용 합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

이 변경이 채워진 후 최종 사용자는 권한 에서 특정 **클라이언트에 대한 로컬 스트리밍을 설정**  >  **합니다.** 자세한 내용은 에서 오디오 [및 비디오 브로드캐스트를 Teams.](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)





