---
title: 중요한 Teams 모임에 워터마크 필요
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 중요한 Teams 모임에서 참석자 비디오 및 공유 콘텐츠에 워터마크를 사용하거나 요구하는 방법을 알아봅니다.
ms.openlocfilehash: 6037bc6e9dbe79d9ecee10666f4c34e4e778216a
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950505"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>중요한 Teams 모임에 워터마크 필요

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

화면에 공유된 콘텐츠와 참석자 비디오 모두에 대해 Teams 모임에 워터마크를 표시하도록 설정할 수 있습니다. 워터마크에는 모임 참가자의 이메일 주소가 표시됩니다. 모임 참가자는 워터마크를 끌 수 없습니다.

워터마크는 Teams 데스크톱 및 모바일에서 지원됩니다. 지원되지 않는 플랫폼에서 모임에 참가하는 사람 오디오 전용 환경을 갖습니다.

[CVI(Cloud Video Interop)](cloud-video-interop.md)에서 참가하는 참가자는 워터마크 없이 콘텐츠를 볼 수 있습니다.

다음 참가자는 워터마크를 사용할 때 오디오 전용 환경을 제공합니다.

- Teams 웹 클라이언트를 사용하는 참가자
- VDI(Virtual Desktop Infrastructure) 참가자
- 익명 참가자
- 오버플로 참가자
- Windows에서 Microsoft Teams 룸 Surface Hub의 Microsoft Teams 룸
- Android에서 Microsoft Teams 룸
- 이전 Teams 클라이언트
- [Microsoft Teams 룸 디바이스에서 직접 게스트 조인](/microsoftteams/rooms/third-party-join)

> [!Note]
> 민감도 레이블, 사용자 지정 모임 템플릿 및 워터마크의 모임 설정에는 Teams Premium 필요합니다.

모임 워터마크는 Teams 관리 센터에서 사용할 수 있습니다. 그런 다음 모임 이끌이가 추가하거나 템플릿 또는 민감도 레이블에 의해 적용할 수 있습니다.

다음 표에서는 워터마크가 구성된 위치를 보여 줍니다.

|설정|관리 정책|민감도 레이블|템플릿|모임 이끌이|
|:------|:----------:|:---------------:|:------:|:---------------:|
|공유 콘텐츠에 워터마크 적용|예|예|예|예|
|모든 사용자의 비디오 피드에 워터마크 적용|예|예|예|예|

모임에서 워터마크를 사용하는 경우 다음 기능이 꺼집니다.

- 자동 녹음/녹화를 포함한 모임 녹음/녹화

- 대형 갤러리

- 함께 모드

- PowerPoint Live

- 화이트보드

- 카메라의 콘텐츠

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>중요하고 매우 민감한 모임에 대한 워터마크

워터마크는 모임에서 공유되는 기밀 정보를 보호하는 데 유용할 수 있습니다. 일반적으로 정보에 액세스할 수 없는 사용자와 정보를 공유할 때 가장 유용합니다. 예를 들어 재무 조직의 구성원은 여러 부서의 관리자와 분기별 추정치를 공유할 때 워터마크를 사용할 수 있습니다.

워터마크는 기밀 정보가 유출될 가능성을 줄이기 위해 설계되었으므로 모든 참가자가 공유되는 콘텐츠에 직접 액세스할 수 있는 모임에서 이를 사용하면 보안에 추가되지 않을 수 있습니다.

다른 모임 기능과 함께 워터마크를 사용하여 모임의 기밀 정보를 보호하는 방법에 대한 자세한 내용은 [매우 중요한 데이터에 대한 보호를 사용하여 Teams 모임 구성](/microsoftteams/configure-meetings-highly-sensitive-protection)을 참조하세요.

## <a name="enable-watermarks"></a>워터마크 사용

템플릿 및 민감도 레이블 및 모임 이끌이에게 워터마크를 사용할 수 있도록 하려면 Teams 관리 센터에서 워터마크를 사용하도록 설정해야 합니다.

모임에 워터마크를 사용하도록 설정하려면

1. Teams 관리 센터에서 **모임을** 확장하고 **모임 정책을** 선택합니다.

1. 업데이트하려는 정책을 선택합니다.

1. 참석자 비디오에서 워터마크를 사용하도록 설정하려면 **워터마크 비디오를** **켜** 기로 설정합니다.

1. 모임의 화면에서 공유된 콘텐츠에 워터마크를 사용하도록 설정하려면 **워터마크 공유 콘텐츠를** **켜** 기로 설정합니다.

    ![워터마크에 대한 Teams 관리 정책의 스크린샷](media/watermark-admin-policy.png)

1. 데스크톱 및 모바일 디바이스에서 워터마크가 어떻게 표시되는지 확인하려면 **미리 보기를** 선택합니다.

1. **저장** 을 선택합니다.

PowerShell을 사용하여 워터마크를 사용하거나 사용하지 않도록 설정할 수도 있습니다. 및 `-AllowWatermarkForScreenSharing` 매개 변수와 함께 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 `-AllowWatermarkForCameraVideo` 사용합니다.

예를 들면 다음과 같습니다.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>관련 주제

[세 가지 보호 계층으로 Teams 모임 구성](configure-meetings-three-tiers-protection.md)

[중요한 모임에 Teams 모임 템플릿, 민감도 레이블 및 관리자 정책을 함께 사용합니다.](meeting-templates-sensitivity-labels-policies.md)
