---
title: 직접 라우팅 세션 경계 컨트롤러 연결을 테스트 하기 위한 PowerShell 스크립트
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트 샘플을 사용 하 여 Microsoft 팀의 직접 라우팅 세션 경계 컨트롤러 연결을 테스트 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0eca4b7c7c4708509eb33bc14e4514dc3f858980
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837958"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>직접 라우팅 세션 경계 컨트롤러 연결을 테스트 하기 위한 PowerShell 스크립트

SIP 테스터 클라이언트는 Microsoft 팀에서 직접 SBC (라우팅 세션 경계 컨트롤러) 연결을 테스트 하는 데 사용할 수 있는 샘플 PowerShell 스크립트입니다. 이 스크립트는 다이렉트 라우팅이 있는 고객 쌍의 SIP (세션 초기화 프로토콜) 트렁크의 기본 기능을 테스트 합니다.

이 스크립트는 SIP 테스트를 test runner에 제출 하 고, 결과를 기다린 다음, 사람이 읽을 수 있는 형식으로 표시 합니다. 이 스크립트를 사용 하 여 다음과 같은 시나리오를 테스트할 수 있습니다.

- 아웃 바운드 및 인바운드 통화
- 동시 연결
- 미디어 확대
- Consultative 전송

## <a name="download-the-script-and-documentation"></a>스크립트 및 문서 다운로드

[SIP 테스터 클라이언트 스크립트 및 문서](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)를 다운로드 합니다.