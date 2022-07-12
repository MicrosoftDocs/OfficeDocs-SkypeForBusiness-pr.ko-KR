---
title: 실시간 원격 분석을 사용하여 모임 품질 저하 문제 해결
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
description: 디바이스, 네트워크 및 연결에 대한 세부 정보와 함께 실시간 원격 분석을 사용하여 Microsoft Teams 예약 모임의 사용자 문제를 해결합니다.
ms.openlocfilehash: 794c0097c3bdcc757e0a469cb0f65b5eb4e6c285
ms.sourcegitcommit: ce1cbdcfce8c785c66f6a51ef8e84092124f3ef0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66716804"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>실시간 원격 분석을 사용하여 모임 품질 저하 문제 해결

이 문서에서는 RTA(Real-Time Analytics)를 사용하여 개별 사용자의 Microsoft Teams 모임 품질 저하 문제를 해결하는 방법을 설명합니다. 다음 역할 중 하나가 있는 경우 Real-Time Analytics에 액세스할 수 있습니다.

- Teams 관리자
- Teams 커뮤니케이션 지원 전문가
- Teams 커뮤니케이션 지원 엔지니어

Teams 관리자 역할에 대한 자세한 내용은 [Microsoft Teams 관리자 역할을 사용하여 Teams를 관리하세요](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics를 사용하면 IT 관리자가 중요한 사용자의 예약된 모임을 살펴보고 오디오, 비디오, 콘텐츠 공유 및 네트워크 관련 문제를 볼 수 있습니다. 관리자는 이 원격 분석을 사용하여 모임 중에 이러한 문제를 조사하고 실시간으로 문제를 해결할 수 있습니다.

## <a name="what-is-real-time-analytics"></a>Real-Time Analytics란?

현재 모임이 종료된 후 [Call Analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) 를 통해 Teams 관리자가 개별 모임 문제 해결을 사용할 수 있습니다. Real-Time Analytics를 사용하면 관리자가 진행 중인 동안 예약된 모임의 문제를 해결할 수 있습니다.

Real-Time Analytics는 실시간으로 업데이트된 Office 365 계정의 각 사용자에 대한 Teams 모임에 대한 자세한 정보를 표시합니다. 여기에는 디바이스, 네트워크, 연결, 오디오, 비디오 및 콘텐츠 공유 문제에 대한 정보가 포함되어 있어 관리자가 통화 품질을 보다 효과적으로 해결하는 데 도움이 됩니다.

Teams 관리자는 각 사용자에 대한 모든 실시간 원격 분석 데이터에 대한 모든 액세스 권한을 얻습니다. 또한 Azure Active Directory 역할을 할당하여 직원을 지원할 수 있습니다. 이러한 역할에 대한 자세한 내용은 [지원 및 지원 센터 직원에게 사용 권한 부여를](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) 참조하세요.

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>사용자별 실시간 문제 해결 원격 분석을 찾을 수 있는 위치

사용자의 모든 모임 정보 및 데이터를 보려면 [Teams 관리 센터로](https://admin.teams.microsoft.com) 이동합니다. **사용자 관리 사용자** >  아래에서 사용자를 선택하고 사용자의 프로필 페이지에서 **모임 & 통화** 탭을 엽니다. **최근 모임** 에는 진행 중인 모임을 포함하여 *실시간 원격 분석을 사용할 수 있는* 지난 24시간 이내에 사용자가 참석한 모임 목록이 표시됩니다. 모임이 진행 중이 아니거나 실시간 원격 분석 데이터가 없는 경우 **과거 모임** 에 표시됩니다.

:::image type="content" alt-text="최근 모임 테이블의 스크린샷" source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

디바이스, 네트워크 및 오디오 통계를 포함하여 진행 중인 모임 참가자에 대한 추가 정보를 얻으려면 **최근 모임** 에서 모임을 찾고 **참가자** 열 아래의 링크를 선택합니다.

:::image type="content" alt-text="참가자 세부 정보 테이블의 스크린샷." source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

디바이스, 네트워크, 오디오, 비디오 및 콘텐츠 공유 세부 정보에 대한 정보를 포함하여 진행 중인 모임에 대해 지정된 사용자의 원격 분석을 보려면 **모임 ID** 를 선택합니다.

:::image type="content" alt-text="통화 분석 사용자 세션 데이터의 스크린샷." source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Real-Time Analytics에서 사용할 수 있는 세부 정보 및 측정값

### <a name="device-information"></a>디바이스 정보
| 이름 | 설명 | 빈 값에 대한 가능한 이유|
|:---|:---|:---|
| 오디오 캡처 디바이스 | 사용 중인 오디오 캡처 디바이스의 이름(예: 마이크) | 시스템에 디바이스와 연결된 이름이 없을 수 있습니다(예: 원격 데스크톱 또는 가상 머신 '원격 오디오' 디바이스).  |
| 오디오 렌더링 디바이스 | 사용 중인 오디오 렌더링 디바이스의 이름(예: 스피커 또는 헤드폰) | 시스템에 디바이스와 연결된 이름이 없을 수 있습니다(예: 원격 데스크톱 또는 가상 머신 '원격 오디오' 디바이스).  |
| 비디오 캡처 디바이스 | 사용 중인 비디오 캡처 디바이스의 이름 | 사용자가 모니터링 중인 엔드포인트에서 비디오를 보내지 않습니다. |

### <a name="connectivity-information"></a>연결 정보
| 메트릭 | 단위/가능한 값 | 설명 | 빈 값에 대한 가능한 이유|
|:---|:---|:---|:---|
| 네트워크 유형 | &bull; 이더넷 <br/> &bull; Wi-Fi | 사용 중인 네트워크 연결 유형 | |
| Wi-Fi 강도 | &bull; 우수 : -50dBm 이상 <br/> &bull; 양호 : -51 dBm ~ -64 dBm<br/> &bull; 불량: -65dBm 이하 | 사용자의 현재 Wi-Fi 연결 강도 | 사용자가 Wi-Fi 연결되지 않았습니다. |
| Wi-Fi 채널 | 정수 | Wi-Fi 네트워크의 액세스 지점이 브로드캐스트되는 채널 | 사용자가 Wi-Fi 연결되지 않았습니다. |
| 물리적 형식 | 문자열 <br/> &bull; 예: 802.11ac | 사용 중인 무선 인프라 유형 | 사용자가 Wi-Fi 연결되지 않았습니다. |
| Wi-Fi 밴드 | 2.4GHz 또는 5GHz | 사용자가 연결된 Wi-Fi 밴드 | 사용자가 Wi-Fi 연결되지 않았습니다. |
| 위치 | 문자열 | 사용자가 있는 국가 | 사용자의 위치 정보가 차단되었거나 사용할 수 없음 |
| 로컬 IP 주소 | 문자열(IP:포트) | 사용자 엔드포인트 및 미디어 포트의 로컬 IP 주소 | |
| 서버 반사 IP 주소 | 문자열(IP:포트) | 사용자 엔드포인트 및 미디어 포트의 공용 IP 주소 | |
| 연결 유형 | UDP 또는 TCP | 사용 중인 전송 계층 프로토콜; UDP는 실시간 미디어에 선호됩니다. | |

### <a name="user-signals"></a>사용자 신호
사용자 신호는 사용자가 통화에 적극적으로 참여하거나, 말하고 있지 않고, 음소거되지 않거나, 음소거된 경우를 식별합니다. 현재 사용자 신호는 오디오에만 사용할 수 있습니다.

| 형식 | 가능한 값 | 설명 |
|:---|:---|:---|
| 오디오 | &bull; 무명, 참가자 말하기 <br/> &bull; 평판이 좋지 않고 말하기가 아닙니다. <br/> &bull; 음소거 | 통화의 오디오 부분에 대한 사용자의 동작을 나타냅니다.  |


### <a name="audio"></a>오디오
|측정값 이름 |단위 |양수 임계값 |설명 |
|:---|:---|:---|:---|
|지터 |밀리초 |30ms 미만 |지터는 데이터 스트림에 대한 패킷 지연의 변화를 측정한 값입니다. 이 값이 너무 높으면 오디오가 고르지 않습니다. | 
|패킷 손실 |비율 |5% 미만 |패킷 손실은 데이터 패킷이 대상에 도달하지 못할 때 발생합니다. 손실된 패킷의 백분율은 전송된 총 패킷 수를 기준으로 합니다. |
|왕복 시간 |밀리초 |500ms 미만 |왕복 시간은 단일 패킷이 클라이언트에서 원격 엔드포인트로 이동하고 클라이언트로 다시 이동하는 데 걸리는 시간입니다. 왕복 시간이 높으면 스트림 재생이 지연될 수 있습니다. 예를 들어 모임에 참석한 두 사람이 지연으로 인해 의도치 않게 서로 말하는 경우가 있습니다. 아웃바운드 오디오에만 표시됩니다. |
|비트 레이트 |초당 킬로비트(Kbps) |24Kbps보다 큼 |초당 킬로비트로 표현된 오디오 스트림의 처리량입니다. |
| 코덱 | 문자열 <br/> &bull; 예: SATIN | 정보만 | 보내고 받는 오디오 코덱을 표시합니다. 전송되는 코덱과 다른 코덱을 받을 수 있습니다. |


### <a name="video"></a>비디오
|측정값 이름 |단위 |양수 임계값 |설명 |
|:---|:---|:---|:---|
|왕복 시간 |밀리초 |500ms 미만 |왕복 시간은 단일 패킷이 클라이언트에서 원격 엔드포인트로 이동하고 클라이언트로 다시 이동하는 데 걸리는 시간입니다. 왕복 시간이 높으면 스트림 재생이 지연될 수 있습니다. 예를 들어 모임에 참석한 두 사람이 지연으로 인해 의도치 않게 서로 말하는 경우가 있습니다. |
|비트 레이트 |초당 메가비트(Mbps) | 정보만 |초당 메가비트로 표현된 비디오 스트림의 처리량입니다. |
|프레임 속도(비디오) |초당 프레임 수 |360p 이상: 25-30 FPS <br/> 270p 이하: 7-15 FPS |아웃바운드 비디오 스트림의 경우 FPS(프레임 속도)는 클라이언트가 전송하는 비디오의 초당 프레임 수입니다. 여기서 예상보다 낮은 값은 시스템 리소스 제약 조건, 네트워크 대역폭 부족 또는 비디오 캡처 디바이스의 잘못된 동작을 제안할 수 있습니다. 해상도가 다르면 허용되는 FPS 범위가 다릅니다. |
|코덱 |문자열 | 정보만 |아웃바운드 비디오 스트림의 비디오 코덱 및 렌더링 모드를 표시합니다. (예: H264 SW HW는 소프트웨어 및 하드웨어 렌더링을 모두 사용하는 H264 비디오 스트림을 나타냅니다.)|
|해결 방법 |픽셀 | 정보만 |전송되는 비디오의 해상도입니다. 아웃바운드 비디오 해상도는 모임의 엔드포인트에서 가장 높은 요구 사항에 따라 동적입니다. 1920 x 1080 비디오를 사용하는 클라이언트는 640 x 360보다 큰 프레임에 해당 사용자의 비디오를 표시하는 클라이언트가 없는 경우에만 640 x 360 비디오를 보냅니다. |


### <a name="application-sharing-vbss"></a>VBSS(애플리케이션 공유)
|측정값 이름 |단위 |양수 임계값 |설명 |
|:---|:---|:---|:---|
|패킷 손실 |비율 |5% 미만 |패킷 손실은 데이터 패킷이 대상에 도달하지 못할 때 발생합니다. 손실된 패킷의 백분율은 전송된 총 패킷 수를 기준으로 합니다. |
|왕복 시간 |밀리초 |500ms 미만 |왕복 시간은 단일 패킷이 클라이언트에서 원격 엔드포인트로 이동하고 클라이언트로 다시 이동하는 데 걸리는 시간입니다. 왕복 시간이 높으면 스트림 재생이 지연될 수 있습니다. 예를 들어 모임에 참석한 두 사람이 지연으로 인해 의도치 않게 서로 말하는 경우가 있습니다. |
|비트 레이트 |초당 메가비트(Mbps) | 정보만 |초당 메가비트로 표현되는 VBSS 스트림의 처리량입니다. |
|프레임 속도 |FPS(초당 프레임 수) | 정보만 |VBSS의 경우 프레임 속도는 필요한 경우 프레임 전송을 피하면서 적절한 환경을 보장하기 위해 필요한 만큼의 프레임을 전송하도록 콘텐츠를 인식합니다. 예를 들어, 화면의 텍스트 문서를 공유하려면 좋은 환경을 만들기 위해 초당 1프레임만 필요하지만, 더 많은 활동으로 비디오 또는 콘텐츠를 공유하면 초당 프레임이 최대 30FPS로 증가하여 더 원활한 환경을 만들 수 있습니다. |
|코덱 |문자열 | 정보만 |VBSS 스트림의 코덱 및 렌더링 모드를 표시합니다. (예: H264 SW HW는 소프트웨어 및 하드웨어 렌더링을 모두 사용하는 H264 VBSS 스트림을 나타냅니다.)|
|해결 방법 |픽셀 | 정보만 |보내고 받는 VBSS 스트림의 확인입니다. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>실시간 원격 분석에 지원되는 클라이언트 플랫폼

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams 웹 클라이언트(VDI 포함)는 원격 분석 배달을 실시간으로 지원하지 않습니다.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>실시간 원격 분석을 지원하는 Teams 디바이스

- MTR - Surface Hub
- MTR - Teams 디스플레이
- MTR - 공동 작업 표시줄
- IP Phone 디바이스

> [!NOTE]
> CVI(Cloud Video Interop) 솔루션을 사용하여 모임에 참가한 디바이스는 Real-Time Analytics에서 지원되지 않습니다.


## <a name="limitations"></a>제한 사항

- 실시간 원격 분석은 예약된 모임 및 지금 모임에만 사용할 수 있습니다. PSTN, 1:1 호출 및 그룹 호출의 경우 실시간 원격 분석을 사용할 수 없습니다.
- 실시간 원격 분석은 예약된 라이브 이벤트의 발표자만 사용할 수 있습니다. 현재 라이브 이벤트 참석자는 사용할 수 없습니다.
- 실시간 원격 분석 데이터는 모임이 종료된 후 24시간 동안 **최근 모임** 에서 모임에 사용할 수 있습니다. 24시간이 지나면 데이터에 액세스할 수 없으며 모임이 **과거 모임** 으로 이동합니다. 모임이 3시간보다 긴 경우 실시간 원격 분석은 *지난 3시간* 동안만 사용할 수 있습니다.
- 이전 버전의 Teams를 사용하는 경우 원격 분석을 실시간으로 사용할 수 없습니다. 사용할 수 있는 원격 분석이 없는 경우 클라이언트를 업데이트해 보세요.
- 외부 참가자 또는 익명 사용자가 모임에 참가하는 경우 해당 표시 이름은 테넌트 간 개인 정보를 유지할 **수 없는** 것으로 표시됩니다.

> [!NOTE]
> 제한된 시간 공개 미리 보기의 일환으로 실시간 원격 분석 데이터는 모임이 종료된 후 **7일 동안** 사용할 수 있습니다. 위의 제한은 공개 미리 보기가 완료되면 적용됩니다.

## <a name="related-topics"></a>관련 항목

[사용자별 통화 분석 설정](set-up-call-analytics.md)

[Microsoft Teams 관리자 역할을 사용하여 Teams를 관리합니다](/MicrosoftTeams/using-admin-roles).
