---
title: 'Lync Server 2013: 호출 되는 ID 프레젠테이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddb1902422cb3efc52f4f0b3271976ab9b9950e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508225"
---
# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="d3e60-102">Lync Server 2013에서 호출 되는 ID 프레젠테이션</span><span class="sxs-lookup"><span data-stu-id="d3e60-102">Called ID presentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3e60-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d3e60-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d3e60-104">Lync Server 2010를 사용 하는 경우 호출 된 당사자의 전화 번호 (전화 번호)는 E. 164 형식에서 트렁크 피어에 필요한 로컬 전화 걸기 형식 (연결 된 게이트웨이, PBX (private branch exchange) 또는 SIP 트렁크)으로 변환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e60-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="d3e60-105">이 작업을 수행 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 변환 규칙을 하나 이상 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e60-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3e60-p102">트렁크 피어에서 변환 규칙을 구성하는 <EM>대신</EM>, 하나 이상의 변환 규칙을 Enterprise Voice 트렁크 구성에 연결하는 기능을 사용할 수 있습니다. 트렁크 피어에 대한 변환 규칙을 구성한 경우 변환 규칙을 Enterprise Voice 트렁크 구성과 연결하지 마십시오. 두 규칙이 충돌할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d3e60-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="d3e60-108">다음 방법 중 하나를 사용하여 변환 규칙을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e60-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="d3e60-109">**변환 규칙 작성** 도구를 사용 하 여 시작 번호, 길이, 제거할 숫자 및 추가할 숫자에 대 한 값을 지정한 다음 Lync Server 제어판에서 해당 일치 패턴 및 변환 규칙을 생성 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e60-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="d3e60-110">수동으로 정규식을 작성하여 일치 패턴 및 변환 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e60-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3e60-111">정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식"을 참조 하십시오 <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> .</span><span class="sxs-lookup"><span data-stu-id="d3e60-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d3e60-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d3e60-112">In This Section</span></span>

  - [<span data-ttu-id="d3e60-113">Lync Server 2013의 변환 규칙 작성 도구를 사용 하 여 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d3e60-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="d3e60-114">Lync Server 2013에서 수동으로 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d3e60-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3e60-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3e60-115">See Also</span></span>


[<span data-ttu-id="d3e60-116">Lync Server 2013의 발신자 번호 프레젠테이션</span><span class="sxs-lookup"><span data-stu-id="d3e60-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

