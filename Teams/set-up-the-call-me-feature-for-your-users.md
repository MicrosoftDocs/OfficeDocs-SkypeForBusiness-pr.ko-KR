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
description: 사용자가 자신의 컴퓨터를 오디오에 사용할 때 오디오 부분에 참가할 수 없는 경우 전화로 오디오 부분에 참가할 수 있도록 Teams에서 통화 기능을 설정하는 방법을 배워야 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821098"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>사용자의 전화 받기 기능 설정

Microsoft Teams에서  통화 기능을 사용하면 전화로 모임의 오디오 부분에 참가할 수 있습니다. 이 시나리오는 오디오에 컴퓨터를 사용할 수 없는 경우 유용합니다. 사용자는 다른 모임 참가자가 자신의 화면을 공유하거나 자신의 컴퓨터를 통해 비디오를 재생하는 경우와 같이 휴대폰이나 유선 전화 및 모임의 콘텐츠 부분을 통해 모임의 오디오 부분을 &mdash; &mdash; 얻습니다.

> [!IMPORTANT]
> 
> COVID-19 발생과 관련하여 경험한 대로 모임이 많은 기간에는 PSTN 회의 번호 또는 <strong>전화 번호</strong>를 사용해 전화를 거는 대신 <strong>Teams 모임 참가</strong> 버튼을 눌러 모임에 참석하는 것이 좋습니다. 이러면 모임이 증가하여 PSTN 네트워크가 정체되는 시기에 오디오 품질을 유지할 수 있습니다. 

> [!IMPORTANT]
> COVID-19 발생 기간에는 PSTN 회의 번호 또는 **전화 번호**</strong>를 사용해 전화를 거는 대신 **Teams 모임 참가** 버튼을 눌러 모임에 참석하는 것이 좋습니다. 이는 주로 COVID-19의 영향을 받는 국가의 전화 통신 인프라의 혼잡 때문입니다. PSTN 통화를 피하면 오디오 품질이 향상될 수 있습니다. 

## <a name="the-user-experience"></a>사용자 환경

### <a name="join-a-meeting-by-using-phone-for-audio"></a>오디오에 휴대폰을 사용하여 모임 참가

**참가를** 클릭하여 모임에 참가한  다음 오디오 및 비디오 설정 선택 화면에서 전화 **오디오를** 클릭합니다. 여기에서 사용자는 모임 전화를 걸고 모임에 참가하거나 모임에 수동으로 전화를 걸 수 있습니다.

![전화 오디오 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Teams 모임 전화 걸기**

오디오 **화면용 전화** 사용 화면에서 사용자가 자신의 전화 번호를 입력한 다음 통화를 **클릭합니다.** 모임에서 사용자에게 전화를 걸고 모임에 참가합니다.

![오디오 화면용 전화 사용의 전화 번호 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**수동으로 전화 접속**

참가하는 또 다른 방법은 모임에 직접 전화 접속하는 것입니다. 오디오 **화면에서 전화** 접속을  수동으로 클릭하여 모임에 전화 접속하는 데 사용할 전화 번호 목록을 표시합니다.

![수동 전화 접속 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>모임 중에 오디오에 문제가 있는 경우 다시 전화 걸기

사용자가 모임 중에 컴퓨터를 사용할 때 오디오 문제가 있는 경우 사용자는 오디오에 휴대폰을 사용하여 쉽게 전환할 수 있습니다. Teams는 오디오 또는 장치 문제가 발생하는 경우를 감지하고 전화 걸기 옵션을 표시하여 사용자가 자신의 휴대폰을 사용할 수 있도록 **리디렉션합니다.**

다음은 Teams에서 마이크를 감지하지  못하면 표시되는 메시지 및 전화 걸기 옵션의 예입니다.

![전화 걸기 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

사용자가 전화 걸기 **기능을 다시** 클릭하면 오디오 화면용 **휴대폰이** 나타납니다. 여기에서 전화 번호를 입력하고 Teams 모임에 전화를 걸고 모임에 참가하거나 수동으로 모임에 전화 접속할 수 있습니다.

## <a name="set-up-the-call-me-feature"></a>전화 걸기 기능 설정

조직의 사용자에 대해 전화 걸기 기능을 사용하도록 설정하려면 다음을 구성해야 합니다.

- 모임(모임 이끌이)을 예약하는 조직의 사용자가 오디오 회의를 사용할 수 있습니다. 자세한 내용은 [Teams에](set-up-audio-conferencing-in-teams.md) 대한 오디오 회의 설정 및 Teams에서 사용자의 오디오 회의 설정 [관리를 참조하세요.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 사용자는 모임에서 전화를 걸 수 있습니다. 자세한 내용은 Teams에서 사용자의 오디오 회의 설정 관리를 [참조하세요.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

사용자가 활성화된 모임에서 전화 접속을 하지  않은 경우 전화 걸기 옵션을 사용할 수 없습니다. 사용자는 모임에 참가하기 위한 전화를 받지 못합니다. 대신 오디오 화면의 사용 전화기에서 전화  번호 목록을 볼 수 있습니다. 이 목록은 전화기에서 모임에 수동으로 전화를 걸 때 사용할 수 있습니다.
