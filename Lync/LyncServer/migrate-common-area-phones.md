---
title: 공통 영역 전화 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7abaa29d2383f80a6f822eaa5d524197996500b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="b9e2a-102">공통 영역 전화 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b9e2a-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9e2a-103">_**마지막으로 수정 된 항목:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="b9e2a-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="b9e2a-104">공통 영역 전화는 공유 작업 영역 또는 일반적인 영역 (예를 들어, 로비, 주방 또는 공장 바닥)에 있는 IP 전화입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="b9e2a-105">Lync Server UC 기능을 제공 하기 위해 일반 영역 전화를 컴퓨터에 연결할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="b9e2a-106">Lync server 2010 배포를 Lync Server 2013로 마이그레이션한 후에는 레거시 공통 영역 전화와 연결 된 대화 상대 개체도 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="b9e2a-107">Lync Server 관리 셸을 사용 하 여 먼저 Lync server 2010 공통 영역 전화와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 Lync Server 2013 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="b9e2a-108">**공통 영역 전화 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="b9e2a-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="b9e2a-109">Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="b9e2a-110">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="b9e2a-111">모든 대화 상대 개체가 Lync Server 2013 풀로 이동 되었는지 확인 하려면 Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="b9e2a-112">모든 대화 상대 개체가 Lync Server 2013 풀과 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e2a-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

