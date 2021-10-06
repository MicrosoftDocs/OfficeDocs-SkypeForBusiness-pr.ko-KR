---
title: 실시간 원격 분석을 사용하여 열악한 모임 품질 문제 해결
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 디바이스, 네트워크 및 연결에 대한 세부 정보를 사용하여 실시간 원격 분석을 사용하여 예약된 모임에서 사용자 Microsoft Teams 문제를 해결합니다.
ms.openlocfilehash: 94b303687995ac3bcd765991dbfeb41c6f1459e7
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138364"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>실시간 원격 분석을 사용하여 열악한 모임 품질 문제 해결

> [!NOTE]
> 이 기능은 현재 2021년 말까지 공개 미리 보기로 제공됩니다. 이 시간 이후에는 실시간으로 보려 하는 각 Microsoft Teams 사용자에 대한 고급 통신 추가 기능도 필요합니다. 자세한 내용은 [Microsoft Teams를 위한 고급 통신 추가 기능](/MicrosoftTeams/teams-add-on-licensing/advanced-communications)을 참조하세요.

이 문서에서는 RTA(Real-Time)를 사용하여 개별 사용자의 모임 Microsoft Teams 문제를 해결하는 방법을 설명합니다. 다음 역할 중 Real-Time 있는 경우 분석 분석에 액세스할 수 있습니다.

- Teams 관리자
- Teams 통신 지원 전문가
- Teams 커뮤니케이션 지원 엔지니어

관리자 역할에 대한 Teams 자세한 내용은 [관리자](/MicrosoftTeams/using-admin-roles)Microsoft Teams 관리자 역할 사용 을 Teams.

Real-Time 분석을 통해 IT 관리자는 중요한 사용자의 예약된 모임을 보고 오디오, 비디오, 콘텐츠 공유 및 네트워크 관련 문제를 볼 수 있습니다. 관리자는 이 원격 분석 을 사용하여 모임 중에 이러한 문제를 조사하고 실시간으로 문제를 해결할 수 있습니다.

## <a name="what-is-real-time-analytics"></a>분석이란 Real-Time 무엇입니까?

현재 개별 모임 문제 해결은 모임이 Teams 후에 [Call Analytics를](use-call-analytics-to-troubleshoot-poor-call-quality.md) 통해 관리자에게 제공됩니다. Real-Time 분석에서는 관리자가 예약된 모임을 진행하는 동안 문제를 해결할 수 있습니다.

Real-Time 분석은 실시간으로 업데이트된 Teams 계정의 각 Office 365 모임에 대한 자세한 정보를 보여줍니다. 여기에는 디바이스, 네트워크, 연결, 오디오, 비디오 및 콘텐츠 공유 문제에 대한 정보가 포함되어 있으며, 관리자가 통화 품질 문제를 보다 효과적으로 해결하는 데 도움이 됩니다.

