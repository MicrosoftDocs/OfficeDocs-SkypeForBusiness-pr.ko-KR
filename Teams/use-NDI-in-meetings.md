---
title: Microsoft 팀에서 NDI 사용
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft 팀에서 NDI를 사용 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 24e4312af520bf783c0382b7543190644bfc1ff0
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47323992"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="0a64f-103">Microsoft 팀에서 NDI® 기술 사용</span><span class="sxs-lookup"><span data-stu-id="0a64f-103">Use NDI® technology in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

 <span data-ttu-id="0a64f-104">NDI® (네트워크 장치 인터페이스) 기술은 미디어 장치 (예: 스튜디오 카메라 및 믹서)를 연결 하는 최신 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-104">NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="0a64f-105">NDI® 기술을 사용 하는 대신 로컬 컴퓨터를 포함 하 여 로컬 인트라넷을 통해 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="0a64f-106">NewTek NDI® 기술은 스트림에 대 한 라이브 콘텐츠를 생성 하는 표준 업계 솔루션이 되었으며, 전문 방송 환경에서 상당한 인식과 채택을 얻었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-106">NewTek NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="0a64f-107">Skype는 이전에 2018의 Skype에 NDI® out 기능을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="0a64f-108">Microsoft 팀은이 기능을 활용 하 여 모임 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="0a64f-109">NDI® 기술은 로컬 네트워크로 제한 되며, 브로드캐스트 솔루션이 아닌 프로덕션 워크플로의 일부로 간주 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="0a64f-110">NDI® 기술 켜기</span><span class="sxs-lookup"><span data-stu-id="0a64f-110">Turn on NDI® technology</span></span>

<span data-ttu-id="0a64f-111">NDI® 기술을 사용 하려면 두 단계가 사용자에 게 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="0a64f-112">테 넌 트 관리자는 CsTeamsMeetingPolicy에서 ' AllowNDIStreaming ' 속성을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="0a64f-113">이 변경 내용이 채워지면 최종 사용자가 **설정**  >  **사용 권한**으로부터 해당 클라이언트에 대해 ndi® 기술을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="0a64f-114">사용자가 모임에 참가할 때 모임이 브로드캐스트 되 고 있음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="0a64f-115">사용자가 브로드캐스트에 포함 하지 않으려는 경우 모임에서 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="0a64f-116">다음 이미지는 팀 모임에서 사용자에 게 표시 되는 배너 메시지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![팀 모임에 표시 되는 NDI® 기술 배너의 이미지입니다.](media/NDI-disclosure.png)

<span data-ttu-id="0a64f-118">이 배너에는 [Microsoft 개인정보 보호 정책](https://aka.ms/teamsprivacy)에 대 한 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="0a64f-119">지원 되는 로캘 및 사용자 유형</span><span class="sxs-lookup"><span data-stu-id="0a64f-119">Supported locales and user types</span></span>

<span data-ttu-id="0a64f-120">NDI® 기술이 모든 로캘에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="0a64f-121">다음 사용자는 NDI® 기술 스트림에 포함 되어 있지만 일부 사용자는 NDI® 기술 스트림에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="0a64f-122">테 넌 트-링/tenantId/userId를 기준으로 제공 되는 완전 한 지원 (모임 정책에 의해 제어 됨)</span><span class="sxs-lookup"><span data-stu-id="0a64f-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="0a64f-123">페더레이션 – 스트림 액세스가 없음 (NDI® 기술이 설정 된 경우에도)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0a64f-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="0a64f-124">Freemium-스트림 액세스 없음</span><span class="sxs-lookup"><span data-stu-id="0a64f-124">Freemium - no stream access</span></span>
- <span data-ttu-id="0a64f-125">익명 – 스트림 액세스 없음</span><span class="sxs-lookup"><span data-stu-id="0a64f-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="0a64f-126">게스트 – 스트림 액세스 없음</span><span class="sxs-lookup"><span data-stu-id="0a64f-126">Guest – no stream access</span></span>  

<span data-ttu-id="0a64f-127">장치 <sup>1</sup> 개에는 기본적으로 설정 되어 있는 ndi® 기술 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="0a64f-128">모임 참가자가 NDI® 기술을 끈 장치를 사용 하는 경우 NDI® 기술을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a64f-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
