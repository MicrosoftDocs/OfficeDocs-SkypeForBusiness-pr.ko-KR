---
title: 사용자에 게 전화 걸기 기능 설정
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 사용자가 오디오에 대 한 컴퓨터를 사용할 수 없는 경우에 휴대폰으로 오디오 부분에 참가할 수 있도록 팀에서 전화 걸기 기능을 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54e9d90a3380358abd0c1e984b90834455eb44e2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243176"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>사용자에 게 전화 걸기 기능 설정

Microsoft 팀에서 전화 **걸기** 기능을 통해 사용자는 휴대폰으로 모임의 오디오 부분에 참가할 수 있습니다. 이 방법은 오디오를 사용 하는 것이 불가능할 수 있는 시나리오에서 유용 합니다. 사용자는 휴대폰 또는 육지 모임의 오디오 부분을 받고 다른 모임 참가자가 화면을 공유 하거나 컴퓨터를 통해 비디오&mdash;&mdash;를 재생할 때 모임의 콘텐츠 부분을 사용할 수 있습니다.

## <a name="the-user-experience"></a>사용자 환경

### <a name="join-a-meeting-by-using-phone-for-audio"></a>오디오 용 전화를 사용 하 여 모임 참가

**참가** 를 클릭 하 여 모임에 참가 한 다음 **오디오 및 비디오 설정 선택** 화면에서 **전화 오디오** 를 클릭 합니다. 여기서는 사용자가 모임 통화를 진행 하 고 참가 하거나 수동으로 모임에 전화를 걸 수 있습니다.

![전화 오디오 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**팀 모임 통화 허용**

**오디오 용 전화 사용** 화면에서 사용자가 전화 번호를 입력 한 다음 전화를 클릭 합니다 ****. 모임이 사용자에 게 전화를 걸고 모임에 참가 합니다.

![오디오 사용 화면의 전화 걸기 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**수동으로 전화 접속**

참가 하는 또 다른 방법은 모임에 직접 전화 접속 하는 것입니다. **오디오 용 전화 사용** 화면에서 **수동으로 전화 접속** 을 클릭 하 여 모임에 전화를 걸 때 사용할 전화 번호 목록을 가져옵니다.

![수동으로 전화 접속 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>모임 중 오디오에 문제가 있는 경우 다시 전화 받기

사용자가 모임 중에 컴퓨터를 사용할 때 오디오 문제가 발생 하는 경우 사용자는 오디오를 사용 하 여 쉽게 전환할 수 있습니다. 팀은 오디오 또는 장치 문제가 발생 하는 경우를 감지 하 고 사용자에 게 콜백 옵션을 **** 표시 하 여 전화를 사용 하도록 리디렉션합니다.

다음은 팀에서 마이크를 감지 하지 못하는 **** 경우 표시 되는 메시지 및 콜백 옵션의 예입니다.

![콜백 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

사용자가 **오디오를 사용** 하는 것을 전화 걸기 화면을 표시 하는 **me 뒤로**를 클릭 합니다. 여기서는 전화 번호를 입력 하 고 팀이 통화를 하 여 모임에 참가 하거나 수동으로 모임에 전화를 걸 수 있습니다.

## <a name="set-up-the-call-me-feature"></a>전화 걸기 기능 설정

조직의 사용자에 게 전화 걸기 기능을 사용 하도록 설정 하려면 다음을 구성 해야 합니다.

- 모임을 예약 하는 조직의 사용자 (모임 이끌이)는 오디오 회의를 사용할 수 있습니다. 자세한 내용은 팀 [에 대 한 오디오 회의 설정](set-up-audio-conferencing-in-teams.md) 및 [팀에서 사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)를 참조 하세요.

- 사용자가 모임에서 전화를 걸 수 있습니다. 자세히 알아보려면 [팀에서 사용자에 대 한 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)를 참조 하세요.

사용자가 모임에서 전화를 걸지 않은 경우 **call me** 옵션을 사용할 수 없으며 사용자가 모임에 참가 하는 전화를 받지 않습니다. 대신 사용자는 휴대폰에서 직접 전화 접속 하는 데 사용할 수 있는 **오디오 사용** 화면의 전화 번호 목록을 표시 합니다.
