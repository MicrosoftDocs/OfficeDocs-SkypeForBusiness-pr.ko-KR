---
title: Microsoft 팀에서 실시간 이벤트 계획
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Microsoft 팀에서 실시간 이벤트를 설정 하기 전에 고려해 야 할 사항에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f5d3b21b1a41779a094ba7b782b309365bc9503
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "36184760"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Microsoft 팀에서 실시간 이벤트 계획

조직에서 대규모 모임을 유지 하기 위해 팀 live 이벤트를 계획 하는 경우, 모두 설정 하기 전에 고려해 야 할 몇 가지 요소가 있습니다. 

## <a name="who-can-create-and-schedule-live-events"></a>누가 라이브 이벤트를 만들고 예약할 수 있나요? 
사용자가 팀 라이브 이벤트를 예약 하려면 다음 전제 조건이 필요 합니다.

할당 해야 하는 라이선스는 다음과 같습니다.  
- Office 365 Enterprise E1, E3 또는 E5 라이선스 또는 Office 365 A3 또는 A5 라이선스
- Microsoft 팀 라이선스
- Microsoft Stream 라이선스

> [!IMPORTANT]
> 라이브 이벤트를 만들고 예약 하는 사용자에 게 Exchange Online 사서함이 있어야 합니다.

Office 365 라이선스는 인증 된 사용자로 라이브 이벤트에 참가 해야 하지만,이 요구 사항은 사용 되는 프로덕션 방법에 따라 달라 집니다.

- **팀에서 생성 된 이벤트의 경우**  사용자에 게 팀 라이선스를 할당 해야 합니다.
- **외부 앱 또는 장치에서 생성 된 이벤트의 경우** 사용자에 게 스트림 라이선스를 할당 해야 합니다.

라이선스에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.

사용자는 다음을 가져야 합니다.
- 팀에서 비공개 모임 일정을 사용 하도록 설정 했습니다 (*TeamsMeetingPolicy-AllowPrivateMeetingScheduling parameter = True*).
- 팀 모임에서 비디오 공유를 사용 하도록 설정 했습니다 (*TeamsMeetingPolicy-AllowIPVideo parameter = True*).
- 팀 모임에서 화면 공유를 사용할 수 있습니다 (*TeamsMeetingPolicy-ScreenSharingMode parameter = EntireScreen*).
- 팀에서 실시간 이벤트 일정을 사용 하도록 설정 했습니다 (*TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling 매개 변수 = True*).
- 스트림 (외부 앱 또는 장치 프로덕션용)에서 라이브 이벤트를 만들 수 있는 권한입니다.

> [!IMPORTANT]
> Office 365 게스트, 페더레이션 및 익명 사용자는 팀 라이브 이벤트에서 제작자 또는 발표자로 초대 될 수 없습니다. Office 365 게스트 및 페더레이션 사용자는 라이브 이벤트만 익명으로 볼 수 있습니다. 
 
## <a name="who-can-watch-live-events"></a>누가 라이브 이벤트를 볼 수 있나요?

|**참석자 표시**       |**팀 생산**  |**외부 앱 또는 장치 프로덕션**  |
|------------------------------|-----------------|----------------------|
|공용 (익명 사용자)      |  '            |  아니요                  |
|게스트 사용자                   |  없음<sup>1</sup> |  아니요                  |
|페더레이션된 회사의 모든 사용자 |  없음<sup>2</sup> |  아니요                  |
|회사의 모든 사용자           |  '            |  '                 |
|특정 그룹/사람      |  '            |  '                 |

라이브 이벤트가 **조직 전체** 옵션을 사용 하 여 설정 된 경우 <sup>1</sup> 은 라이브 이벤트를 볼 수 있습니다.<br>
<sup>2</sup> 는 실시간 이벤트만 익명 사용자로 볼 수 있습니다.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>팀 live 이벤트 및 Skype 모임 브로드캐스트
다음 표에는 라이브 이벤트에 제공 되는 핵심 기능 및 기능과 Skype 모임 브로드캐스트와의 차이가 표시 됩니다. 

