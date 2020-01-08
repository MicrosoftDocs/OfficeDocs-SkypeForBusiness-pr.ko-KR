---
title: 중재 서버 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="966e6-102">중재 서버 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="966e6-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="966e6-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="966e6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="966e6-104">병합 마법사를 실행할 때 중재 서버는 Lync Server 2013 파일럿 토폴로지에 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="966e6-105">그러나 Office Communications Server 2007 R2 풀이 Lync Server 2013 조정 서버와 통신할 수 없기 때문에 모든 사용자를 마이그레이션한 후에는 Lync Server 2013 조정 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="966e6-106">병렬 마이그레이션 중에 Lync Server 2013 풀은 Office Communications Server 2007 R2 중재 서버와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="966e6-107">Lync Server 2013 조정 서버를 구성할 때는 Office Communications Server 2007 R2 게이트웨이도 업그레이드 하거나 교체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="966e6-108">Office Communications Server 2007 R2 게이트웨이는 Lync Server 2013 중재 서버를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="966e6-109">Lync Server 2013에 대해 인증 된 게이트웨이를 배포 하 고 Lync Server 2013 조정 서버와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="966e6-110">이 단계는 Office Communications Server 2007 R2 배포를 완전히 서비스 해제 하기 전에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="966e6-111">이 섹션의 항목에서는 Lync Server 2013 조정 서버의 마이그레이션을 완료 한 후 수행 해야 하는 구성 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="966e6-112">Collocated 중재 서버를 독립 실행형 중재 서버로 전환 하는 것은 선택적 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="966e6-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="966e6-113">중재 서버 구성</span><span class="sxs-lookup"><span data-stu-id="966e6-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="966e6-114">새 Lync Server 2013 중재 서버를 사용 하도록 음성 경로 변경</span><span class="sxs-lookup"><span data-stu-id="966e6-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="966e6-115">Collocated 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="966e6-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

