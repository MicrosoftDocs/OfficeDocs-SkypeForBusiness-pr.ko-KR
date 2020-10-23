---
title: 모임 녹화에 비즈니스용 OneDrive 및 SharePoint 사용
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
ms.openlocfilehash: ce6c5cc546c3c2e8b8369247de38e0f734b9b467
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739226"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 스트림 사용

> [!Note]
> Microsoft Stream을 비즈니스용 OneDrive 및 Microsoft SharePoint for Business에 대 한 변경 내용은 단계적으로 사용 됩니다.


|시작일|이벤트|
|---|-----------------|
|초기 Q4 CY20|**비즈니스용 OneDrive 및 SharePoint에 대 한 팀 모임 녹음/녹화를 옵트인 또는 옵트아웃 (opt out) 할 수 있습니다.**<br> 테 넌 트 관리자가 비즈니스용 OneDrive 및 SharePoint에서 옵트인 또는 선택 취소 하 여 PowerShell에서 팀 정책 설정|
|중급 Q4 CY20|**비즈니스용 OneDrive 및 SharePoint에서 팀 모임 녹음/녹화를 옵트아웃 하지 않은 테 넌 트에 대 한 기본값으로 설정**<br> 이는 대부분의 고객에 게 권장 되는 경로입니다.|
|Q1 CY21|**더 이상 허용 되지 않는 클래식 스트림으로 팀 모임 기록 저장**<br>모든 테 넌 트가 비즈니스용 OneDrive 및 SharePoint에 팀 모임 기록을 저장 합니다.|


Microsoft 팀에는 모임 녹음/녹화를 저장 하는 새로운 방법이 있습니다. 이 방법은 기존 Microsoft Stream에서 [새 스트림으로](https://docs.microsoft.com/stream/streamnew/new-stream)전환 하는 첫 번째 단계로, microsoft 365의 비즈니스용 Microsoft 비즈니스용 OneDrive 및 SharePoint에 기록을 저장 하 고 다양 한 혜택을 제공 합니다.

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

> [!Note]
> 모임 기록 옵션은 팀 정책 수준의 설정입니다. 다음 예제에서는 전역 정책을 설정 하는 방법을 보여 줍니다. 사용자에 게 할당 한 정책이 나 정책에 대 한 모임 기록 옵션을 설정 했는지 확인 합니다. 팀 정책 변경 사항은 전파 하는 데 시간이 걸립니다. 설정한 시간 후 다시 확인 한 후 로그 아웃 하 고 다시 로그인 합니다.

1. 비즈니스용 Skype Online PowerShell을 설치 합니다. 
**참고**: 비즈니스용 Skype Online 커넥터는 현재 최신 팀 PowerShell 모듈의 일부입니다. 최신 팀 PowerShell 공용 릴리스를 사용 하 고 있는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다. [PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)를 참조 하세요.

    a. [비즈니스용 Skype Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)을 다운로드 하세요. 

    b. 화면의 지시에 따라 설치 합니다.

    c. 컴퓨터를 다시 시작 합니다.

2. 관리자로 PowerShell 시작

3. SkypeOnline 커넥터를 가져오고 팀 관리자로 로그인 합니다.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) 를 사용 하 여 스트림 저장소에서 비즈니스용 OneDrive 및 SharePoint로 전환 하도록 팀 모임 정책을 설정 합니다.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>비즈니스용 OneDrive 및 SharePoint에서 스트림을 사용 하 여 계속 합니다.

정책이 **Stream**으로 설정 되어 있는 경우에도 설정 되지 않았을 수 있습니다. 일반적으로 정책이 설정 되어 있지 않으면 기본 설정은 **스트림**입니다. 그러나이 새로운 변경으로 인해 SharePoint 또는 OneDrive 사용을 옵트아웃 하려면 정책을 **스트림으로** 다시 설정 하 여 해당 설정이 기본값 인지 확인 해야 합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>사용 권한 또는 역할 기반 액세스


