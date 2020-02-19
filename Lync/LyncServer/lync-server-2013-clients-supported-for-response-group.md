---
title: 'Lync Server 2013: 응답 그룹에 대해 지원 되는 클라이언트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Response Group
ms:assetid: 84911025-e754-41a8-ba48-e31c058fc557
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398674(v=OCS.15)
ms:contentKeyID: 48184705
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df73091da5c71451940362600a345ff2b2b96c7a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-response-group-in-lync-server-2013"></a><span data-ttu-id="04834-102">Lync Server 2013의 응답 그룹에 대해 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="04834-102">Clients supported for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04834-103">_**마지막으로 수정 된 항목:** 2014-03-28_</span><span class="sxs-lookup"><span data-stu-id="04834-103">_**Topic Last Modified:** 2014-03-28_</span></span>

<span data-ttu-id="04834-104">응답 그룹 응용 프로그램은 다음 클라이언트를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="04834-104">The Response Group application supports the following clients:</span></span>

  - <span data-ttu-id="04834-105">Lync 2013 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="04834-105">Lync 2013 desktop client</span></span>

  - <span data-ttu-id="04834-106">Lync 2010 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="04834-106">Lync 2010 desktop client</span></span>

  - <span data-ttu-id="04834-107">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="04834-107">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="04834-108">Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="04834-108">Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="04834-109">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="04834-109">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04834-110">응답 그룹 응용 프로그램은 Lync 모바일 클라이언트에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04834-110">The Response Group application is not supported on Lync mobile clients.</span></span>



</div>

<span data-ttu-id="04834-111">새 기능에 대 한 자세한 내용은 시작 설명서에서 [Lync Server 2013의 새 응답 그룹 응용 프로그램 기능](lync-server-2013-new-response-group-application-features.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04834-111">For details about new features, see [New Response Group application features in Lync Server 2013](lync-server-2013-new-response-group-application-features.md) in the Getting Started documentation.</span></span>

<span data-ttu-id="04834-112">사용할 수 있는 특정 클라이언트는 다음과 같은 응답 그룹 사용자의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="04834-112">The specific client that you can use depends on the type of Response Group user that you are:</span></span>

  - <span data-ttu-id="04834-113">**발신자**는 앞에 나열된 클라이언트와 PSTN(공중 전화망)을 통해 일반 전화기를 사용하여 응답 그룹에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04834-113">**Callers** can call a response group by using any of the clients listed previously, and by using a standard telephone over the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="04834-114">**비공식적인 에이전트** (통화를 수락 하기 위해 그룹에 로그인 하지 않은 에이전트)는 전화 교환, Lync 또는 Lync Phone Edition을 사용 하 여 통화를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04834-114">**Informal agents** (agents who do not sign into and out of their groups to accept calls) can accept calls by using Attendant, Lync, or Lync Phone Edition.</span></span> <span data-ttu-id="04834-115">비공식적인 에이전트는 이러한 클라이언트 중 하나를 사용 하 여 Lync Server 2013에 로그인 하면 해당 그룹에 자동으로 로그인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04834-115">Informal agents are automatically signed into their groups when they sign in to Lync Server 2013 by using one of these clients.</span></span>

  - <span data-ttu-id="04834-116">**공식 에이전트** (통화를 수락 하기 위해 그룹에 로그인 하거나 로그 아웃 해야 하는 에이전트)는 Lync 2013을 사용 하 여 통화를 수락 하 고, 메뉴 항목에서 에이전트 콘솔에 액세스 하거나, 전화 교환을 사용 하 고 Internet Explorer에서 에이전트 콘솔에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04834-116">**Formal agents** (agents who must sign into and out of their groups to accept calls) can accept calls by using Lync 2013 and accessing the agent console from the menu item, or by using Attendant and accessing the agent console directly from Internet Explorer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

