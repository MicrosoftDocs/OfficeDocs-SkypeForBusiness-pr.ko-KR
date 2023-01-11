---
title: Microsoft Teams의 라이브 이벤트 계획하기
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams에서 라이브 이벤트를 설정하기 전에 고려해야 하는 요소에 대해 설명합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cde485a3cf290c105ae475e6f7733787ba6971a2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767609"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Microsoft Teams의 라이브 이벤트 계획하기

조직에서 대규모 모임을 개최하기 위해 Teams 라이브 이벤트를 계획하는 경우, 설정하기 전에 고려해야 할 몇 가지 요소가 있습니다.

> [!NOTE]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>누가 라이브 이벤트를 참석하고 만들고 예약할 수 있나요?

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

사용자가 Teams 라이브 이벤트를 예약하려면 다음과 같은 필수 구성 요소가 있어야 합니다.

Teams 라이브 이벤트를 구성, 제작 또는 발표하기 위해 할당해야 하는 라이선스는 다음과 같습니다.  

- **구성 방법:** Microsoft 또는 Office 365 Enterprise E1, E3 또는 E5 라이선스 **[또는]** Microsoft 또는 Office 365 Education A3 또는 A5 라이선스.
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Microsoft Teams 라이선스 - 첫 번째 및 두 번째 글머리 기호에 나열된 라이선스에 포함됩니다.

> [!NOTE]
> 현재로서는 Teams 라이브 이벤트를 만들고 보유하는 데 사용할 수 있는 Microsoft 365 Small Business 요금제가 없습니다.

인증된 사용자로서 라이브 이벤트에 참여하려면 Microsoft 365 또는 Office 365 라이선스가 필요하다는 것을 알고 있어야 하지만 이 요구 사항은 사용되는 프로덕션 방법에 따라 다릅니다.

- **Teams에서 생성되거나 Teams 전원 인코더를 사용하는 이벤트의 경우**  사용자에게 Teams 라이선스가 할당되어야 합니다.

> [!NOTE]
> 이제 Teams 라이브 이벤트는 GCC(미국 정부 클라우드 커뮤니티) 조직에서 사용할 수 있습니다.

라이선싱에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조하세요.

사용자에게 다음이 필요합니다.

- Teams에서 비공개 모임 예약 활성화(*TeamsMeetingPolicy -AllowPrivateMeetingScheduling 매개 변수 = True*)
- Teams 모임에서 비디오 공유 기능 활성화(*TeamsMeetingPolicy -AllowIPVideo 매개 변수 = True*).
- Teams 모임에서 화면 공유 기능 활성화(*TeamsMeetingPolicy -ScreenSharingMode 매개 변수 = EntireScreen*).
- Teams에서 라이브 이벤트 예약 활성화(*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling 매개 변수 = True*)
- 팀 모임(*아일랜드, 모임 먼저 또는 Teams 전용*)를 예약할 수 있는 공존 모드가 구성되었습니다.

> [!IMPORTANT]
> 인증되지 않은 익명 사용자는 Teams 라이브 이벤트에 제작자 또는 발표자로 초대를 받을 수 없습니다.

### <a name="guest-to-present"></a>[게스트 프레젠테이션](#guest-to-present)

게스트가 라이브 이벤트에서 프레젠테이션을 하려면 다음을 수행합니다.

