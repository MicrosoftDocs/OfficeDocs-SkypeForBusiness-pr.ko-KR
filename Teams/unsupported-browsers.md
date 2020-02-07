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
ms.openlocfilehash: 5f2fc7ee97a5172a849c14d9ede6d93ffc08d302
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837258"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="90aeb-103">지원 되지 않는 브라우저에서 Microsoft 팀 모임</span><span class="sxs-lookup"><span data-stu-id="90aeb-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="90aeb-104">Internet Explorer 11, Safari, Firefox 등의 일부 브라우저는 Microsoft 팀 웹 앱을 지원 하지만 일부 팀 통화 및 모임 기능은 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="90aeb-105">이 제한을 해결 하기 위해 팀 web app을 통해 사용자는 PSTN 연결을 통해 오디오를 수신 하 고 표시 되는 콘텐츠 (화면 공유)를 축소 된 디스플레이 속도로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

<span data-ttu-id="90aeb-106">팀이 지원 되지 않는 브라우저를 감지 하면 문제 및 세션 제한을 설명 하는 메시지가 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-106">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="90aeb-107">이 메시지는 팀이 사용자에 게 전화를 걸거나 사용자에 게 모임 초대에 포함 된 전화 회의 번호로 전화를 걸 수 있도록 사용자에 게 전화 번호를 남길 것을 알려 주는 등 모임 오디오에 액세스 하기 위한 추가 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-107">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="90aeb-108">또한이 메시지는 사용자가 [팀 데스크톱 클라이언트](https://teams.microsoft.com/downloads) 를 다운로드 하 고 사용 하 여 전체 팀 경험을 경험할 수 있도록 장려 합니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-108">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="90aeb-109">PSTN을 사용할 수 없는 경우에는 사용자에 게 모임에 액세스 하기 위한 지침이 표시 되지 않으며 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-109">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="90aeb-110">브라우저 제한 사항</span><span class="sxs-lookup"><span data-stu-id="90aeb-110">Browser limitations</span></span>

<span data-ttu-id="90aeb-111">지원 되지 않는 브라우저에서 팀 웹 앱을 사용 하는 사용자에 게 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-111">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="90aeb-112">오디오는 PSTN 연결을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-112">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="90aeb-113">사용자는 마이크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-113">Users can't use their microphone.</span></span>
- <span data-ttu-id="90aeb-114">사용자가 카메라를 공유 하거나 다른 참가자의 비디오를 볼 수는 없지만 이미지 기반 화면 공유를 통해 표시 된 콘텐츠를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-114">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="90aeb-115">다른 모임 참가자가 공유 하는 화면을 볼 수 있지만 사용자는 자신의 화면을 공유할 수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-115">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="90aeb-116">사용자는 화면 공유 세션 중에 제어권을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-116">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="90aeb-117">사용자는 수신 전화 알림을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-117">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="90aeb-118">통화가 중단 되 면 모임이 자동으로 다시 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-118">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="90aeb-119">사용자가 모임을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90aeb-119">Users can't start meetings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="90aeb-120">관련 항목</span><span class="sxs-lookup"><span data-stu-id="90aeb-120">Related topics</span></span>

- [<span data-ttu-id="90aeb-121">지원 되지 않는 브라우저에서 팀 모임 참가</span><span class="sxs-lookup"><span data-stu-id="90aeb-121">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
- [<span data-ttu-id="90aeb-122">Teams의 제한과 사양</span><span class="sxs-lookup"><span data-stu-id="90aeb-122">Limits and specifications for Teams</span></span>](/microsoftteams/limits-specifications-teams#browsers)