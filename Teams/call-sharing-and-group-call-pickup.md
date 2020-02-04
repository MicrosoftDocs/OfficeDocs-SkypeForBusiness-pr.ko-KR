---
title: Microsoft 팀에서 공유 및 그룹 통화 걸기
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
ms.custom:
- Phone System
description: 통화 공유 및 그룹 통화 픽업 사용자는 사용자를 사용할 수 없는 경우 전화를 통해 들어오는 전화를 동료와 공유할 수 있습니다.
ms.openlocfilehash: a39ed0a606b38a159473fbab9c35d21ae461c34b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684121"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="64747-103">Microsoft 팀에서 공유 및 그룹 통화 걸기</span><span class="sxs-lookup"><span data-stu-id="64747-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="64747-104">Microsoft 팀의 통화 공유 및 그룹 통화 픽업 기능을 통해 사용자가 사용자를 사용할 수 없는 동안 발생 하는 전화를 받을 수 있도록 동료와의 수신 전화를 공유할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64747-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="64747-105">사용자가 들어오는 공유 통화에 대 한 알림을 받는 방법을 구성할 수 있으므로 (예: 착신 통화 전환 또는 동시 연결) 다른 형태의 통화 공유에 대 한 낮은 중단의 경우 그룹 통화 또는 배너에 응답 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64747-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="64747-106">다른 사용자와 통화를 공유 하려면 통화 그룹을 만들고 통화를 공유 하려는 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="64747-107">그런 다음 동시 링 또는 전달 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="64747-108">자세한 내용은 [팀의 착신 전환 및 동시](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64747-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64747-109">통화 그룹 소유자 및 통화 그룹의 구성원은 팀 전용 배포 모드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="64747-110">팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64747-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="64747-111">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="64747-111">License required</span></span>

<span data-ttu-id="64747-112">통화 공유 및 그룹 통화 픽업 설정 및 사용을 위해서는 사용자가 엔터프라이즈 음성 기능을 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="64747-113">라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 용 Office 365 라이선스](office-365-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64747-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="64747-114">그룹 통화 픽업 구성</span><span class="sxs-lookup"><span data-stu-id="64747-114">Configure group call pickup</span></span>

<span data-ttu-id="64747-115">그룹 통화 픽업을 설정 하려면 사용자가 먼저 통화 그룹 (보안 그룹 또는 Office 365 그룹과 동일 하지 않음)을 구성한 다음 통화를 공유할 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="64747-116">그런 다음 동시 링 또는 통화 전달 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="64747-117">자세한 내용 및 단계별 절차는 [팀의 착신 전환 및 동시](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64747-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="64747-118">통화 그룹 만들기 및 알림 기본 설정은 사용자 구동 기능입니다. 관리자는 사용자를 위해 이러한 기능을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64747-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="64747-119">보안 그룹 또는 Office 365 그룹에서 통화 그룹을 만들 수 없습니다. 팀에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="64747-120">관리자는 사용자에 대 한 **Teamscallingpolicy AllowCallGroups** 설정을 통해 통화 그룹을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="64747-121">관리자는 또한 팀 관리자 포털을 통해이를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64747-121">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="64747-122">또한 구성 된 사용자는 클라이언트를 통해 직접 호출 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64747-122">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="64747-123">관리자 또는 최종 사용자는 서로에 대 한 구성을 차단할 수 없지만, 팀 관리자 포털 및 팀 클라이언트는이 관계를 두 위치에 정확 하 게 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-123">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="64747-124">중요: 관리자가 사용자에 대 한 통화 그룹을 끄면 (켜져 있고, 통화 그룹 관계가 구성 된 후) 관리자는 팀 관리 센터의 사용자에 대 한 통화 그룹 관계를 정리 하 여 잘못 된 통화 라우팅이 발생 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64747-124">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="64747-125">따릅니다</span><span class="sxs-lookup"><span data-stu-id="64747-125">Limitations</span></span>

<span data-ttu-id="64747-126">테 넌 트에는 최대 32768 개의 통화 그룹이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64747-126">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="64747-127">각 통화 그룹에 최대 25 명의 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64747-127">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="64747-128">추가 정보</span><span class="sxs-lookup"><span data-stu-id="64747-128">More information</span></span>

[<span data-ttu-id="64747-129">팀의 착신 전환 및 동시 연결</span><span class="sxs-lookup"><span data-stu-id="64747-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