1. [사용자를 팀에 게스트로 추가합니다](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. 사용자가 게스트 초대를 수락하고 팀에 참가하도록 합니다.
3. [라이브 이벤트를 예약하고 게스트를 이벤트 그룹에 추가합니다](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## <a name="who-can-watch-live-events"></a>누가 라이브 이벤트를 볼 수 있나요?

| 참석자 표시 유형 | Teams 프로덕션 | 외부 앱 또는 장치 프로덕션 | Teams 전원 인코더
|------------------------------|-----------------|----------------------|----------------|
|공개(익명 사용자)      |  예            |  아니요                  | 예
|게스트 사용자                   |  예<sup>1</sup>            |  아니요                  |  예            |
|외부 액세스(페더레이션) 회사의 모든 사용자 |  예<sup>1</sup>|  아니요                  | 예            |
|회사의 모든 사용자           |  예            |  예                 | 예                |
|특정 그룹/사용자      |  예            |  예                 | 예                |

<sup>1</sup> 사용자 및 그룹을 통해서만 초대받을 수 있습니다. <br>

## <a name="teams-live-events"></a>Teams 라이브 이벤트

다음 표에서는 라이브 이벤트에서 제공되는 핵심 기능 및 기능을 강조 표시합니다.

> [!IMPORTANT]
> **Microsoft 365 라이브 이벤트 한도 증가**
>
> **고객의 요구 사항을 계속 지원하기 위해 다음을 포함하여 2023년 6월 30일까지 라이브 이벤트에 대한 임시 제한 증가를 연장합니다.**
>
>- 최대 20,000명의 참석자를 위한 이벤트 지원
>- 한 테넌트에 걸쳐 동시에 50개의 이벤트가 호스트될 수 있습니다.
>- 브로드캐스트당 16시간의 이벤트 시간
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

| 기능 | Teams에서 생성된 이벤트 | 외부 앱 또는 장치에서 생성된 이벤트 |
|---------|---------|---------|
|대상 그룹 최대 크기 |10,000명의 참석자<sup>1</sup> |10,000명의 참석자<sup>1</sup> |
|라이브 이벤트 최대 시간 |4시간 |4시간 |
|라이브 이벤트에서 발표자 및 프로듀서의 최대 수 |10 <sup>2</sup> |10 <sup>2</sup> |
|Microsoft 365 또는 Office 365 조직당 최대 동시 발생 라이브 이벤트 수 | 15  | 15  |
|라이브 이벤트 만들기 |Teams, Teams를 통한 Yammer | Teams, Teams를 통한 Yammer, Stream |
|대상 그룹 참여 – Yammer |&#x2714; (통합 환경) |&#x2714; (통합 환경) |
|대상 그룹 참여 – 중재된 Q&A |&#x2714; |&#x2714; |
|Windows의 프로듀서 클라이언트 |&#x2714;(Teams) |&#x2714;(Stream, Stream Embed를 통한 Teams) |
|Mac의 프로듀서 클라이언트 |&#x2714;(Teams) |&#x2714;(Stream, Stream Embed를 통한 Teams) |
|프로듀서 UI의 참석자 수 |&#x2714;(Teams) |&#x2714;(Stream, Stream Embed를 통한 Teams) |
|여러 발표자 허용 |&#x2714;(Teams) |해당 없음  |
|모임 중에 발표자 초대 |&#x274C; |해당 없음 |
|웹과 모바일의 발표자 참여 |&#x274C; |해당 없음 |
|외부 액세스(페더레이션) 및 게스트 발표자/참석자 |&#x2714;(Teams) |해당 없음 |
|발표자 – PSTN 액세스 |&#x2714;(Teams) |해당 없음 |
|화면 발표 |&#x2714;(Teams) |해당 없음 |
|Windows에서 시스템 오디오 공유(화면 공유 시에만 사용 가능)|&#x2714;(Teams) |&#x2714; |
|PowerPoint 발표(PPT 공유) |&#x274C; (화면 공유를 통해 완화됨) |해당 없음 |
|클라우드 기반 모임 녹음/녹화 |&#x2714; |&#x2714; |
|자동으로 Stream에 녹음/녹화 게시 |&#x274C; |&#x2714; |
|라이브 캡션 및 자막 |&#x2714; |&#x274C; |
|라이브 이벤트 녹음/녹화의 캡션 |&#x2714; |&#x2714; |
|참석자 DVR 컨트롤(일시 중지, 되감기) |&#x2714; |&#x2714; |
|Microsoft eCDN |&#x2714; |&#x2714; |
|파트너 eCDN 지원 |&#x2714;(Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|프로듀서용 브로드캐스트 후 참석 보고서 |&#x2714; |&#x274C; |
|대상 그룹 감정 분석 – 실시간 투표 및 설문 조사 |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> 라이브 이벤트에는 최대 100명의 발표자와 프로듀서가 있을 수 있지만, 마지막 10명만 목록에 나타납니다.

## <a name="regional-availability"></a>국가별 가용성

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> 이벤트 지역은 이끌이와 Microsoft 365 테넌트 위치에 따라 자동으로 선택됩니다.

**다음 지역에서 사용 가능합니다.**

- 북미
- 중미
- 남미
- 아시아 태평양
- 유럽/아프리카

**이들 국가/지역의 데이터 위치(지원)**

- 오스트레일리아
- 브라질
- 캐나다
- 프랑스
- 독일
- 인도
- 일본
- 노르웨이
- 싱가포르
- 남아프리카 공화국
- 대한민국
- 스위스
- UAE
- 영국

**제외 사항 및 고려 사항**

- **데이터 위치:** 위에 나열된 지역 이외의 Teams 데이터 위치는 현재 지원되지 않습니다.

## <a name="next-steps"></a>다음 단계

[Teams 라이브 이벤트 설정](set-up-for-teams-live-events.md)으로 이동하세요.

### <a name="related-topics"></a>관련 항목

- [Teams 라이브 이벤트란?](what-are-teams-live-events.md)
- [Teams 라이브 이벤트 설정하기](set-up-for-teams-live-events.md)
- [Teams에서 라이브 이벤트 설정 구성하기](configure-teams-live-events.md)
