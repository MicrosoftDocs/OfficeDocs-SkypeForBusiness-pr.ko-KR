---
title: Microsoft Teams의 라이브 이벤트 계획하기
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams에서 라이브 이벤트를 설정하기 전에 고려해야 하는 요소에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95baeaf25600853b7d6a2b4e18c548d1998f6789
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102369"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Microsoft Teams의 라이브 이벤트 계획하기

조직에서 대규모 모임을 개최하기 위해 Teams 라이브 이벤트를 계획하는 경우 모두 설정하기 전에 고려해야 할 몇 가지 요소가 있습니다. 

## <a name="who-can-create-and-schedule-live-events"></a>누가 라이브 이벤트를 만들고 예약할 수 있나요? 
사용자가 Teams 라이브 이벤트를 예약하려면 다음과 같은 필수 구성 요소가 있어야 합니다.

다음과 같은 라이선스가 할당되어야 합니다.  
- Office 365 Enterprise E1, E3 또는 E5 라이선스 또는 Office 365 A3 또는 A5 라이선스
- Microsoft Teams 라이선스
- Microsoft Stream 라이선스

> [!IMPORTANT]
> 라이브 이벤트를 만들고 예약하는 사용자에게는 Exchange Online 사서함이 있어야 합니다.

인증된 사용자로서 라이브 이벤트에 참여하려면 Office 365 라이선스가 필요하다는 것을 알고 있어야 하지만 이 요구 사항은 사용되는 프로덕션 방법에 따라 다릅니다.

- **Teams에서 생성된 이벤트의 경우** 사용자에게 Teams 라이선스가 할당되어야 합니다.
- **외부 앱 또는 장치를 사용하여 생성된 이벤트의 경우** 사용자에게 Stream 라이선스가 할당되어야 합니다.

> [!NOTE]
> 이제 Teams 라이브 이벤트는 GCC(미국 정부 클라우드 커뮤니티) 조직에서 사용할 수 있습니다.

라이선싱에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조하세요.

사용자에게 다음이 필요합니다.
- Teams에서 비공개 모임 예약 활성화(*TeamsMeetingPolicy -AllowPrivateMeetingScheduling 매개 변수 = True*)
- Teams 모임에서 비디오 공유 기능 활성화(*TeamsMeetingPolicy -AllowIPVideo 매개 변수 = True*).
- Teams 모임에서 화면 공유 기능 활성화(*TeamsMeetingPolicy -ScreenSharingMode 매개 변수 = EntireScreen*).
- Teams에서 라이브 이벤트 예약 활성화(*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling 매개 변수 = True*)
- Stream에서 라이브 이벤트를 만들 수 있는 사용 권한(외부 앱 또는 장치 프로덕션용)

> [!IMPORTANT]
> 인증되지 않은 익명 사용자는 Teams 라이브 이벤트에서 프로듀서 또는 발표자로 초대를 받을 수 없습니다. 
 
## <a name="who-can-watch-live-events"></a>누가 라이브 이벤트를 볼 수 있나요?

|**참석자 공개 여부**       |**Teams 프로덕션**  |**외부 앱 또는 장치 프로덕션**  |
|------------------------------|-----------------|----------------------|
|공개(익명 사용자)      |  예            |  아니요                  |
|게스트 사용자                   |  예            |  아니요                  |
|페더레이션된 회사의 모든 사용자 |  예<sup>1</sup>|  아니요                  |
|회사의 모든 사용자           |  예            |  예                 |
|특정 그룹/사용자      |  예            |  예                 |

<sup>1 개의</sup> 페더레이션 참석자는 사용자 & 그룹을 통해서만 초대할 수 있습니다. <br>


 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams 라이브 이벤트 및 Skype 모임 브로드캐스트

다음 표에는 라이브 이벤트에서 제공하는 핵심 기능과 특성 및 Skype 모임 브로드캐스트와의 차이점을 중점적으로 설명합니다. 

