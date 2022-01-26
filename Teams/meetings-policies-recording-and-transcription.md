---
title: 기록 및 전사에 대한 모임 정책 관리
author: KarliStites
ms.author: kastites
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
description: 기록 및 전사에 대한 Teams 모임 정책 설정을 관리하는 방법을 학습합니다.
ms.openlocfilehash: ee558ae87d7bea781cae3d2bc267f82bc1fdb18a
ms.sourcegitcommit: faeb8976299375e7658499ff31d25e8ef6003144
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2022
ms.locfileid: "62224075"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>기록 기록을 위한 모임 & 설정

이 문서에서는 다음을 포함하여 기록 및 전사와 관련한 모임 정책 설정을 설명합니다.

- [기록 허용](#allow-transcription)
- [클라우드 녹음/녹화 허용](#allow-cloud-recording)
- [국가 또는 지역 외부의 녹음/녹화 저장](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>기록 허용

이끌이 및 사용자당 정책의 조합입니다. 이 설정은 모임 녹음/녹화 재생 중에 캡션 및 전사 기능을 사용할 수 있는지 여부를 제어합니다. 기록을 시작한 사람은 이러한 기능이 기록과 함께 작동하기 위해 이 설정을 켜야 합니다.

이 설정을 켜면 모임 기록에서 **검색,** **CC** 및 대본을 사용할 수 있는  모임 기록과 함께 저장된 녹취록의 복사본이 생성됩니다.

녹음된 모임에 대한 전사는 현재 해당 언어를 언어로 설정하거나 모임에서 영어를 Teams 지원됩니다.

## <a name="allow-cloud-recording"></a>클라우드 녹음/녹화 허용

이 설정은 이끌이 및 사용자당 정책의 조합으로 모임을 기록할 수 있는지 여부를 제어합니다. 참가자에 대한 정책 설정이 켜져 있으며 동일한 조직의 인증된 사용자인 경우 모임 이끌이 또는 다른 모임 참가자가 녹음을 시작할 수 있습니다.

페더레이션 사용자 및 익명 사용자와 같은 조직 외부의 사용자는 녹음/녹화를 시작할 수 없습니다. 게스트 사용자는 녹음/녹화를 시작하거나 중지할 수 없습니다.

![녹화 옵션을 보여주는 스크린샷](media/meeting-policies-recording.png)

다음 예를 살펴봅시다.

|사용자 |모임 정책  |클라우드 녹음/녹화 허용 |
|---------|---------|---------|
|Daniela | 전역   | 해제 |
|Amanda | Location1MeetingPolicy | 설정|
|John(외부 사용자) | 해당 사항 없음 | 해당 사항 없음|

- Daniela가 조직한 모임은 기록할 수 없습니다.
- Amanda는 다니엘라가 조직한 모임을 기록할 수 없습니다.
- Amanda에서 조직된 모임을 기록할 수 있습니다.
- Daniela는 Amanda에서 조직한 모임을 녹화할 수 없습니다.
- John은 Amanda에서 조직한 모임을 기록할 수 없습니다.

클라우드 모임 녹음/녹화에 대해 자세히 알아보려면 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.

## <a name="store-recordings-outside-of-your-country-or-region"></a>국가 또는 지역 외부의 녹음/녹화 저장

이 정책은 모임 레코드를 다른 국가 또는 지역에 영구적으로 저장할 수 있는지 여부를 제어합니다. 활성화되어 있는 경우 기록을 마이그레이션할 수 없습니다. 클라우드 모임 및 녹화가 저장되는 위치에 대한 자세한 내용은 클라우드 모임 Teams [참조하세요.](cloud-recording.md)

## <a name="related-topics"></a>관련 항목

- [사용자에 대한 정책 할당 Teams](policy-assignment-overview.md)
- [클라우드 모임 녹화](cloud-recording.md)
