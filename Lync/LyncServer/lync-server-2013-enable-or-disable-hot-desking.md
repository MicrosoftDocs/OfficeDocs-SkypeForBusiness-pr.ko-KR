---
title: 'Lync Server 2013: hot desking 사용 또는 사용 안 함'
description: 'Lync Server 2013: 핫 desking을 사용 하거나 사용 하지 않도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd22c9bf51078324cfe5e215bd154503c2d9b57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552434"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="f6db5-103">Lync Server 2013에서 핫 desking 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f6db5-103">Enable or disable hot desking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6db5-104">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f6db5-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f6db5-105">공통 영역 전화를 *핫-일반 전화기*로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-105">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="f6db5-106">일반 전화기를 사용 하면 사용자가 자신의 사용자 계정에 로그온 하 고, 로그온 한 후 Lync Server 기능 및 자체 사용자 프로필 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-106">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="f6db5-107">Hot desking는 클라이언트 정책을 사용 하 여 관리 되며 핫 desking를 사용 하거나 사용 하지 않도록 설정 하려면 공통 영역 전화에서 사용 하는 클라이언트 정책을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-107">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="f6db5-108">공통 영역 전화에 할당 된 회의 정책을 확인 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 공통 영역 전화 정보 보기](lync-server-2013-view-common-area-phone-information.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6db5-108">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="f6db5-109">다음과 같이 **새 CSClientPolicy** Cmdlet의 EnableHotdesking 매개 변수 또는 **csclientpolicy** cmdlet을 사용 하 여 휴대폰에서 hot desking을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-109">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="f6db5-110">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 이러한 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-110">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f6db5-111">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6db5-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="f6db5-112">Hot desking 사용</span><span class="sxs-lookup"><span data-stu-id="f6db5-112">Enabling hot desking</span></span>

  - <span data-ttu-id="f6db5-113">공통 영역 전화에 대해 핫 desking을 사용 하도록 설정 하려면 해당 휴대폰 또는 전화 모음에 할당 된 클라이언트 정책을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-113">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="f6db5-114">수정 해야 하는 정책을 식별 한 후에는 **CsClientPolicy** cmdlet을 사용 하 여 EnableHotdesking 매개 변수를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-114">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="f6db5-115">예제:</span><span class="sxs-lookup"><span data-stu-id="f6db5-115">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="f6db5-116">또는 **새 CsClientPolicy** cmdlet을 사용 하 여 핫 desking을 사용 하도록 설정 하는 새 클라이언트 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-116">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="f6db5-117">예제:</span><span class="sxs-lookup"><span data-stu-id="f6db5-117">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f6db5-118">이 정책을 만든 후에는 해당 공통 영역 전화에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-118">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="f6db5-119">자세한 내용은 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Lync Server 2013의 정책을 공통 영역 전화에 할당</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6db5-119">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="f6db5-120">Hot desking 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f6db5-120">Disabling hot desking</span></span>

  - <span data-ttu-id="f6db5-121">공통 영역 전화에 대해 핫 desking를 사용 하지 **않도록 설정 하려면** EnableHotdesking 매개 변수를 기본값인 False로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db5-121">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="f6db5-122">예제:</span><span class="sxs-lookup"><span data-stu-id="f6db5-122">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="f6db5-123">자세한 내용은 [새-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 및 [설정-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6db5-123">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

