---
title: 'Lync Server 2013: 정규화 규칙 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9406e4fa7445242ae3f112ebfb772713d9d2219c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="2df11-102">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="2df11-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2df11-103">_**마지막으로 수정한 주제:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="2df11-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="2df11-104">Lync Server 2013 정규화 규칙은 .NET Framework 정규식을 사용 하 여 전화를 거는 전화 번호를 전자 164 형식으로 변환 합니다. 즉, 정규화 규칙은 사용자가 전화를 거는 전화 번호를 사용 하 여 Lync Server에서 내부적으로 사용 하는 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df11-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="2df11-105">각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df11-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="2df11-106">정규화 규칙에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2df11-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="2df11-107">정규식을 작성 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 정규식"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2df11-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="2df11-108">다음 방법 중 하나를 사용 하 여 정규화 규칙을 정의 하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df11-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="2df11-109">**정규화 규칙 작성** 도구를 사용 하 여 시작 숫자, 길이, 제거할 숫자, 추가할 숫자에 대 한 값을 지정한 다음 Lync Server 제어판에서 해당 하는 일치 패턴 및 번역 규칙을 생성 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df11-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="2df11-110">정규식을 수동으로 작성 하 여 일치 패턴 및 번역 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df11-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2df11-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2df11-111">In This Section</span></span>

  - [<span data-ttu-id="2df11-112">Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="2df11-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="2df11-113">Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="2df11-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2df11-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2df11-114">See Also</span></span>


[<span data-ttu-id="2df11-115">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="2df11-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="2df11-116">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="2df11-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

