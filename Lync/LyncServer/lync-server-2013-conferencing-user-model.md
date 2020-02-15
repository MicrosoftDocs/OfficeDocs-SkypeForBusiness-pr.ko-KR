---
title: Lync Server 2013 회의 사용자 모델
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcc74259f9a5cb6ee40cb29fbab56e638ba78b79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="c209d-102">Lync Server 2013의 회의 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="c209d-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c209d-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c209d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c209d-104">Lync Server 회의 사용자 모델의 중요 한 부분은 모임 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="c209d-105">이전 섹션에서 설명한 대로 여러 데이터 요소에서 데이터를 수집한 결과, Microsoft에서는 다음을 파악했습니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="c209d-106">대부분의 모임은 참가자가 평균 4~6명인 소규모의 공동 작업 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="c209d-107">약 80%의 모임은 참가자가 20명 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="c209d-108">99.98%의 모임은 참가자가 100명 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="c209d-109">모임 크기 이외에도 회의 사용자 모델은 다음과 같은 여러 가지 요인을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="c209d-110">**동시 회의**   회의에 예상 되는 사용자의 수는 얼마나 됩니까?</span><span class="sxs-lookup"><span data-stu-id="c209d-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="c209d-111">**미디어 믹스**   사용할 수 있는 미디어 유형 및 모임 사용자가 사용 해야 할 것으로 예상 되는 기능은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="c209d-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="c209d-112">**사용자 유형은**   사용자 내부 사용자, 원격 사용자, 페더레이션 사용자 또는 익명 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="c209d-113">**모임 램프 가동 시간**   모든 모임 사용자가 모임에 참가 하는 데 어느 정도의 시간이 걸립니까?</span><span class="sxs-lookup"><span data-stu-id="c209d-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="c209d-114">사용자 모델에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c209d-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="c209d-115">테스트에 사용할 모임 및 사용자 수를 결정하기 위해 Microsoft에서는 다음을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="c209d-116">한 조직의 전체 사용자 수(예: 80,000명의 사용자)에 모임 동시 참가 비율(예: 전체 사용자의 5%)을 곱하여 동시에 모임에 참가할 것으로 예상되는 총 사용자 수(이 예에서 4,000명의 사용자)를 파악했습니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="c209d-117">총 사용자 수를 Lync Server 2013, 배포의 프런트 엔드 서버 (예: 8 개 서버)로 나누어 프런트 엔드 서버당 예상 모임 참가자 수 (이 예에서는 프런트 엔드 서버당 500 사용자)를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="c209d-118">프런트 엔드 서버 당 사용자 수를 평균 모임 크기 (예: 4 명의 사용자)로 나누면 프런트 엔드 서버당 예상 평균 모임 수 (이 예에서는 프런트 엔드 서버당 125 회의)를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="c209d-119">각 프런트 엔드 서버에서 미디어 부하를 확보 하기 위해 미디어 조합이 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="c209d-120">예를 들어 회의의 75%에 오디오 지원 뿐 아니라 이러한 모임의 50% 이상이 필요한 경우 응용 프로그램 공유가 필요한 경우 평균 47 회의 및 188 사용자가 각 프런트 엔드 서버에 동시에 응용 프로그램 공유를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="c209d-121">서버 확장성을 보장하도록 공유 풀에 최대 250명의 사용자가 있는 사용자 모델을 기반으로 다양한 모임 크기를 테스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="c209d-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

