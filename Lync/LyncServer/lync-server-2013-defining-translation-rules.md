---
title: 'Lync Server 2013: 변환 규칙 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd10438fa469b7c6d6285a616d9b9f5f3a262c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="bb58c-102">Lync Server 2013에서 변환 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="bb58c-102">Defining translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb58c-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="bb58c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="bb58c-104">Lync Server 2013 엔터프라이즈 음성은 전자 164 형식으로 정규화 된 전화 번호를 기준으로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="bb58c-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="bb58c-105">즉, 역 번호 조회 (RNL)를 수행 하기 위해 모든 대상 문자열을 해당 SIP URI로 변환할 수 있도록 E를 164 형식으로 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb58c-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="bb58c-106">Lync Server 2013는 호출 된 ID와 발신자 ID 프레젠테이션을 조작할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb58c-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="bb58c-107">이 섹션에서는 호출 된 ID와 발신자 ID를 조작 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb58c-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb58c-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bb58c-108">In This Section</span></span>

  - [<span data-ttu-id="bb58c-109">Lync Server 2013의 발신자 ID 프레젠테이션</span><span class="sxs-lookup"><span data-stu-id="bb58c-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="bb58c-110">Lync Server 2013에서 ID 프레젠테이션 호출</span><span class="sxs-lookup"><span data-stu-id="bb58c-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb58c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb58c-111">See Also</span></span>


[<span data-ttu-id="bb58c-112">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="bb58c-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

