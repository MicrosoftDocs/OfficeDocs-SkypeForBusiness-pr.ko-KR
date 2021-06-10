---
title: 사용자에 대한 모임 전화 접속 확인 설정 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 전화 통화에 응답할 수 Teams 음성 메일 시스템이 모임에 연결되지 않도록 전화 접속 확인을 요청하는 방법을 알아보습니다.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117096"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="980de-103">사용자에 대한 모임 전화 접속 확인을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="980de-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="980de-104">모임 전화 걸기 및 전화 통화는 참가자를 모임에 참가할 수 있는 초대하고 기존 참가자가 기존 또는 휴대폰을 사용하여 모임에 참가할 수 있는 매우 유용한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="980de-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="980de-105">그러나 호출된 사용자가 통화에 응답할 수 없는 경우 음성메일 시스템이 모임에 연결되고 참가자는 모임에서 제거될 때까지 수신 수신을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980de-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="980de-106">전화 번호로 모임 전화 걸기를 보내고 호출한 사람이 통화에 응답할 수 없는 경우 음성 메일 시스템이 모임에 연결되지 않도록 Teams 모임에 참가할 수 있는 호출된 사람의 확인을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980de-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="980de-107">호출된 사용자가 통화에 응답할 수 없는 경우 음성 메일 시스템에서 전화를 걸면 음성 메일 시스템이 모임에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="980de-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="980de-108">이 기능을 사용하도록 설정하면 전화 걸기 또는 전화 통화를 받는 사용자가 기존 또는 휴대폰에서 1을 눌러 모임에 참가할지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="980de-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="980de-109">조직의 모든 모임에 대해 이 기능을 사용하도록 설정하려면 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를 ```true``` 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="980de-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="980de-110">이렇게 하여 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="980de-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="980de-111">관련 항목</span><span class="sxs-lookup"><span data-stu-id="980de-111">Related topics</span></span>

- [<span data-ttu-id="980de-112">사용자의 전화 받기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="980de-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="980de-113">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="980de-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)