|모임 유형                               | 누가 레코드를 클릭 했습니까?| 녹화가 어디에 있나요?                               |누가 액세스 권한이 있나요? R/W, R 또는 공유                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|내부 파티와의 1:1 통화             |호출인                 |발신자의 비즈니스용 OneDrive 계정                        |-호출자가 소유자이 고 전체 권한 (동일한 테 넌 트)에 읽기 전용 액세스 권한이 있는 경우 공유 액세스-피호출자 (다른 테 넌 트에 있는 경우)는 액세스할 수 없습니다. 호출자는이를 피호출자와 공유 해야 합니다.|
|내부 파티와의 1:1 통화             |피호출자                 |피호출자의 비즈니스용 OneDrive 계정                        |-피호출자는 소유자 이며, 모든 권한 호출자 (동일한 테 넌 트에 읽기 전용 액세스 권한이 있는 경우, 공유 액세스 호출자 없음 (다른 테 넌 트에 있는 경우)에는 액세스할 수 없습니다. 피호출자가이를 피호출자와 공유 해야 합니다.|
|1:1 통화 (외부 통화 포함)             |호출인                 |발신자의 비즈니스용 OneDrive 계정                        |-호출자가 소유자이 고 전체 권한이 있는 경우 호출 수신자가 액세스할 수 없습니다. 호출자는이를 피호출자와 공유 해야 합니다.|
|1:1 통화 (외부 통화 포함)             |피호출자                 |발신자의 비즈니스용 OneDrive 계정                        |-피호출자는 소유자 이며, 모든 권한이 있는 호출자는 액세스할 수 없습니다. 피호출자가이를 호출자에 게 공유 해야 합니다.|
|그룹 통화                                 |통화의 모든 구성원 |Record의 비즈니스용 OneDrive 계정에서 클릭 한 구성원  |-레코드를 클릭 한 구성원에 게 모든 권한이 있는 경우-동일한 테 넌 트의 다른 구성원에 게 읽기 권한이 있습니다. 다른 테 넌 트의 다른 구성원에 대 한 권한은 없습니다.|
|임시/예약 된 모임                    |구성 도우미              |조직자의 비즈니스용 OneDrive 계정                     |-이끌이는 모든 녹음/녹화에 대 한 모든 권한을 가집니다-모임의 다른 모든 구성원은 읽기 권한이 있습니다.|
|임시/예약 된 모임                    |다른 모임 구성원   |레코드를 클릭 한 구성원                                  |-레코드를 클릭 한 구성원에 게 녹음/녹화 구성 도우미에 대 한 모든 권한이 있는 경우 모든 구성원에 게 편집 권한이 있고 공유할 수 있음-다른 모든 구성원이 읽기 권한을 가집니다.|
|외부 사용자와의 임시/예약 된 모임|구성 도우미              |조직자의 비즈니스용 OneDrive 계정                     |이끌이는 읽기 권한이 있으므로-organizer에는 같은 테 넌 트의 모든 다른 구성원의 기록에 대 한 모든 권한이 있습니다. 다른 모든 외부 구성원은 액세스 권한이 없으며 이끌이는이를 공유 해야 합니다.|
|외부 사용자와의 임시/예약 된 모임|다른 모임 구성원   |레코드를 클릭 한 구성원                                  |-레코드를 클릭 한 구성원에 게 녹음/녹화 구성 도우미에 대 한 모든 권한이 있는 경우 이끌이는 읽기 권한이 있고, 다른 모든 외부 구성원은 액세스할 수 없으며, 이끌이는이를 공유 해야 하는 경우에는 같은 테 넌 트에서 모임의 모든 구성원을 공유 합니다.|
|채널 모임                            |채널 구성원         |해당 채널에 대 한 팀의 SharePoint 위치                   |-레코드를 클릭 한 구성원에 게 녹음/녹화에 대 한 편집 권한이 있는 경우-다른 모든 구성원의 권한은 채널의 SharePoint 사용 권한에 따라 달라 집니다.|


## <a name="frequently-asked-questions"></a>자주하는 질문

**모임 녹화가 저장 되는 위치**

- 채널이 아닌 모임의 경우 녹음/녹화는 모임 녹음/녹화를 시작한 사람에 속하는 비즈니스용 OneDrive의 상위 수준 **에 있는 기록 이라는 폴더** 에 저장 됩니다. 예

  <i>레코더의 비즈니스용 OneDrive</i> / **기록**

- 채널 모임의 **경우 기록은 기록 이라는 폴더**의 팀 사이트 문서 라이브러리에 저장 됩니다. 예

  <i>팀 이름-채널 이름</i> / **문서** / **기록**

**이전 직원의 녹음/녹화를 처리 하려면 어떻게 하나요?**

비디오는 비즈니스용 OneDrive 및 SharePoint의 다른 파일과 유사 하기 때문에 직원을 떠난 후 소유권 및 보존 처리는 일반적인 [비즈니스용 onedrive 및 sharepoint 프로세스]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)를 따릅니다.