관리자 Teams 각 사용자의 모든 실시간 원격 분석 데이터에 대한 모든 액세스 권한을 얻을 수 있습니다. 또한 직원 지원에 Azure Active Directory 역할을 할당할 수 있습니다. 이러한 역할에 대한 자세한 내용은 지원 및 지원 센터 직원에 대한 권한 [부여를 참조합니다.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>사용자당 실시간 문제 해결 원격 분석 찾기 위치

사용자에 대한 모든 모임 정보 및 데이터를 표시하려면 Teams [관리 센터로 이동하세요.](https://admin.teams.microsoft.com) 사용자 **관리** 아래에서 사용자를 선택하고 사용자의 프로필 페이지에서 & 모임 탭을  >  니다.  최근 **모임에서** 진행 중 모임을 포함하여 실시간 원격 분석이 가능한 지난 24시간 이내에 사용자가 참석한 모임 목록이 표시됩니다.  모임이 진행 중이 아니거나 실시간 원격 분석 데이터가 없는 경우 과거 모임에 **표시됩니다.**

![최근 모임 테이블의 스크린샷.](media/recent-meetings.png)

디바이스, 네트워크 및 오디오 통계를 포함하여 진행 중인 모임의 참가자에 대한 추가 정보를  얻하려면 최근 모임에서 모임을 찾아 참가자 열 아래 링크를 **선택합니다.**

![참가자 세부 정보 테이블의 스크린샷.](media/participant-details.png)

디바이스, 네트워크, 오디오, 비디오 및 콘텐츠 공유 세부 정보를 포함한 진행 중 모임에 대한 특정 사용자의 원격 분석에서 모임 ID 를 **선택합니다.**

![통화 분석 사용자 세션 데이터의 스크린샷.](media/real-time-telemetry.png)

## <a name="measures-available-in-real-time-analytics"></a>분석에서 사용할 Real-Time 측정값

|측정 이름 |단위 |양호한 임계값 |설명 |
|:---|:---|:---|:---|
|지터 |밀리초 |30 ms 미만 |Jitter는 데이터 스트림에 대한 패킷 지연의 변동을 측정하는 척도입니다. 이 너무 높을 경우 오디오가 희미해질 수 있습니다. | 
|패킷 손실 |백분율 |5% 미만 |패킷 손실은 데이터 패킷이 대상에 도달하지 못할 때 발생합니다. 손실된 패킷의 백분율은 전송된 총 패킷 수를 기준으로 합니다. |
|왕복 시간 |밀리초 |500 ms 미만 |왕복 시간은 단일 패킷이 클라이언트에서 원격 엔드포인트로 이동하고 클라이언트로 돌아가는 데 걸리는 시간입니다. 왕복 시간이 높을 경우 스트림 재생이 지연될 수 있습니다. 한 예로, 모임에 참석한 두 사람이 지연으로 인해 의도치 않은 말을 하는 경우입니다. |
|비트레이트(오디오) |초당 킬로비트(Kbps) |24 Kbps보다 크다. |초당 킬로비트로 표현된 오디오 스트림의 사용률입니다. |
|비트레이트(비디오 & 앱 공유) |초당 메가비트(Mbps) | 정보만 |초당 메가비트로 표현된 비디오 스트림의 데이터입니다. |
|프레임 속도(비디오) |초당 프레임 |360p 이상: 25-30 FPS <br/> 270p 이상: 7-15 FPS |아웃바운드 비디오 스트림의 경우 FPS(프레임 속도)는 클라이언트가 보내는 비디오의 초당 프레임 수입니다. 예상 값보다 낮을 경우 시스템 리소스 제약 조건, 부족한 네트워크 대역폭 또는 비디오 캡처 디바이스의 잘못된 사용이 제안될 수 있습니다. 다른 해상도에는 허용되는 FPS 범위가 다릅니다. |
|프레임 속도(앱 공유) |FPS(초당 프레임) |정보만 |앱 공유의 경우 프레임 속도는 필요한 경우 프레임 전송을 피하면서 적절한 환경을 보장하기 위해 필요한 경우 많은 프레임을 전송할 수 있도록 콘텐츠 인식입니다. 예를 들어 화면에서 텍스트 문서를 공유하려면 좋은 환경을 만들려면 초당 1프레임만 필요하고, 더 많은 활동으로 비디오 또는 콘텐츠를 공유하면 초당 프레임이 최대 30FPS로 증가하여 더 부드러운 환경을 만들 수 있습니다. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>실시간 원격 분석에 지원되는 클라이언트 플랫폼

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams 원격 분석에 대한 지원이 있는 디바이스

- MTR - Surface Hub
- MTR - Teams 디스플레이
- MTR - 공동 작업 표시줄
- IP 전화 디바이스

## <a name="limitations"></a>제한 사항

- 실시간 원격 분석은 예약된 모임에만 사용할 수 있습니다. 지금 모임, PSTN, 1:1 통화 및 그룹 통화와 같은 추가 모임의 경우 실시간 원격 분석은 사용할 수 없습니다.
- 실시간 원격 분석은 예약된 라이브 이벤트의 발표자만 사용할 수 있습니다. 현재 라이브 이벤트 참석자에 대해 사용할 수 없습니다.
- 실시간 원격 분석 데이터는 모임이 종료된  후 24시간 동안 최근 모임에서 모임에 사용할 수 있습니다. 24시간 후에 데이터에 액세스할 수 없습니다. 모임이 지난 모임으로 **이동합니다.** 모임이 3시간보다 길면 실시간 원격 분석은 지난 *3시간 동안만 사용할 수 있습니다.*
- 이전 버전의 데이터를 사용할 때 원격 분석은 실시간으로 사용할 수 Teams. 원격 분석이 사용할 수 없는 경우 클라이언트를 업데이트해 시도합니다.
- 외부 참가자 또는 익명 사용자가 모임에 참가하는 경우  해당 표시 이름은 테넌트 간 개인 정보를 유지할 수 없음으로 표시됩니다.

## <a name="related-topics"></a>관련 항목

[사용자당 통화 분석 설정](set-up-call-analytics.md)

[관리자 Microsoft Teams 을 사용하여 를 관리 Teams.](/MicrosoftTeams/using-admin-roles)
