---
title: 모임 녹음/녹화에 OneDrive 및 SharePoint 사용
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft 팀에서 스트림을 비즈니스용 OneDrive 및 SharePoint 모임 기록 저장소로 전환 하는 방법을 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1072f86d019415dbc97d0507ff9d76b2cbdc6e6
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269642"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 스트림 사용

> [!Note]
> Microsoft Stream에서 모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint로의 변경은 단계별로 접근합니다. 시작 시 테 넌 트 관리자는 지금이 새 워크플로 옵션을 선택할 수 있으며, 2020 년 10 월부터 비즈니스용 OneDrive 및 SharePoint에 대 한 녹음/녹화 자동 업로드를 표시 하기 시작 합니다. 11 월에는 스트림을 계속 사용 하기 위해 옵트아웃 해야 하며, 초기 2021에는 모든 고객이 비즈니스용 OneDrive 및 SharePoint를 사용 하 여 새 모임 녹화가 필요 합니다.

Microsoft 팀에는 모임 녹음/녹화를 저장 하는 새로운 방법이 있습니다. Stream에서 출발 하는 경우이 메서드는 Microsoft 365에서 Microsoft OneDrive 및 SharePoint를 사용 하 고 다양 한 혜택을 제공 합니다.

비즈니스용 OneDrive 및 SharePoint를 사용 하 여 기록을 저장할 때의 이점은 다음과 같습니다.

- TMR (팀 모임 기록) 용 보존 정책 (S + C E5 autoretention 레이블)
- 비즈니스용 OneDrive 및 SharePoint 정보 관리 혜택
- 손쉬운 사용 권한 및 공유 설정
- 명시적 공유로만 게스트 (외부 사용자)와 녹음/녹화 공유
- 액세스 흐름 요청
- 비즈니스용 OneDrive 및 SharePoint 공유 링크 제공
- 할당량 증가
- 모임 녹음/녹화 속도 향상
- **로컬** 테 넌 트 이동 지원
- 다중 지역 지원 – 녹음/녹화가 해당 사용자와 관련 된 지역에 저장 됩니다.
- 자체 키 (BYOK) 지원
- 향상 된 성적 품질 및 강연자 특성

다음과 같은 몇 가지 제한 사항을 고려해 야 합니다.

- 영어 전용 자막 및 성적 증명서가 있습니다.
- 본 대화 내용 또는 해당 콘텐츠는 검색할 수 없습니다.
- 성적 증명서는 편집할 수 없지만, 캡션을 설정/해제할 수 있습니다.
- 녹음/녹화를 공유한 사람을 제어할 수 있지만, 공유 액세스 권한이 있는 사용자는 녹음/녹화를 다운로드 하지 못하도록 차단할 수 없습니다.
- 녹음/녹화가 완료 되 면 전자 메일을 받을 수 없지만, 완료 되 면 녹음 내용이 모임 채팅에 표시 됩니다. 이는 이전에 스트림에서 했던 것 보다 훨씬 더 빠르게 수행 됩니다.

자세한 내용은 "모임 녹음/녹화"를 시청 하세요.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>비즈니스용 OneDrive 및 SharePoint에 대 한 모임 녹음/녹화 옵션 설정

1. 비즈니스용 Skype Online PowerShell 관리 콘솔을 설치 합니다.

    a. [비즈니스용 Skype Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)을 다운로드 하세요.

    b. 화면의 지시에 따라 설치 합니다.

    c. 컴퓨터를 다시 시작 합니다.

2. 관리자로 PowerShell 시작

3. SkypeOnline 커넥터를 가져오고 팀 관리자로 로그인 합니다.

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 를 사용 하 여 스트림 저장소에서 odsp로 전환 하도록 팀 모임 정책을 설정 합니다.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>비즈니스용 OneDrive 및 SharePoint에서 스트림을 사용 하 여 계속 합니다.

정책이 이미 **Stream**으로 설정 되어 있는 경우에도 설정 되지 않았을 수 있습니다. Nothing으로 설정 된 경우 기본값은 스트림입니다. 옵트아웃 (opt out) 하려면 해당 스트림이 기본값 인지 확인 하기 위해 정책을 **스트림으로** 다시 설정 **해야 합니다** .

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>자주하는 질문

**모임 녹화가 저장 되는 위치**

- 채널이 아닌 모임의 경우 기록은 이라는 폴더에 저장 됩니다. 기록 * * 모임 녹음/녹화를 시작한 사람에 속한 OneDrive의 최상위 수준에 있습니다. 예

  <i>레코더의 비즈니스용 OneDrive</i> / **기록**

- 채널 모임의 **경우 기록은 기록 이라는 폴더**의 팀 사이트 문서 라이브러리에 저장 됩니다. 예

  <i>팀 이름-채널 이름</i> / **문서** / **기록**

**모임 녹음/녹화를 볼 수 있는 권한이 있는 사람은 누구 인가요?**

- 채널이 아닌 모임의 경우 외부 사용자를 제외한 모든 모임 초대 대 상자가 개인 공유 링크를 자동으로 받게 됩니다. 외부 사용자는 모임 이끌이 또는 모임 녹음/녹화를 시작한 사용자가 공유 목록에 명시적으로 추가 해야 합니다.

- 채널 모임의 경우 사용 권한은 채널의 소유자 및 구성원 목록에서 상속 됩니다.

**어떻게 하면 증명서를 관리할 수 있나요?**

이 미리 보기를 사용 하는 고객에 게는 OneDrive 및 SharePoint로 마이그레이션된 팀 모임 녹음/녹화에 대 한 폐쇄 캡션이 없습니다.여기서는 영어에서 선택 자막으로 시작 하 여 2020 년 10 월에 모임 녹음/녹화에 캡션을 추가 하는 작업을 진행 하 고 있습니다.

[팀 구름 기록](cloud-recording.md) 에 설명 된 대로 기록을 허용 하도록 옵트인 된 고객의 경우 선택 자막을 팀 모임 기록에 사용할 수 있습니다.

캡션은 모든 기능을 보는 사람을 위해 포괄 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 팀에서 캡션을 삭제 하지 않는 한 팀에서 성적을 사용할 수 있지만, 캡션을 숨길 수는 있습니다. [모임 녹음/녹화를 설정 하거나 해제 하는 방법](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization) 보기

폐쇄 캡션은 모임이 기록 될 때 60 일간의 팀 모임 기록에 대해 지원 됩니다.

**내 저장소 할당량에 영향을 주는 방법**

비즈니스용 OneDrive 및 SharePoint에 파일을 기록 하는 팀 모임에는 해당 서비스의 할당량에 포함 되어 있습니다. [SharePoint 할당량](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 및 [비즈니스용 OneDrive 할당량] ()을 참조 하세요 https://docs.microsoft.com/onedrive/set-default-storage-space) .

**팀 모임 녹음/녹화를 재생 하려면 어떻게 하나요?**

파일에 액세스 하는 위치에 따라 비즈니스용 OneDrive 또는 SharePoint의 비디오 플레이어에서 비디오가 재생 됩니다.