**모임 녹음/녹화를 볼 수 있는 권한이 있는 사람은 누구 인가요?**

- 채널이 아닌 모임의 경우 외부 사용자를 제외한 모든 모임 초대 대 상자가 개인 공유 링크를 자동으로 받게 됩니다. 외부 사용자는 모임 이끌이 또는 모임 녹음/녹화를 시작한 사용자가 공유 목록에 명시적으로 추가 해야 합니다.

- 채널 모임의 경우 사용 권한은 채널의 소유자 및 구성원 목록에서 상속 됩니다.

**어떻게 하면 증명서를 관리할 수 있나요?**

이 미리 보기를 사용 하는 고객에 게는 비즈니스용 OneDrive 및 SharePoint로 마이그레이션된 팀 모임 녹음/녹화에 대 한 폐쇄 캡션이 없습니다.여기서는 영어에서 선택 자막으로 시작 하 여 2020 년 10 월에 모임 녹음/녹화에 캡션을 추가 하는 작업을 진행 하 고 있습니다.

[팀 구름 기록](cloud-recording.md) 에 설명 된 대로 기록을 허용 하도록 옵트인 된 고객의 경우 선택 자막을 팀 모임 기록에 사용할 수 있습니다.

캡션은 모든 기능을 보는 사람을 위해 포괄 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 팀에서 캡션을 삭제 하지 않는 한 팀에서 성적을 사용할 수 있지만, 캡션을 숨길 수는 있습니다. [모임 녹음/녹화를 설정 하거나 해제 하는 방법](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization) 보기

폐쇄 캡션은 모임이 기록 될 때 60 일간의 팀 모임 기록에 대해 지원 됩니다.

팀 모임 녹화가 OneDrive 또는 SharePoint의 원래 위치에서 이동 또는 복사 되는 경우 선택 캡션이 완전히 지원 되지 않습니다.

**내 저장소 할당량에 영향을 주는 방법**

비즈니스용 OneDrive 및 SharePoint에 파일을 기록 하는 팀 모임에는 해당 서비스의 할당량에 포함 되어 있습니다. [SharePoint 할당량](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 및 [비즈니스용 OneDrive 할당량] ()을 참조 하세요 https://docs.microsoft.com/onedrive/set-default-storage-space) .

**팀 모임 녹음/녹화를 재생 하려면 어떻게 하나요?**

파일에 액세스 하는 위치에 따라 비즈니스용 OneDrive 또는 SharePoint의 비디오 플레이어에서 비디오가 재생 됩니다.

**Deprecating 추가를 계획 하는 경우 기존 비디오는 그대로 유지 되 고 얼마 동안 지속 되나요?**

플랫폼으로 스트림은 가까운 장래에 더 이상 사용 되지 않습니다. 현재 스트림에 살고 있는 비디오는 마이그레이션을 시작할 때까지 유지 됩니다. 마이그레이션에 따라 이러한 비디오는 ODSP로도 마이그레이션됩니다. 자세한 내용은 [여기](https://docs.microsoft.com/stream/streamnew/classic-migration) 를 참조 하세요.
