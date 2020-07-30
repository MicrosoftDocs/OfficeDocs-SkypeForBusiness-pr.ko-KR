---
title: Microsoft 팀에서 NDI 사용
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft 팀에서 NDI를 사용 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522918"
---
# <a name="use-ndi-in-microsoft-teams"></a>Microsoft 팀에서 NDI 사용

[!INCLUDE [template](includes/preview-feature.md)]

NDI (네트워크 디바이스 인터페이스)는 미디어 장치 (예: 스튜디오 카메라 및 믹서)를 연결 하는 데 사용할 수 있는 최신 솔루션입니다. NDI는 실제 연결을 사용 하는 대신 로컬 컴퓨터를 포함 하 여 로컬 인트라넷을 통해 연결할 수 있도록 합니다.

NewTek NDI®는 스트림에 대 한 라이브 콘텐츠를 생성 하는 표준 업계 솔루션이 되며, 전문 방송 환경에서 상당한 인식과 채택을 얻었습니다.

Skype는 이전에 2018 Skype에 NDI Out 기능을 추가 했습니다. Microsoft 팀은이 기능을 활용 하 여 모임 환경을 개선 합니다.

NDI는 로컬 네트워크로 제한 되며 브로드캐스트 솔루션이 아닌 프로덕션 워크플로의 일부로 간주 해야 합니다.

## <a name="turn-on-ndi"></a>NDI 켜기

NDI를 사용 하려면 사용자에 대해 두 단계가 설정 되어 있어야 합니다.

1. 테 넌 트 관리자는 기능 플래그 enableStreamingCallsOverNdi을 사용 하도록 설정 해야 합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 이 변경이 채워지면 최종 사용자가 **설정**  >  **사용 권한**으로부터 해당 클라이언트에 대해 ndi를 설정 해야 합니다.

사용자가 모임에 참가할 때 모임이 브로드캐스트 되 고 있음을 알리는 메시지가 표시 됩니다. 사용자가 브로드캐스트에 포함 하지 않으려는 경우 모임에서 삭제 해야 합니다.

다음 이미지는 팀 모임에서 사용자에 게 표시 되는 배너 메시지를 보여줍니다.

![팀 모임에 표시 되는 NDI 배너의 이미지입니다.](media/NDI-disclosure.png)

이 배너에는 [Microsoft 개인정보 보호 정책](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi)에 대 한 링크가 있습니다.

## <a name="supported-locales-and-user-types"></a>지원 되는 로캘 및 사용자 유형

NDI는 모든 로캘에서 지원 됩니다. NDI 모임에서 지원 되는 사용자는 다음과 같습니다.

- 테 넌 트-링/tenantId/userId를 기준으로 제공 되는 완전 한 지원 (모임 정책 + 기능 플래그에 의해 제어 됨)
- 페더레이션 – 아니요 (NDI를 사용 하는 경우에도)<sup>1</sup>
- Freemium-no (기본값)
- 익명 – 아니요 (기본값)
- 게스트 – no (기본값)

장치 <sup>1</sup> 개에는 기본적으로 설정 되어 있는 ndi 설정이 있습니다. 모임 참가자가 NDI h l l m이 해제 된 장치를 사용 하는 경우 NDI를 설정 해야 합니다.
