---
title: Teams용 브라우저 로그 및 추적
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams에서 생성한 브라우저 및 WebRTC 로그, 찾을 수 있는 위치, Microsoft 지원 사용하여 로그를 수집하는 방법 및 모니터링 및 문제 해결에 도움이 되는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005470"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Teams용 브라우저 로그 및 추적

일부 오류 범주의 경우 Microsoft 지원 브라우저 추적을 수집해야 할 수 있습니다. 이 정보는 오류가 발생할 때 Teams 클라이언트의 상태에 대한 중요한 세부 정보를 제공할 수 있습니다. 이 문서에서는 Teams용 브라우저 및 WebRTC 로그를 수집하는 방법을 설명합니다.

## <a name="browser-logs"></a>브라우저 로그

브라우저 추적을 시작하기 전에 Teams에 로그인했는지 확인합니다. 추적에 중요한 로그인 정보가 포함되지 않도록 추적을 시작하기 전에 이 작업을 수행하는 것이 중요합니다.

로그인한 후 브라우저에 적합한 다음 링크 중 하나를 선택하고 제공된 단계를 따릅니다. 

-   [Chrome & Edge(Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [가장자리](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [사파리](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [파이어 폭스](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 이 단계에서는 Azure Portal 대한 모든 참조를 Teams 클라이언트로 바꿉니다.
  
## <a name="webrtc-logs-in-browsers"></a>브라우저의 WebRTC 로그

WebRTC 로그는 오디오 및 비디오 통화에 대한 연결 세부 정보를 제공하여 Microsoft 지원 지원할 수 있습니다. Edge(Chromium) 또는 Chrome에서 WebRTC 로그에 액세스하려면 다음 단계를 수행합니다.
  
1. 새 탭을 열고 다음 URL 중 하나로 이동합니다.
    - Edge(Chromium):`edge://webrtc-internals/`
    - 크롬: `chrome://webrtc-internals/`
  
2. Teams 웹 애플리케이션을 열고 문제를 재현합니다.
  
3. 1단계에서 액세스한 탭으로 돌아가기 두 개 이상의 탭이 표시됩니다.
    - GetUserMedia 요청
    - `https://teams.microsoft.com/url`

4. Teams 애플리케이션의 이름이 있는 탭을 선택하고 페이지 콘텐츠를 저장합니다.

## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)

[Teams에서 모니터링 및 문제 해결을 위한 로그 파일 구성](/MicrosoftTeams/log-files)
