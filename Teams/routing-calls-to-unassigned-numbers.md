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
description: 조직의 할당되지 않은 번호로 통화를 라우팅하는 방법을 알아봅니다.
ms.openlocfilehash: 810c6b1547586d5494dbba3d0ddbdfc8d5d3c5e1
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795520"
---
# <a name="routing-calls-to-unassigned-numbers"></a>할당되지 않은 번호로 호출 라우팅

관리자는 조직의 할당되지 않은 번호로 통화를 라우팅할 수 있습니다. 예를 들어 다음과 같이 호출을 할당되지 않은 숫자로 라우팅할 수 있습니다. 

- 할당되지 않은 지정된 번호로 모든 호출을 사용자 지정 공지 사항으로 라우팅합니다.

- 할당되지 않은 지정된 번호로 모든 호출을 주 스위치보드로 라우팅합니다.

할당되지 않은 번호로 통화를 사용자, 자동 전화 교환 또는 통화 큐와 연결된 리소스 계정 또는 호출자에게 사용자 지정 오디오 파일을 재생하는 알림 서비스로 라우팅할 수 있습니다.

Teams 관리 센터를 사용하거나 PowerShell을 사용하여 할당되지 않은 숫자의 라우팅을 구성할 수 있습니다.

## <a name="use-teams-admin-center"></a>Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동합니다.

2. **라우팅 규칙** 탭에서 **추가** 를 클릭합니다.

3. 규칙에 이름, 설명을 지정하고 규칙에 대한 평가 순서를 지정합니다.

4. 추가할 규칙 종류를 결정합니다. 전화 번호 패턴 유형이 미리 구성된 규칙을 선택하고 패턴 및 라우팅 옵션을 완료할 수 있습니다. 전화 번호 패턴 및 라우팅 옵션에 대한 정규식을 직접 입력하는 고급 설정을 선택할 수도 있습니다.

5. **저장** 을 선택합니다.

할당되지 않은 전화 번호에 대한 라우팅 규칙을 직접 만들 수도 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동합니다.

2. **숫자** 탭에서 할당되지 않은 전화 번호를 선택하고 보기 맨 위에 있는 **경로를** 클릭합니다.

4. 규칙에 이름, 설명을 지정하고 규칙에 대한 평가 순서를 지정합니다.

4. 라우팅 옵션을 선택합니다.

5. **저장** 을 선택합니다.

테스트 번호 기능을 사용하여 라우팅 규칙을 테스트할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동합니다.

2. **라우팅 규칙** 탭에서 **테스트 번호를** 클릭합니다.

3. 전화 번호를 직접 입력하거나 **숫자 선택을** 클릭하고 드롭다운에서 할당되지 않은 전화 번호 중 하나를 선택합니다.

4. **테스트를** 선택합니다.


## <a name="use-powershell"></a>PowerShell 사용

할당되지 않은 번호로 호출을 라우팅하려면 Teams PowerShell 모듈 2.5.1 이상에서 사용할 수 있는 New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment cmdlet을 사용합니다.

호출된 숫자 또는 숫자 범위와 이러한 번호에 대한 호출에 대한 연결된 라우팅을 지정해야 합니다. 예를 들어 다음 명령은 숫자 +1(555) 222-3333에 대한 모든 호출이 리소스 계정 aa@contoso.com 라우팅되도록 지정합니다.

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

다음 예제에서는 숫자 범위 +1(555) 333-0000 ~+1(555) 333-9999에 대한 모든 호출이 알림 서비스로 라우팅되도록 지정합니다. 그러면 오디오 파일 MainAnnouncement.wav가 호출자에게 재생됩니다.

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>참고

- 알림으로 라우팅하는 경우 오디오 파일이 호출자에게 한 번 재생됩니다.

- 할당되지 않은 Microsoft 통화 플랜 구독자 번호로 통화를 라우팅하려면 테넌트에게 사용 가능한 [통신 크레딧이](what-are-communications-credits.md) 있어야 합니다.

- 할당되지 않은 Microsoft 통화 플랜 서비스 번호로 통화를 라우팅하려면 테넌트에게 하나 이상의 **Microsoft Teams 전화 리소스 계정** 라이선스가 있어야 합니다.

- 지원되는 사용자 지정 오디오 파일 형식은 WAV(압축되지 않은, 모노 또는 스테레오의 깊이가 8/16/32비트인 선형 PCM), WMA(모노 전용) 및 MP3입니다. 오디오 파일 콘텐츠는 5MB를 초과할 수 없습니다.

> [!NOTE]
> Microsoft Teams 서비스에서 음악 또는 오디오 파일을 사용하는 데 필요한 모든 권한과 권한을 독립적으로 지우고 보호해야 합니다. 여기에는 모든 관련 권리 보유자의 오디오 파일에서 음악, 음향 효과, 오디오, 브랜드, 이름 및 기타 콘텐츠에 대한 지적 재산권 및 기타 권리가 포함될 수 있습니다. 보유자는 예술가, 배우, 공연자, 음악가, 작곡가, 음반 레이블, 음악 출판사, 노조, 길드, 권리 사회, 집단 관리 조직 및 음악 저작권, 음향 효과, 오디오 및 기타 지적 재산권을 소유, 제어 또는 허가하는 기타 당사자를 포함할 수 있습니다.

- Microsoft Teams에 대한 인바운드 호출과 Microsoft Teams의 아웃바운드 통화는 할당되지 않은 번호 범위에 대해 호출된 번호를 확인합니다.

- 지정된 패턴/범위에 테넌트에서 사용자 또는 리소스 계정에 할당된 전화 번호가 포함된 경우 이러한 전화 번호에 대한 호출은 적절한 대상으로 라우팅되고 할당되지 않은 지정된 번호 처리로 라우팅되지 않습니다. 범위에 있는 숫자의 다른 검사는 없습니다. 범위에 유효한 외부 전화 번호가 포함된 경우 Microsoft Teams에서 해당 전화 번호로의 아웃바운드 통화는 처리에 따라 라우팅됩니다.


## <a name="related-topics"></a>관련 주제

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
