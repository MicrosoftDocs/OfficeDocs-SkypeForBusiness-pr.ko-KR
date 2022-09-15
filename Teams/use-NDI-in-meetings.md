---
title: 모임 콘텐츠 브로드캐스트
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: NDI 및 SDI를 사용하여 Microsoft Teams에서 모임 콘텐츠를 브로드캐스트하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc185a22c7ea4d849008989da29f50a8f98ebb9d
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706815"
---
# <a name="broadcast-meeting-content"></a>모임 콘텐츠 브로드캐스트 



Teams는 Teams 모임 콘텐츠를 브로드캐스트하는 두 가지 옵션인 NewTek NDI®(네트워크 디바이스 인터페이스) 및 SDI(직렬 디지털 인터페이스)를 제공합니다.

- NewTek NDI® 기술은 미디어 디바이스(예: 스튜디오 카메라 및 믹서)를 연결하기 위한 최신 솔루션입니다. NDI® 기술은 물리적 연결을 사용하는 대신 로컬 컴퓨터를 포함하여 로컬 인트라넷을 통해 연결할 수 있도록 합니다.

  NDI® 기술은 스트림을 위한 라이브 콘텐츠를 제작하기 위한 표준 산업 솔루션이 되었으며 전문 방송 세계에서 상당한 인식과 채택을 얻고 있습니다.

- SDI는 1989년부터 브로드캐스트 프로덕션에 사용되어 왔으며 대부분의 레거시 스튜디오 하드웨어 디바이스에서 지원됩니다. AJA Video Systems 및 Blackmagic Design의 하드웨어 디바이스는 SDI를 사용하는 레거시 브로드캐스트 디바이스에 대한 연결을 제공합니다.

> [!NOTE]
> SDI를 지원하는 Video Hardware Out 기능은 현재 미리 보기 릴리스에 있습니다.

NDI® 및 SDI 기술은 모든 로캘에서 지원됩니다.

NDI 및 SDI 사용에 대한 액세스는 기능을 활성화하려는 사용자의 모임 정책에 따라 결정됩니다. 가장 안전한 솔루션의 경우 로컬 스트리밍 매개 변수를 전역 설정으로 설정하지 마세요.


## <a name="enable-broadcast-features"></a>브로드캐스트 기능 사용

사용자에 대해 NDI® 및 SDI 브로드캐스트 기능을 사용하도록 설정하려면 다음을 수행합니다.

1. 테넌트 관리자는 최종 사용자가 모임 정책에 대해 로컬 스트리밍을 사용하도록 설정해야 합니다. 

2. 최종 사용자는 특정 클라이언트에 대해 로컬 스트리밍을 켜야 합니다.


최종 사용자를 사용하도록 설정하려면 다음과 같이 Teams 관리 센터 또는 Teams PowerShell을 사용할 수 있습니다.

Teams 관리 센터에서 **오디오 & 비디오를 > 모임 정책** 으로 이동하고 **로컬 브로드캐스팅을** 선택합니다.

PowerShell을 사용하려면 다음과 같이 Set-CsTeamsMeetingPolicy cmdlet을 사용합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

이 변경 내용이 채워지면 최종 사용자는 **설정** > **사용 권한** 에서 특정 클라이언트에 대한 로컬 스트리밍을 켜야 합니다. 자세한 내용은 [Teams에서 오디오 및 비디오 브로드캐스팅을 참조하세요](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