|**성능**   |**Skype 모임 브로드캐스트** |**팀에서 생성 된 이벤트** |**외부 앱 또는 장치에서 생성 된 이벤트** |
|---------|---------|---------|---------|
|최대 대상 그룹 크기 |1만 참석자 |1만 참석자 * |1만 참석자 * |
|라이브 이벤트의 최대 지속 시간 |4 시간 |4 시간 |4 시간 |
|Office 365 테 넌 트 당 최대 동시 라이브 이벤트 수 |~  | ~  | ~  |
|라이브 이벤트 만들기 |   Skype 모임 브로드캐스트 포털 |팀, 팀을 통한 Yammer | 팀, 팀을 통한 Yammer, 스트림 |
|대상 그룹 참여-Yammer |&#x2714; |&#x2714; (통합 환경) |&#x2714; (통합 환경) |
|대상 그룹 계약 – 중재 질문에 대 한 & |&#x2714;  |&#x2714; |&#x2714; |
|Windows의 생산자 클라이언트 |&#x2714; (비즈니스용 Skype) |&#x2714; (팀) |&#x2714; (스트림, 스트림 Embed를 통한 팀) |
|Mac의 생산자 클라이언트 |축  | &#x2714; (팀) |&#x2714; (스트림, 스트림 Embed를 통한 팀) |
|생산자 UI의 참석자 수 |축  |&#x2714; (팀) |&#x2714; (스트림, 스트림 Embed를 통한 팀) |
|여러 발표자 허용 |&#x2714; (비즈니스용 Skype) |&#x2714; (팀) |해당 없음  |
|모임 중에 발표자 초대 |&#x2714; (비즈니스용 Skype) |축 |해당 없음 |
|웹 및 모바일의 발표자 참가 |&#x2714; (비즈니스용 Skype)  |축 |해당 없음 |
|페더레이션된 & 게스트 발표자/참석자 |&#x2714; (비즈니스용 Skype)  | (출시 예정) |해당 없음 |
|발표자 – PSTN 액세스 |축 |&#x2714; (팀) |해당 없음 |
|화면 프레젠테이션 |축 |&#x2714; (팀) |해당 없음 |
|PowerPoint 프레젠테이션 (PPT 공유) |&#x2714; |X (화면 공유를 통해 완화) |해당 없음 |
|클라우드 기반 모임 기록 |&#x2714; |&#x2714; |&#x2714; |
|자동으로 스트림에 기록 게시 |축 |축 |&#x2714; |
|라이브 캡션과 자막 |&#x2714; |&#x2714; |축 |
|라이브 이벤트 기록의 캡션 |&#x2714; |&#x2714; |&#x2714; |
|참석자 DVR 컨트롤 (일시 중지, 되감기) |&#x2714; |&#x2714; |&#x2714; |
|파트너 eCDN 지원 |&#x2714; (Hive, Kollective, 램프) |&#x2714; (Hive, Kollective, 램프) |&#x2714; (Hive, Kollective, 램프) |
|생산자에 대 한 사후 브로드캐스트 모임 보고서 |&#x2714; |&#x2714; |축 |
|대상 그룹 정서 분석 – 실시간 투표 설문 & 폴링 |&#x2714; (Microsoft 펄스) |축 |축 |

> [!IMPORTANT]
> 설정 된 한도가 변경 될 수 있습니다.

## <a name="regional-availability"></a>지역 가용성
전세계 여러 지역에서 팀의 실시간 이벤트를 사용할 수 있습니다. 다음 정보는 이벤트 팀 구성원 및 참석자의 가용성을 보여줍니다. 

> [!IMPORTANT]
> 구성 및 Office 365 조직에 따라 이벤트의 영역이 자동으로 선택 됩니다.

**이 지역에서 사용 가능**
- 아메리카
- 유럽/아프리카
- 아시아 태평양
- 현지 캐나다로 이동

**제외 및 고려 사항**
- **지역으로 이동:** 영국, 인도, 오스트레일리아, 일본 및 기타 팀 지역 Go는 현재 지원 되지 않습니다.
- **중국:** 중국에서는 Azure CDN에 액세스할 수 없으므로 이벤트 팀 구성원 및 참석자가 팀의 라이브 이벤트를 사용 하지 못할 수도 있습니다. 해결 방법은 고객의 회사 네트워크를 통해 CDN에 연결 된 클라이언트를 가져오는 회사 VPN 연결을 사용 하는 것입니다.

## <a name="next-steps"></a>다음 단계
[팀의 라이브 이벤트 설정](set-up-for-teams-live-events.md)으로 이동 합니다.

### <a name="related-topics"></a>관련 항목
- [팀 라이브 이벤트는 무엇 인가요?](what-are-teams-live-events.md)
- [팀에 대 한 라이브 이벤트 설정](set-up-for-teams-live-events.md)
- [팀에서 라이브 이벤트 설정 구성](configure-teams-live-events.md)

