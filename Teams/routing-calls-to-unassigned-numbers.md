---
title: 할당되지 않은 번호로 호출 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 조직에서 할당되지 않은 번호로 통화를 라우팅하는 방법을 알아봅니다.
ms.openlocfilehash: 3f3d0b9e6962cce7abdb91efa8539dd559c38956
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272303"
---
# <a name="routing-calls-to-unassigned-numbers"></a>할당되지 않은 번호로 호출 라우팅

관리자는 조직의 할당되지 않은 번호로 통화를 라우팅할 수 있습니다. 예를 들어 다음과 같이 할당되지 않은 숫자로 호출을 라우팅할 수 있습니다. 

- 할당되지 않은 지정된 번호로 모든 호출을 사용자 지정 공지 사항으로 라우팅합니다.

- 할당되지 않은 지정된 번호로 모든 호출을 주 스위치보드로 라우팅합니다.

할당되지 않은 번호로 통화를 사용자, 자동 전화 교환 또는 통화 큐와 연결된 리소스 계정 또는 호출자에게 사용자 지정 오디오 파일을 재생하는 알림 서비스로 라우팅할 수 있습니다.

## <a name="configuration"></a>구성

할당되지 않은 번호로 호출을 라우팅하려면 Teams PowerShell 모듈 2.5.1 이상에서 사용할 수 있는 New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment cmdlet을 사용합니다.

호출된 번호 또는 숫자 범위와 이러한 번호에 대한 호출에 대한 연결된 라우팅을 지정해야 합니다. 예를 들어 다음 명령은 숫자 +1(555) 222-3333에 대한 모든 호출이 aa@contoso.com 리소스 계정으로 라우팅되도록 지정합니다.

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

다음 예제에서는 숫자 범위 +1 (555) 333-0000 ~ +1 (555) 333-9999에 대한 모든 호출이 알림 서비스로 라우팅되도록 지정합니다. 그러면 오디오 파일 MainAnnouncement.wav가 호출자에게 재생됩니다.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>참고

- 알림으로 라우팅하는 경우 오디오 파일이 호출자에게 한 번 재생됩니다.

- 할당되지 않은 Microsoft 통화 플랜 구독자 번호로 통화를 라우팅하려면 테넌트에 사용 가능한 [통신 크레딧](what-are-communications-credits.md)이 있어야 합니다.

- 할당되지 않은 Microsoft 통화 플랜 서비스 번호로 통화를 라우팅하려면 테넌트에 하나 이상의 **Microsoft Teams 전화 리소스 계정** 라이선스가 있어야 합니다.

- 지원되는 사용자 지정 오디오 파일 형식은 WAV(압축되지 않은, 모노 또는 스테레오의 깊이가 8/16/32비트인 선형 PCM), WMA(모노 전용) 및 MP3입니다. 오디오 파일 콘텐츠는 5MB를 초과할 수 없습니다.

- Microsoft Teams에 대한 인바운드 통화와 Microsoft Teams의 아웃바운드 통화는 할당되지 않은 번호 범위에 대해 호출된 번호를 확인합니다.

- 지정된 패턴/범위에 테넌트에서 사용자 또는 리소스 계정에 할당된 전화 번호가 포함된 경우 이러한 전화 번호에 대한 호출은 적절한 대상으로 라우팅되고 지정된 할당되지 않은 번호 처리로 라우팅되지 않습니다. 범위에 있는 숫자에 대한 다른 검사는 없습니다. 범위에 유효한 외부 전화 번호가 포함된 경우 Microsoft Teams에서 해당 전화 번호로의 아웃바운드 통화는 처리에 따라 라우팅됩니다.

## <a name="related-topics"></a>관련 항목

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
