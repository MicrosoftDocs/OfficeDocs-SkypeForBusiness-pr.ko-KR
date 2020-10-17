---
title: 'Lync Server 2013: 디렉터를 사용 하도록 자동 클라이언트 Sign-In 구성'
description: 'Lync Server 2013: 디렉터를 사용 하도록 자동 클라이언트 Sign-In를 구성 합니다.'
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
ms.openlocfilehash: b9c45a1a677d3a30704d8dca1771ef865cef29ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546654"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="b4fd8-103">Lync Server 2013에서 디렉터를 사용 하도록 자동 클라이언트 Sign-In 구성</span><span class="sxs-lookup"><span data-stu-id="b4fd8-103">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4fd8-104">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b4fd8-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b4fd8-105">Lync Server 2013, 디렉터 또는 디렉터 풀을 배포할 때는 자동 클라이언트 Sign-In를 최상의 방법으로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fd8-105">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="b4fd8-106">자동 클라이언트 로그인을 사용 하도록 DNS 서버를 구성 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 자동 클라이언트 로그인에 대 한 dns 요구 사항을](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4fd8-106">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="b4fd8-107">이미 자동 클라이언트 로그인을 배포한 경우 이를 디렉터에서 구성하려면 다음 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4fd8-107">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="b4fd8-108">단일 디렉터 인스턴스</span><span class="sxs-lookup"><span data-stu-id="b4fd8-108">Single Director Instance</span></span>

<span data-ttu-id="b4fd8-109">이미 자동 클라이언트 Sign-In 배포 되어 있고 프런트 엔드 서버 또는 프런트 엔드 풀을 가리키고 있는 경우에는 디렉터를 가리키도록 DNS SRV 레코드를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4fd8-109">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="b4fd8-110">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="b4fd8-110">Director Pool</span></span>

<span data-ttu-id="b4fd8-111">이미 자동 클라이언트 Sign-In 배포 되었으며 프런트 엔드 서버 또는 프런트 엔드 풀을 가리키고 있는 경우 디렉터 풀을 가리키도록 DNS SRV 레코드를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4fd8-111">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

