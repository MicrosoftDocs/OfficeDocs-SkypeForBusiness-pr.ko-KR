---
title: 직접 라우팅 세션 테두리 컨트롤러 연결을 테스트하는 PowerShell 스크립트
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트 샘플을 사용하여 직접 라우팅 세션 테두리 컨트롤러 연결을 Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: acba1d06debc9a0e06ee6636e14ee5cbf15bd90f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774408"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>직접 라우팅 세션 테두리 컨트롤러 연결을 테스트하는 PowerShell 스크립트

SIP Tester 클라이언트는 SBC(직접 라우팅 세션 테두리 컨트롤러) 연결을 테스트하는 데 사용할 수 있는 샘플 PowerShell 스크립트 Microsoft Teams. 이 스크립트는 직접 라우팅을 사용하여 고객 쌍 세션 시작 프로토콜(SIP) 트렁크의 기본 기능을 테스트합니다.

스크립트는 테스트 러너에 SIP 테스트를 제출하고 결과를 기다렸다가 읽을 수 있는 형식으로 표시됩니다. 이 스크립트를 사용하여 다음 시나리오를 테스트할 수 있습니다.

- 아웃바운드 및 인바운드 호출
- 동시 링
- 미디어 에스컬레이터
- 협의적 전송

## <a name="download-the-script-and-documentation"></a>스크립트 및 설명서 다운로드

[SIP Tester 클라이언트 스크립트 및 설명서를 다운로드합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > SIP Tester 클라이언트 스크립트는 adal.ps 버전 3.19.8.1만 지원합니다. 나중에 버전이 사용되는 경우 오류가 adal.ps 반환됩니다.
  
  
