---
title: 부적당 번호에 대한 라우팅 호출
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 조직의 부적당 번호로 호출을 라우팅하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 2574a0ac734ed6caee1eadf5a5ee006111713055
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536999"
---
# <a name="routing-calls-to-unassigned-numbers"></a>부적당 번호에 대한 라우팅 호출

> [!NOTE]
> 이 기능은 공개 미리 보기 릴리스로 사용할 수 있습니다.

관리자는 조직의 부적당 번호로 호출을 라우팅할 수 있습니다. 예를 들어 다음과 같이 부호가 없는 숫자로 호출을 라우팅할 수 있습니다. 

- 지정되지 않은 번호로 모든 호출을 사용자 지정 공지에 라우팅합니다.

- 모든 호출을 주 스위치보드에 배정되지 않은 번호로 라우팅합니다.

호출을 사용자에 라우팅할 수 있습니다. 사용자 지정 오디오 파일을 호출자에 대한 사용자 지정 오디오 파일을 재생하는 자동 전화 교환 또는 통화 큐와 연결된 리소스 계정으로 라우팅할 수 있습니다.

## <a name="configuration"></a>구성

부적격 번호로 호출을 라우팅하려면 PowerShell 모듈 2.5.1 이상에서 사용할 수 있는 New/Get/Set/Remove-CsTeamsUnasignedNumberTreatment cmdlet을 Teams 사용합니다.

호출된 숫자 또는 숫자 범위 및 이러한 숫자에 대한 호출에 대한 연결된 라우팅을 지정해야 합니다. 예를 들어 다음 명령은 숫자 +1(555) 222-3333에 대한 모든 호출이 리소스 계정으로 라우팅됩니다 aa@contoso.com.

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

다음 예제에서는 번호 범위 +1(555) 333-0000에서 +1 (555) 333-9999에 대한 모든 호출이 공지 서비스로 라우팅됩니다.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>참고

- 공지에 라우팅하면 오디오 파일이 호출자에 한 번 재생됩니다.

- 배포되지 않은 Microsoft Calling Plan 구독자 번호로 호출을 라우팅하기 위해 테넌트에 사용 가능한 [Communications 크레딧이 필요합니다.](what-are-communications-credits.md)

- 배포되지 않은 Microsoft Calling Plan 서비스 번호로 호출을 라우팅하기 위해 테넌트에 가상 사용자 라이선스인 전화 시스템 하나 이상이 필요합니다.

## <a name="related-topics"></a>관련 항목

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)