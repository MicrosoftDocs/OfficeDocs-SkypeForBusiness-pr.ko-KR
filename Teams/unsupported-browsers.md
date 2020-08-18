---
title: 지원 되지 않는 브라우저에서 Microsoft 팀 모임
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 팀이 지원 되지 않는 브라우저에서 오디오 및 비디오를 지 원하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51d19affd962b396af42f4efaec707388b186094
ms.sourcegitcommit: 27fb021e46d775652a99d862b19d94f3fc020594
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778050"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="0db54-103">지원 되지 않는 브라우저에서 Microsoft 팀 모임</span><span class="sxs-lookup"><span data-stu-id="0db54-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="0db54-104">Internet Explorer 11, Safari, Firefox 등의 일부 브라우저는 Microsoft 팀 웹 앱을 지원 하지만 일부 팀 통화 및 모임 기능은 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="0db54-105">이 제한을 해결 하기 위해 팀 web app을 통해 사용자는 PSTN 연결을 통해 오디오를 수신 하 고 표시 되는 콘텐츠 (화면 공유)를 축소 된 디스플레이 속도로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="0db54-106">Microsoft 365 앱 및 서비스는 2021 년 8 월 17 일에 시작 하는 Internet Explorer 11을 지원 하지 않습니다 (Microsoft 팀은 Internet Explorer 11 년 11 월 30 2020 일 이전에는 지원 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="0db54-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="0db54-107">[자세히 알아보세요](https://aka.ms/AA97tsw).</span><span class="sxs-lookup"><span data-stu-id="0db54-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="0db54-108">Internet Explorer 11은 지원 되는 브라우저에 남아 있음을 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0db54-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="0db54-109">Internet Explorer 11은 Windows 운영 체제의 구성 요소 이며 설치 된 제품에 대 한 [주기 정책을 따릅니다](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) .</span><span class="sxs-lookup"><span data-stu-id="0db54-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="0db54-110">팀이 지원 되지 않는 브라우저를 감지 하면 문제 및 세션 제한을 설명 하는 메시지가 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="0db54-111">이 메시지는 팀이 사용자에 게 전화를 걸거나 사용자에 게 모임 초대에 포함 된 전화 회의 번호로 전화를 걸 수 있도록 사용자에 게 전화 번호를 남길 것을 알려 주는 등 모임 오디오에 액세스 하기 위한 추가 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="0db54-112">또한이 메시지는 사용자가 [팀 데스크톱 클라이언트](https://teams.microsoft.com/downloads) 를 다운로드 하 고 사용 하 여 전체 팀 경험을 경험할 수 있도록 장려 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="0db54-113">PSTN을 사용할 수 없는 경우에는 사용자에 게 모임에 액세스 하기 위한 지침이 표시 되지 않으며 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="0db54-114">브라우저 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0db54-114">Browser limitations</span></span>

<span data-ttu-id="0db54-115">지원 되지 않는 브라우저에서 팀 웹 앱을 사용 하는 사용자에 게 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="0db54-116">오디오는 PSTN 연결을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="0db54-117">사용자는 마이크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="0db54-118">사용자가 카메라를 공유 하거나 다른 참가자의 비디오를 볼 수는 없지만 이미지 기반 화면 공유를 통해 표시 된 콘텐츠를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="0db54-119">다른 모임 참가자가 공유 하는 화면을 볼 수 있지만 사용자는 자신의 화면을 공유할 수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="0db54-120">사용자는 화면 공유 세션 중에 제어권을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="0db54-121">사용자는 수신 전화 알림을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="0db54-122">통화가 중단 되 면 모임이 자동으로 다시 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="0db54-123">사용자가 모임을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0db54-123">Users can't start meetings.</span></span>

<span data-ttu-id="0db54-124">팀의 브라우저 지원에 대 한 자세한 내용은 [팀에 대 한 제한 및 규정](/microsoftteams/limits-specifications-teams#browsers)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0db54-124">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0db54-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0db54-125">Related topics</span></span>

- [<span data-ttu-id="0db54-126">지원 되지 않는 브라우저에서 팀 모임 참가</span><span class="sxs-lookup"><span data-stu-id="0db54-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
