---
title: 'Lync Server 2013: 통화 대기 관리'
description: 'Lync Server 2013: 통화 대기를 관리 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6540cc6d4df06b3eaadd78dce8fe01990928045a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569164"
---
# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="010f2-103">Lync Server 2013의 통화 대기 관리</span><span class="sxs-lookup"><span data-stu-id="010f2-103">Managing Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="010f2-104">_**마지막으로 수정 된 항목:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="010f2-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="010f2-105">통화 대기 응용 프로그램을 사용 하면 Enterprise Voice 사용자가 전화를 통해 통화를 한 번에 전화를 걸어 나중에 모든 전화기에서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="010f2-105">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="010f2-106">사용자가 전화를 걸 때 Lync Server는 통화가 전화를 걸거나 시간이 초과 될 때까지 통화를 대기 하는 *궤도*라는 임시 번호로 통화를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="010f2-106">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="010f2-107">이 섹션의 항목에서는 배포에서 통화 대기 응용 프로그램을 사용자 지정 하 고 유지 관리 하기 위해 수행할 수 있는 작업에 대 한 단계별 절차를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="010f2-107">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="010f2-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="010f2-108">In This Section</span></span>

  - [<span data-ttu-id="010f2-109">Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성</span><span class="sxs-lookup"><span data-stu-id="010f2-109">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="010f2-110">Lync Server 2013의 통화 대기 설정 구성</span><span class="sxs-lookup"><span data-stu-id="010f2-110">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="010f2-111">Lync Server 2013에서 통화 대기 음악 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="010f2-111">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="010f2-112">Lync Server 2013에서 재해 복구 중 통화 대기 관리</span><span class="sxs-lookup"><span data-stu-id="010f2-112">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

