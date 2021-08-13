---
title: 사용자의 전화 받기 기능 설정
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 오디오를 위해 컴퓨터를 사용할 때 사용자가 전화로 오디오 부분을 조인할 수 있도록 Teams 전화로 통화 기능을 설정하는 방법에 대해 알아보십시오.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 972368de75f38ef1ad1d3f268bfa21526eda261658792b67ce8b0d51c3281b2e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324817"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>사용자의 전화 받기 기능 설정

Microsoft Teams 통화 기능은 사용자가  전화로 모임의 오디오 부분에 참가할 수 있는 방법을 제공합니다. 오디오에 컴퓨터를 사용할 수 없는 경우 시나리오에서 유용합니다. 사용자는 다른 모임 참가자가 자신의 화면을 공유하거나 컴퓨터를 통해 비디오를 재생하는 경우와 같이 휴대폰 또는 대지 회선 및 모임의 콘텐츠 부분을 통해 모임의 오디오 부분을 &mdash; &mdash; 얻습니다.

> [!IMPORTANT]
> 
> COVID-19 발생과 관련하여 경험한 대로 모임이 많은 기간에는 PSTN 회의 번호 또는 <strong>전화 번호</strong>를 사용해 전화를 거는 대신 <strong>Teams 모임 참가</strong> 버튼을 눌러 모임에 참석하는 것이 좋습니다. 이러면 모임이 증가하여 PSTN 네트워크가 정체되는 시기에 오디오 품질을 유지할 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>사용자 환경

### <a name="join-a-meeting-by-using-phone-for-audio"></a>오디오에 휴대폰을 사용하여 모임 참가

**참가를** 클릭하여 모임에 참가한 다음 전화  및 오디오 옵션 선택 **화면에서** 오디오를 표시하고 지금 **참가를 클릭합니다.** 여기에서 사용자는 모임 통화를 하게 하여 모임에 참가하거나 모임에 수동으로 전화 접속할 수 있습니다.

![오디오 옵션의 전화 스크린샷](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**모임 Teams 수 있습니다.**

오디오용 **휴대폰** 사용 화면에서 사용자가 자신의 전화 번호를 입력한 다음 나를 호출 **을 클릭합니다.** 모임에서 사용자를 호출하고 모임에 참가합니다.

![오디오 화면용 휴대폰 사용에서 전화 걸기 옵션의 스크린샷](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**수동으로 전화 접속**

참가하는 또 다른 방법은 모임에 직접 전화 접속하는 것입니다. 오디오용 **휴대폰** 사용 화면에서  수동으로 전화 접속을 클릭하여 모임에 전화 접속하는 데 사용할 전화 번호 목록을 얻습니다.

![수동으로 다이얼 옵션의 스크린샷](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>모임 중에 오디오에 문제가 있는 경우 다시 전화 걸기

사용자가 모임 중에 컴퓨터를 사용할 때 오디오 문제가 있는 경우 사용자는 오디오에 휴대폰을 사용하여 쉽게 전환할 수 있습니다. Teams 또는 디바이스 문제가 발생하는 경우를 감지하고 전화 걸기 옵션을 표시하여 사용자가 휴대폰을 사용할 수 있도록 **리디렉션합니다.**

다음은 마이크를 감지하지 못하면  표시되는 메시지 및 전화 Teams 예입니다.

![전화 걸기 옵션의 스크린샷](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

사용자가 다시 전화 걸기 를 **클릭하면** 오디오 화면에 휴대폰 **사용이** 나타납니다. 여기에서 전화 번호를 입력하고 모임에 Teams 모임에 참가하거나 모임에 수동으로 전화 접속할 수 있습니다.

## <a name="set-up-the-call-me-feature"></a>전화 걸기 기능 설정

조직의 사용자에 대해 전화 걸기 기능을 사용하도록 설정하려면 다음을 구성해야 합니다.

- 모임(모임 이끌이)을 예약하는 조직의 사용자가 오디오 회의를 사용할 수 있습니다. 자세한 내용은 [에서](set-up-audio-conferencing-in-teams.md) 사용자에 대한 오디오 회의 설정 및 Teams 사용자에 대한 오디오 회의 설정 관리를 [Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 모임 이끌이는 모임에서 전화 접속할 수 있습니다. 자세한 내용은 의 사용자에 대한 오디오 회의 [설정 관리를 Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

모임 이끌이가 모임에서 전화 접속을 사용하도록 **설정하지 않은** 경우 비디오  및 전화 선택 화면의 오디오 옵션을 다른 사용자가 사용할 수 없습니다. 다른 사용자가 모임에 참가할 전화를 받을 수 없습니다. 전화 접속을 사용하도록 설정한 사용자의 경우 모임에 참가한 후 참가자 표시 아이콘에서 자신의 번호로 전화를 걸 수 있는 다른 사용자와 조인할 **수** 있습니다.
