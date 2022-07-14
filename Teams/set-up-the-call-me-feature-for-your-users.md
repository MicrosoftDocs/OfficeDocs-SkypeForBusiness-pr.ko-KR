---
title: 사용자의 전화 받기 기능 설정
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 오디오에 컴퓨터를 사용할 때 사용자가 전화로 오디오 부분을 조인할 수 없도록 Teams에서 통화 기능을 설정하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794536"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>사용자의 전화 받기 기능 설정

Microsoft Teams에서 **통화** 기능은 사용자에게 전화로 모임의 오디오 부분에 참가할 수 있는 방법을 제공합니다. 이는 오디오용 컴퓨터를 사용할 수 없는 경우 시나리오에서 유용합니다. 사용자는 휴대폰 또는 유선으로 모임의 오디오 부분과 다른 모임 참가자가 화면을 공유하거나 컴퓨터를 통해 비디오를&mdash;재생하는 경우와 같은 모임&mdash;의 콘텐츠 부분을 받습니다.

> [!IMPORTANT]
> 
> COVID-19 발생과 관련하여 경험한 대로 모임이 많은 기간에는 PSTN 회의 번호 또는 <strong>전화 번호</strong>를 사용해 전화를 거는 대신 <strong>Teams 모임 참가</strong> 버튼을 눌러 모임에 참석하는 것이 좋습니다. 이러면 모임이 증가하여 PSTN 네트워크가 정체되는 시기에 오디오 품질을 유지할 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>사용자 환경

### <a name="join-a-meeting-by-using-phone-for-audio"></a>오디오에 휴대폰을 사용하여 모임 참가

**참가** 를 클릭하여 모임에 참가한 다음 **비디오 및 오디오 옵션 선택** 화면에서 **전화 오디오** 를 클릭한 다음 **지금 참가** 를 클릭합니다. 여기에서 사용자는 모임 전화를 받고 모임에 참가하거나 모임에 수동으로 전화를 걸 수 있습니다.

![휴대폰 오디오 옵션의 스크린샷.](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Teams 모임 전화 걸기**

오디오 화면에 **휴대폰 사용** 화면에서 사용자가 전화 번호를 입력한 다음 **전화 걸** 기를 클릭합니다. 모임에서 사용자를 호출하고 모임에 참가합니다.

![오디오 화면에 휴대폰 사용 옵션의 스크린샷.](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**수동으로 전화 걸기**

참가하는 또 다른 방법은 모임에 직접 전화하는 것입니다. 오디오에 **휴대폰 사용** 화면에서 **수동으로 전화 접속** 을 클릭하여 모임에 전화를 걸 때 사용할 전화 번호 목록을 가져옵니다.

![수동으로 다이얼의 스크린샷 옵션.](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>모임 중에 오디오에 문제가 발생하면 다시 전화 걸기

모임 중에 컴퓨터를 사용할 때 오디오 문제가 발생하는 경우 사용자는 휴대폰을 오디오로 쉽게 전환할 수 있습니다. Teams는 오디오 또는 장치 문제가 발생하는 경우를 감지하고 **전화 걸** 기 옵션을 표시하여 사용자가 휴대폰을 사용하도록 리디렉션합니다.

다음은 Teams에서 마이크를 감지하지 않을 때 표시되는 메시지 및 **다시 전화 걸** 기 옵션의 예입니다.

![다시 전화 걸기 옵션의 스크린샷.](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

사용자가 **다시 전화 걸** 기를 클릭하면 **오디오 화면에 휴대폰 사용** 이 표시됩니다. 여기에서 전화 번호를 입력하고 Teams 모임 전화를 받고 모임에 참가하거나 모임에 수동으로 전화를 걸 수 있습니다.

## <a name="set-up-the-call-me-feature"></a>통화 기능 설정

조직의 사용자에 대해 통화 기능을 사용하도록 설정하려면 다음을 구성해야 합니다.

- 모임(모임 이끌이)을 예약하는 조직의 사용자에 대해 오디오 회의를 사용할 수 있습니다. 자세한 내용은 [Teams에 대한 오디오 회의 설정 및 Teams](set-up-audio-conferencing-in-teams.md) [사용자에 대한 오디오 회의 설정 관리를 참조하세요](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- 모임 이끌이는 모임에서 전화를 걸 수 있습니다. 자세한 내용은 [Teams에서 사용자에 대한 오디오 회의 설정 관리를 참조하세요](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

모임 이끌이가 모임에서 전화 접속을 사용하도록 설정하지 않은 경우 **비디오 및 오디오 옵션 선택** 화면의 **전화 오디오** 옵션을 사용할 수 없으며 다른 사용자는 모임에 참가하기 위한 전화를 받을 수 없습니다. 전화 접속이 활성화된 사용자의 경우 모임에 참가한 후에는 **참가자 표시** 아이콘에서 자신의 번호로 전화를 걸어 다른 사용자와 참가할 수 있습니다.
