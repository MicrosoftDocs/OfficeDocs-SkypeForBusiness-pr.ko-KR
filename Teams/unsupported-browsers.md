---
title: Microsoft Teams 브라우저에서 모임을 열 수 있습니다.
author: cichur
ms.author: v-cichur
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
description: 지원되지 Teams 브라우저에서 오디오 및 비디오를 지원하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121316"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="6ad01-103">Microsoft Teams 브라우저에서 모임을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="6ad01-104">11, Internet Explorer, Safari 및 Firefox와 같은 일부 브라우저는 Microsoft Teams 웹앱을 지원하지만 일부 Teams 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="6ad01-105">이 제한 사항을 해결하기 위해 Teams 웹앱을 사용하면 사용자가 PSTN 연결을 통해 오디오를 수신하고 표시 속도 감소로 제시된 콘텐츠(화면 공유)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="6ad01-106">Microsoft 365 앱 및 서비스는 2021년 8월 17일부터 Internet Explorer 11일(Microsoft Teams 11월 30일부터 Internet Explorer 지원하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="6ad01-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="6ad01-107">[자세한 정보](https://aka.ms/AA97tsw)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="6ad01-108">Internet Explorer 11은 지원되는 브라우저로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="6ad01-109">Internet Explorer 11은 Windows 운영 체제의 구성 요소로 [](/lifecycle/faq/internet-explorer-microsoft-edge) 설치되는 제품에 대한 수명 주기 정책을 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="6ad01-110">지원 Teams 브라우저를 검색하면 문제 및 세션 제한 사항을 설명하는 메시지가 자동으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="6ad01-111">이 메시지는 사용자에게 전화를 걸 수 있도록 전화 걸기 번호를 남겨 두라고 Teams 모임 초대에 포함된 전화 회의 번호를 호출하도록 사용자에게 지시하는 등 모임 오디오에 액세스하기 위한 추가 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="6ad01-112">또한 메시지는 사용자가 전체 Teams 데스크톱 [](https://teams.microsoft.com/downloads) 클라이언트를 다운로드하고 사용하는 Teams 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="6ad01-113">PSTN을 사용할 수 없는 경우 사용자는 모임에 액세스하는 지침이 표시되지 않습니다. 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="6ad01-114">브라우저 제한 사항</span><span class="sxs-lookup"><span data-stu-id="6ad01-114">Browser limitations</span></span>

<span data-ttu-id="6ad01-115">지원되지 않는 브라우저에서 Teams 웹앱을 사용하는 사람들은 다음과 같은 제한 사항을 경험하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="6ad01-116">오디오는 PSTN 연결을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="6ad01-117">사용자는 마이크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="6ad01-118">사용자는 카메라를 공유하거나 다른 참가자의 비디오를 볼 수 없지만 이미지 기반 화면 공유를 통해 제시된 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="6ad01-119">다른 모임 참가자가 공유하는 화면을 볼 수 있도 사용자가 자신의 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="6ad01-120">사용자는 화면 공유 세션 중에 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="6ad01-121">사용자는 들어오는 통화 알림을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="6ad01-122">통화가 중단되면 모임이 자동으로 다시 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="6ad01-123">사용자는 모임을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad01-123">Users can't start meetings.</span></span>

<span data-ttu-id="6ad01-124">에서 브라우저 지원에 대한 Teams 에 대한 제한 및 사양을 [Teams.](./limits-specifications-teams.md#browsers)</span><span class="sxs-lookup"><span data-stu-id="6ad01-124">For more information about browser support in Teams, see [Limits and specifications for Teams](./limits-specifications-teams.md#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6ad01-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6ad01-125">Related topics</span></span>

- [<span data-ttu-id="6ad01-126">지원되지 Teams 브라우저에서 모임 참가</span><span class="sxs-lookup"><span data-stu-id="6ad01-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)