|**기능**   |**Skype 모임 브로드캐스트** |**Teams에서 생성된 이벤트** |**외부 앱 또는 장치에서 생성된 이벤트** |
|---------|---------|---------|---------|
|대상 그룹 최대 크기 |10,000명의 참석자 |10,000명의 참석자<sup>1</sup> |10,000명의 참석자<sup>1</sup> |
|라이브 이벤트 최대 시간 |4시간 |4시간 |4시간 |
|라이브 이벤트의 발표자 및 제작자 최대 수 |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Office 365 테넌트당 최대 동시 라이브 이벤트 수 |~  | ~  | ~  |
|라이브 이벤트 만들기 |   Skype 모임 브로드캐스트 포털 |Teams, Teams를 통한 Yammer | Teams, Teams를 통한 Yammer, Stream |
|대상 그룹 참여 – Yammer |&#x2714; |&#x2714; (통합 환경) |&#x2714; (통합 환경) |
|대상 그룹 참여 – 중재된 Q&A |&#x2714;  |&#x2714; |&#x2714; |
|Windows의 프로듀서 클라이언트 |&#x2714;(비즈니스용 Skype) |&#x2714;(Teams) |&#x2714;(Stream, Stream Embed를 통한 Teams) |
|Mac의 프로듀서 클라이언트 |&#x274C;  | &#x2714;(Teams) |&#x2714;(Stream, Stream Embed를 통한 Teams) |
|프로듀서 UI의 참석자 수 |&#x274C;  |&#x2714;(Teams) |&#x2714;(Stream, Stream Embed를 통한 Teams) |
|여러 발표자 허용 |&#x2714;(비즈니스용 Skype) |&#x2714;(Teams) |해당 없음  |
|모임 중에 발표자 초대 |&#x2714;(비즈니스용 Skype) |&#x274C; |해당 없음 |
|웹과 모바일의 발표자 참여 |&#x2714;(비즈니스용 Skype)  |&#x274C; |해당 없음 |
|페더레이션 및 게스트 발표자/참석자 |&#x2714;(비즈니스용 Skype)  |  &#x2714;(Teams) |해당 없음 |
|발표자 – PSTN 액세스 |&#x274C; |&#x2714;(Teams) |해당 없음 |
|화면 발표 |&#x274C; |&#x2714;(Teams) |해당 없음 |
|PowerPoint 발표(PPT 공유) |&#x2714; |&#x274C; (화면 공유를 통해 완화) |해당 없음 |
|클라우드 기반 모임 녹음/녹화 |&#x2714; |&#x2714; |&#x2714; |
|자동으로 Stream에 녹음/녹화 게시 |&#x274C; |&#x274C; |&#x2714; |
|라이브 캡션 및 자막 |&#x2714; |&#x2714; |&#x274C; |
|라이브 이벤트 녹음/녹화의 캡션 |&#x2714; |&#x2714; |&#x2714; |
|참석자 DVR 컨트롤(일시 중지, 되감기) |&#x2714; |&#x2714; |&#x2714; |
|파트너 eCDN 지원 |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|프로듀서용 브로드캐스트 후 참석 보고서 |&#x2714; |&#x2714; |&#x274C; |
|대상 그룹 감정 분석 – 실시간 투표 및 설문 조사 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> 설정된 제한이 변경되었을 수 있습니다. [팀에 대 한 제한 및 사양을](../limits-specifications-teams.md)확인 합니다.<br/>
<sup>2</sup> 라이브 이벤트에서 최대 250 명의 발표자와 제작자를 가질 수 있지만, 사용자는 스포크를 사용 하 여 목록에 표시 되는 최근 10 개 밖에 없습니다.


## <a name="regional-availability"></a>국가별 가용성
전 세계 여러 지역에서 Teams 라이브 이벤트를 사용할 수 있습니다. 다음 정보는 이벤트 팀 구성원과 참석자의 가용성을 보여 줍니다. 

> [!IMPORTANT]
> 이벤트 지역은 이끌이와 Office 365 조직에 따라 자동으로 선택됩니다.

**다음 지역에서 사용 가능**
- 아메리카
- 유럽/아프리카
- 아시아 태평양
- Go Local 캐나다, 인도, 호주, 일본, 영국

**제외 사항 및 고려 사항**
- **Go Local:** Teams Go Local은 현재 위에 나열된 지역 외에는 지원되지 않습니다.
- **중국:** 중국에서 Azure CDN에 액세스할 수 없으므로 팀 구성원 및 참석자는 Teams 라이브 이벤트를 사용할 수 없습니다. 해결 방법은 회사 VPN 연결을 사용하여 고객의 회사 네트워크를 통해 CDN에 클라이언트를 연결하는 것입니다.

## <a name="next-steps"></a>다음 단계
[Teams 라이브 이벤트 설정](set-up-for-teams-live-events.md)으로 이동하세요.

### <a name="related-topics"></a>관련 항목
- [Teams 라이브 이벤트란?](what-are-teams-live-events.md)
- [Teams 라이브 이벤트 설정하기](set-up-for-teams-live-events.md)
- [Teams에서 라이브 이벤트 설정 구성하기](configure-teams-live-events.md)

