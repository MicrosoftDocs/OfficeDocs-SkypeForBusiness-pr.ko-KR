---
title: Microsoft Teams에서 NDI 사용
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams에서 NDI를 사용하는 방법을 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337017"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="b91a4-103">Microsoft Teams에서 NDI® 기술 사용</span><span class="sxs-lookup"><span data-stu-id="b91a4-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="b91a4-104">NewTek NDI®(네트워크 디바이스 인터페이스) 기술은 미디어 디바이스(예: 스튜디오 카메라 및 믹서)를 연결하기 위한 최신 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="b91a4-105">NDI® 기술을 사용하면 물리적 연결을 사용하는 대신 로컬 머신을 포함하여 로컬 인트라넷을 통해 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="b91a4-106">NDI® 기술은 스트림용 라이브 콘텐츠를 생성하기 위한 표준 산업 솔루션이 됐고 전문 브로드캐스트 세계에서 상당한 인지도와 채택을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="b91a4-107">Skype는 이전에 2018년 후반에 NDI® 기능을 Skype에 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="b91a4-108">Microsoft Teams는 이 기능을 사용하여 모임 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="b91a4-109">NDI® 기술은 로컬 네트워크로 제한되어 있으며 브로드캐스트 솔루션이 아닌 프로덕션 워크플로의 일부로만 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="b91a4-110">NDI 및 ® 켜기</span><span class="sxs-lookup"><span data-stu-id="b91a4-110">Turn on NDI® technology</span></span>

<span data-ttu-id="b91a4-111">NDI® 기술을 사용하려면 사용자에 대해 두 단계를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="b91a4-112">테넌트 관리자는 CsTeamsMeetingPolicy에서 'AllowNDIStreaming' 속성을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="b91a4-113">이 변경이 채워진 후 최종 사용자는 설정 권한에서 특정 클라이언트에 대한 NDI® 기술을  >  **켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b91a4-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="b91a4-114">사용자가 모임에 참가하면 모임이 브로드캐스트 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="b91a4-115">사용자가 브로드캐스트에 포함하지 못하게 하려는 경우 모임에서 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="b91a4-116">다음 이미지는 사용자가 Teams 모임에서 볼 수 있는 배너 메시지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Teams ® 표시하는 기술 배너입니다.](media/NDI-disclosure.png)

<span data-ttu-id="b91a4-118">배너에는 Microsoft 개인 정보 취급 방침에 [대한 링크가 있습니다.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="b91a4-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="b91a4-119">지원되는 지역 및 사용자 유형</span><span class="sxs-lookup"><span data-stu-id="b91a4-119">Supported locales and user types</span></span>

<span data-ttu-id="b91a4-120">NDI® 기술은 모든 로케일에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="b91a4-121">다음 사용자는 NDI® 기술 스트림에 포함되지만 일부 사용자가 NDI 및 기술 스트림에 액세스할 ® 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="b91a4-122">테넌트 내 – 링/tenantId/userId(모임 정책에 의해 제어)에 따라 제공된 전체 지원</span><span class="sxs-lookup"><span data-stu-id="b91a4-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="b91a4-123">페더링 – 스트림 액세스 없음(NDI® 기술이 있는<sup>경우에도) 1</sup></span><span class="sxs-lookup"><span data-stu-id="b91a4-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="b91a4-124">프리미엄 - 스트림 액세스 없음</span><span class="sxs-lookup"><span data-stu-id="b91a4-124">Premium - no stream access</span></span>
- <span data-ttu-id="b91a4-125">익명 – 스트림 액세스 없음</span><span class="sxs-lookup"><span data-stu-id="b91a4-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="b91a4-126">게스트 - 스트림 액세스 없음</span><span class="sxs-lookup"><span data-stu-id="b91a4-126">Guest – no stream access</span></span>  

<span data-ttu-id="b91a4-127"><sup>1개</sup> 디바이스에는 기본적으로 ® NDI 및 기술 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="b91a4-128">모임 참가자가 NDI® 디바이스를 사용하는 경우 NDI 및 ® 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91a4-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
