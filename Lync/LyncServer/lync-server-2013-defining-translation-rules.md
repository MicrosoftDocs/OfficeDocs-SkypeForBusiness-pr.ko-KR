---
title: 'Lync Server 2013: 변환 규칙 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c67030878e4fe99a0deaa89e69c553b2e225fd8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="a1b2d-102">Lync Server 2013에서 변환 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="a1b2d-102">Defining translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1b2d-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a1b2d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a1b2d-104">Lync Server 2013 Enterprise Voice는 전자 164 형식으로 정규화 된 전화 번호를 기반으로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2d-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="a1b2d-105">즉, RNL (역방향 번호 조회)를 수행 하 여 일치 하는 SIP URI로 변환할 수 있도록 모든 전화 건 문자열을 E. 164 형식으로 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2d-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="a1b2d-106">Lync Server 2013는 호출 된 ID와 발신자 번호 프레젠테이션을 조작할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2d-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="a1b2d-107">이 섹션에서는 호출 된 ID 및 발신자 ID를 조작 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2d-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1b2d-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a1b2d-108">In This Section</span></span>

  - [<span data-ttu-id="a1b2d-109">Lync Server 2013의 발신자 번호 프레젠테이션</span><span class="sxs-lookup"><span data-stu-id="a1b2d-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="a1b2d-110">Lync Server 2013에서 호출 되는 ID 프레젠테이션</span><span class="sxs-lookup"><span data-stu-id="a1b2d-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1b2d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1b2d-111">See Also</span></span>


[<span data-ttu-id="a1b2d-112">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="a1b2d-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

