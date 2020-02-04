---
title: 'Lync Server 2013: 분기 사이트 음성 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for branch-site voice resiliency
ms:assetid: 67713f57-3ded-4127-ac37-57d8099bf384
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398477(v=OCS.15)
ms:contentKeyID: 48184351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 004790da7562374284e11e28c6e89836a924f654
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-branch-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="8e71d-102">Lync Server 2013의 분기 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="8e71d-102">Planning for branch-site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e71d-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8e71d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8e71d-104">가용성 엔터프라이즈 음성 서비스를 제공 하는 경우에는 다음과 같은 세 가지 방법으로 지점 사이트의 복원을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e71d-104">If you want to provide branch-site resiliency, that is, high-availability Enterprise Voice service, you have three options for doing so:</span></span>

  - <span data-ttu-id="8e71d-105">Survivable 분기 기기</span><span class="sxs-lookup"><span data-stu-id="8e71d-105">Survivable Branch Appliance</span></span>

  - <span data-ttu-id="8e71d-106">Survivable Branch 서버</span><span class="sxs-lookup"><span data-stu-id="8e71d-106">Survivable Branch Server</span></span>

  - <span data-ttu-id="8e71d-107">지점 사이트의 전체 Lync Server 배포</span><span class="sxs-lookup"><span data-stu-id="8e71d-107">A full Lync Server deployment at the branch site</span></span>

<span data-ttu-id="8e71d-108">이 가이드는 조직에 가장 적합 한 탄력성 솔루션을 평가 하는 데 도움이 되며 PSTN 연결 솔루션에 해당 하는 복원 솔루션을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e71d-108">This guide will help you evaluate which resiliency solution is best for your organization and, based on your resiliency solution, which PSTN-connectivity solution to use.</span></span> <span data-ttu-id="8e71d-109">또한 필수 구성 요소 및 기타 계획 고려 사항을 설명 하 여 선택한 솔루션을 배포 하도록 준비 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e71d-109">It will also help you prepare to deploy the solution that you choose by describing prerequisites and other planning considerations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8e71d-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8e71d-110">In This Section</span></span>

  - [<span data-ttu-id="8e71d-111">Lync Server 2013의 분기 사이트 복구 기능</span><span class="sxs-lookup"><span data-stu-id="8e71d-111">Branch-site resiliency features in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-features.md)

  - [<span data-ttu-id="8e71d-112">Lync Server 2013의 분기 사이트 복구 솔루션</span><span class="sxs-lookup"><span data-stu-id="8e71d-112">Branch-site resiliency solutions in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-solutions.md)

  - [<span data-ttu-id="8e71d-113">Lync Server 2013에 대한 분기 사이트 복구 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e71d-113">Branch-site resiliency requirements for Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-requirements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

