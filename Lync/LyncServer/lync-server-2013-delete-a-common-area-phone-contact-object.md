---
title: 'Lync Server 2013: 공통 영역 전화 연락처 개체 삭제'
description: 'Lync Server 2013: 공통 영역 전화 연락처 개체를 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566604"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="eeb59-103">Lync Server 2013에서 공통 영역 전화 연락처 개체 삭제</span><span class="sxs-lookup"><span data-stu-id="eeb59-103">Delete a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eeb59-104">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="eeb59-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="eeb59-105">공통 영역 전화와 연결 된 contact 개체를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-105">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="eeb59-106">예를 들어 직원 \에 게 전화를 제거 하는 경우 해당 전화와 연결 된 연락처 개체를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-106">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="eeb59-107">**Move-cscommonareaphone** cmdlet은 공통 영역 전화 계정을 삭제할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-107">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="eeb59-108">이 cmdlet을 실행 하면 **move-cscommonareaphone**에서 반환 되는 공통 영역 전화 목록에서 전화가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-108">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="eeb59-109">또한 해당 전화와 연결 된 contact 개체가 Active Directory 도메인 서비스에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-109">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="eeb59-110">**Move-cscommonareaphone** 을 사용 하 여 표시 이름, 국가 및 지역 코드와 같은 공통 요소를 가진 공통 영역 전화 또는 모든 공통 영역 전화를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-110">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="eeb59-111">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-111">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eeb59-112">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="eeb59-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="eeb59-113">지정 된 공통 영역 전화 제거</span><span class="sxs-lookup"><span data-stu-id="eeb59-113">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="eeb59-114">다음 명령은 SIP 주소 sip:mainlobby@litwareinc.com를 사용 하 여 공통 영역 전화를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-114">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="eeb59-115">표시 이름에 따라 공통 영역 전화 제거</span><span class="sxs-lookup"><span data-stu-id="eeb59-115">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="eeb59-116">이 명령은 표시 이름에 문자열 값 "빌딩 14"가 포함 된 공통 영역 전화를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-116">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="eeb59-117">국가 및 지역 번호에 따라 공통 영역 전화 제거</span><span class="sxs-lookup"><span data-stu-id="eeb59-117">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="eeb59-118">이 명령은 미국 (국가 코드 1) 및 지역 번호 425에 대 한 공통 영역 전화를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb59-118">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="eeb59-119">자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="eeb59-119">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eeb59-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeb59-120">See Also</span></span>


[<span data-ttu-id="eeb59-121">Move-cscommonareaphone</span><span class="sxs-lookup"><span data-stu-id="eeb59-121">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

