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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 통화 공유 및 그룹 통화 픽업 사용자는 사용자를 사용할 수 없는 경우 전화를 통해 들어오는 전화를 동료와 공유할 수 있습니다.
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182273"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="61a56-103">Microsoft 팀에서 공유 및 그룹 통화 걸기</span><span class="sxs-lookup"><span data-stu-id="61a56-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="61a56-104">Microsoft 팀의 통화 공유 및 그룹 통화 픽업 기능을 통해 사용자가 사용자를 사용할 수 없는 동안 발생 하는 전화를 받을 수 있도록 동료와의 수신 전화를 공유할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="61a56-105">사용자가 들어오는 공유 통화에 대 한 알림을 받는 방법을 구성할 수 있으므로 (예: 착신 통화 전환 또는 동시 연결) 다른 형태의 통화 공유에 대 한 낮은 중단의 경우 그룹 통화 또는 배너에 응답 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="61a56-106">다른 사용자와 통화를 공유 하려면 통화 그룹을 만들고 통화를 공유 하려는 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="61a56-107">그런 다음 동시 링 또는 전달 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="61a56-108">자세한 내용은 [팀의 착신 전환 및 동시](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61a56-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61a56-109">통화 그룹 소유자 및 통화 그룹의 구성원은 팀 전용 배포 모드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="61a56-110">팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61a56-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="61a56-111">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="61a56-111">License required</span></span>

<span data-ttu-id="61a56-112">통화 공유 및 그룹 통화 픽업 설정 및 사용을 위해서는 사용자가 엔터프라이즈 음성 기능을 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="61a56-113">라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 용 Office 365 라이선스](office-365-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61a56-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="61a56-114">그룹 통화 픽업 구성</span><span class="sxs-lookup"><span data-stu-id="61a56-114">Configure group call pickup</span></span>

<span data-ttu-id="61a56-115">그룹 통화 픽업을 설정 하려면 사용자가 먼저 통화 그룹 (보안 그룹 또는 Office 365 그룹과 동일 하지 않음)을 구성한 다음 통화를 공유할 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="61a56-116">그런 다음 동시 링 또는 통화 전달 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="61a56-117">자세한 내용 및 단계별 절차는 [팀의 착신 전환 및 동시](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61a56-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="61a56-118">통화 그룹 만들기 및 알림 기본 설정은 사용자 구동 기능입니다. 관리자는 사용자를 위해 이러한 기능을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="61a56-119">보안 그룹 또는 Office 365 그룹에서 통화 그룹을 만들 수 없습니다. 팀에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="61a56-120">관리자는 사용자에 대 한 **Teamscallingpolicy AllowCallGroups** 설정을 통해 통화 그룹을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="61a56-121">관리자는이 사용자가 통화 그룹을 구성할 수 있는지만 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="61a56-122">비트가 true로 설정 되 면 관리자는 사용자가 원하는 호출 그룹 사용자를 구성 하 고 추가 하는 것을 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="61a56-123">따릅니다</span><span class="sxs-lookup"><span data-stu-id="61a56-123">Limitations</span></span>

<span data-ttu-id="61a56-124">테 넌 트에는 최대 32768 개의 통화 그룹이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="61a56-125">각 통화 그룹에 최대 5 명의 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a56-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="61a56-126">추가 정보</span><span class="sxs-lookup"><span data-stu-id="61a56-126">More information</span></span>

[<span data-ttu-id="61a56-127">팀의 착신 전환 및 동시 연결</span><span class="sxs-lookup"><span data-stu-id="61a56-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)