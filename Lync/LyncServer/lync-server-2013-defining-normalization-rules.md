---
title: 'Lync Server 2013: 정규화 규칙 정의'
description: 'Lync Server 2013: 정규화 규칙을 정의 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542044"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="8ae36-103">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="8ae36-103">Defining normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ae36-104">_**마지막으로 수정 된 항목:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="8ae36-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="8ae36-105">Lync Server 2013 정규화 규칙은 .NET Framework 정규식을 사용 하 여 전화를 걸고 있는 전화 번호를 E. 164 형식으로 변환 합니다. 즉, 정규화 규칙은 사용자가 건 전화 번호를 가져오고 해당 번호를 Lync Server에서 내부적으로 사용 하는 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae36-105">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="8ae36-106">각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae36-106">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="8ae36-107">정규화 규칙에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ae36-107">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="8ae36-108">정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="8ae36-108">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="8ae36-109">다음 방법 중 하나를 사용하여 정규화 규칙을 정의하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae36-109">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="8ae36-110">**정규화 규칙 작성** 도구를 사용 하 여 시작 번호, 길이, 제거할 숫자 및 추가할 숫자에 대 한 값을 지정한 다음 Lync Server 제어판에서 해당 일치 패턴 및 변환 규칙을 생성 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae36-110">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="8ae36-111">수동으로 정규식을 작성하여 일치 패턴 및 변환 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae36-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ae36-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8ae36-112">In This Section</span></span>

  - [<span data-ttu-id="8ae36-113">Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ae36-113">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="8ae36-114">Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8ae36-114">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ae36-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ae36-115">See Also</span></span>


[<span data-ttu-id="8ae36-116">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="8ae36-116">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="8ae36-117">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="8ae36-117">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

