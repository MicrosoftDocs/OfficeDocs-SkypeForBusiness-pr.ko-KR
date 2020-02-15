---
title: 'Lync Server 2013: 디렉터를 사용 하도록 자동 클라이언트 로그인 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 634bfad77e61846528b6013b82921dfdc366f372
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="3d280-102">Lync Server 2013에서 디렉터를 사용 하도록 자동 클라이언트 로그인 구성</span><span class="sxs-lookup"><span data-stu-id="3d280-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d280-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3d280-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3d280-104">Lync Server 2013, 디렉터 또는 디렉터 풀을 배포할 때는 자동 클라이언트 로그인을 모범 사례로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d280-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="3d280-105">자동 클라이언트 로그인을 사용 하도록 DNS 서버를 구성 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 자동 클라이언트 로그인에 대 한 dns 요구 사항을](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d280-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="3d280-106">이미 자동 클라이언트 로그인을 배포한 경우 이를 디렉터에서 구성하려면 다음 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d280-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="3d280-107">단일 디렉터 인스턴스</span><span class="sxs-lookup"><span data-stu-id="3d280-107">Single Director Instance</span></span>

<span data-ttu-id="3d280-108">이미 자동 클라이언트 로그인을 배포 했으며 프런트 엔드 서버 또는 프런트 엔드 풀을 가리키고 있는 경우에는 디렉터를 가리키도록 DNS SRV 레코드를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d280-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="3d280-109">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="3d280-109">Director Pool</span></span>

<span data-ttu-id="3d280-110">이미 자동 클라이언트 로그인을 배포 했으며 프런트 엔드 서버 또는 프런트 엔드 풀을 가리키고 있는 경우에는 디렉터 풀을 가리키도록 DNS SRV 레코드를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d280-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

