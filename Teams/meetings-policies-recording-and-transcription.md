---
title: 녹음/녹화를 위한 모임 정책 관리
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: 기록 및 전사를 위해 Teams에서 모임 정책 설정을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 12f8be910c713a9ce023ac17c956ef50f5889792
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268983"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>& 기록 기록을 위한 모임 정책 설정

이 문서에서는 다음을 포함하여 녹음/녹화와 관련된 모임 정책 설정에 대해 설명합니다.

- [기록 허용](#allow-transcription)
- [클라우드 녹음/녹화 허용](#allow-cloud-recording)
- [국가 또는 지역 외부에 녹음/녹화 저장](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>기록 허용

이는 이끌이별 및 사용자별 정책의 조합입니다. 이 설정은 모임 녹음/녹화 재생 중에 캡션 및 전사 기능을 사용할 수 있는지 여부를 제어합니다. 녹음/녹화를 시작한 사람은 이러한 기능이 레코딩에서 작동하려면 이 설정을 켜야 합니다.

이 설정을 켜면 모임 기록에서 **검색**, **참조** 및 **대본** 을 사용하는 모임 기록과 함께 저장된 대본의 사본이 생성됩니다.

기록된 모임에 대한 전사는 현재 Teams 모임에서 영어로 언어를 설정하거나 영어를 사용하는 사용자에 대해서만 지원됩니다.

## <a name="allow-cloud-recording"></a>클라우드 녹음/녹화 허용

이 설정은 이끌이별 및 사용자별 정책의 조합이며 모임을 기록할 수 있는지 여부를 제어합니다. 참가자에 대한 정책 설정이 켜져 있고 동일한 조직의 인증된 사용자인 경우 모임 이끌이 또는 다른 모임 참가자가 녹음/녹화를 시작할 수 있습니다.

페더레이션 사용자 및 익명 사용자와 같은 조직 외부의 사용자는 녹음/녹화를 시작할 수 없습니다. 게스트 사용자는 녹음/녹화를 시작하거나 중지할 수 없습니다.

![녹음/녹화 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

다음 예를 살펴봅시다.

|사용자 |모임 정책  |클라우드 녹음/녹화 허용 |
|---------|---------|---------|
|Daniela | 전역   | 해제 |
|Amanda | Location1MeetingPolicy | 설정|
|John(외부 사용자) | 해당 사항 없음 | 해당 사항 없음|

- Daniela가 조직한 모임은 녹음/녹화할 수 없습니다.
- 아만다는 다니엘라가 주최한 모임을 녹음할 수 없습니다.
- Amanda가 조직한 모임을 녹음할 수 있습니다.
- 다니엘라는 아만다가 주최한 모임을 녹음할 수 없습니다.
- 요한은 아만다가 주최한 모임을 녹음할 수 없다.

클라우드 모임 녹음/녹화에 대해 자세히 알아보려면 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.

## <a name="store-recordings-outside-of-your-country-or-region"></a>국가 또는 지역 외부에 녹음/녹화 저장

이 정책은 모임 레코드를 다른 국가 또는 지역에 영구적으로 저장할 수 있는지 여부를 제어합니다. 이 기능을 사용하도록 설정하면 기록을 마이그레이션할 수 없습니다. 클라우드 모임 및 녹음/녹화가 저장되는 위치에 대한 자세한 내용은 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.

## <a name="related-topics"></a>관련 항목

- [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
- [클라우드 모임 녹음/녹화](cloud-recording.md)
- [Microsoft Teams의 모임 정책 및 모임 만료](meeting-expiration.md)
