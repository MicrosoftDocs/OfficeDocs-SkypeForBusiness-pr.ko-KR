---
title: 'Lync Server 2013: 공유 라인 모양에 대 한 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="c839d-102">Lync Server 2013의 공유 라인 모양에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="c839d-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c839d-103">_**마지막으로 수정한 주제:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="c839d-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="c839d-104">이 항목에서는 Lync Server 2013, 누적 업데이트 4 월 2016에서 SLA (공유 선 모양)를 계획 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="c839d-105">공유 되는 선 모양은 공유 번호 라는 특정 번호에서 여러 통화를 처리 하는 Lync Server 2013 누적 업데이트 4 월 2016의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="c839d-106">SLA는 여러 회선을 통해 엔터프라이즈 음성 사용 Lync 사용자를 공유 번호로 구성 하 여 복수 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="c839d-107">전화는 실제로 공유 번호로 수신 되지 않고 공유 번호의 대리인 역할을 하는 사용자에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="c839d-108">대리인 중 한 명의 대리인은 통화를 선택한 사람에 대 한 알림 메시지를 받을 수 있으며, 그 결과로 약속이 있는 줄이 있는지에 대 한 알림이 전화에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="c839d-109">줄 수와 대리인은 모두 SLA에서 공유 되는 번호로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="c839d-110">또한 BusyOption (모든 회선이 사용 중일 때 발생 하는 상황) 및 MissedCallOption (대리인의 모든 항목이 없는 경우)과 같은 고급 옵션이 공유 번호에 대해 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="c839d-111">SLA는 다음 전화 장치 에서만 지원 됩니다 (컴퓨터, 휴대 전화 또는 기타 장치에서는 Lync 클라이언트에 대해 지원 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="c839d-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="c839d-112">Polycom VVX300 펌웨어 업데이트 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c839d-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c839d-113">Polycom VVX400 펌웨어 업데이트 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c839d-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c839d-114">Polycom VVX500 펌웨어 업데이트 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c839d-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c839d-115">Polycom VVX600 펌웨어 업데이트 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c839d-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="c839d-116">SLA는 Lync Server 2013, 누적 업데이트 4 월 2016의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="c839d-117">SLA 배포에 대 한 자세한 내용은 [Lync Server 2013에서 공유 선 모양 배포](lync-server-2013-deploy-shared-line-appearance.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c839d-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="c839d-118">기능 목록</span><span class="sxs-lookup"><span data-stu-id="c839d-118">Feature List</span></span>

<span data-ttu-id="c839d-119">SLA 그룹을 설정 하면 다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="c839d-120">그룹의 모든 대리인은 같은 공유 번호로 들어오는 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="c839d-121">통화는 PSTN 기반 이거나 SIP 기반 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="c839d-122">대리인은 통화를 보류 하 고 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="c839d-123">대리인은 전화를 SLA 그룹 밖의 번호로 양도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="c839d-124">대리인은 현재 공유 번호에 있는 통화 수를 확인 하 고 각 통화의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="c839d-125">공유 번호에 대 한 최대 동시 통화 수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="c839d-126">이 최대값에 도달한 후 추가 통화를 처리 하는 방법을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="c839d-127">불필요 한 통화는 통화 중 신호를 통해 거부 하거나, 대체 번호로 착신 전환 하거나, 음성 메일로 착신 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="c839d-128">부재 중 통화 (특정 시간 이후에 선택 되지 않은 통화)를 처리 하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="c839d-129">그룹 id에 대해 음성 메일을 사용 하도록 설정 하면 부재 중 통화가 자동으로 음성 메일로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="c839d-130">그룹 id (공유 번호)에 대해 음성 메일을 사용할 수 없는 경우 부재 중 통화를 거부 하거나 다른 번호로 착신 전환 하거나 연결을 끊지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c839d-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

