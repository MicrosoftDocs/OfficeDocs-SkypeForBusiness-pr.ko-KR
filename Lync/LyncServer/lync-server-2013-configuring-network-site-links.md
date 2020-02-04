---
title: 'Lync Server 2013: 네트워크 사이트 링크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="2c25e-102">Lync Server 2013에서 네트워크 사이트 링크 구성</span><span class="sxs-lookup"><span data-stu-id="2c25e-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c25e-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2c25e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2c25e-104">CAC (call 허용 제어) 구성 내에서 직접 연결 된 사이트 간의 대역폭 제한을 정의 하는 네트워크 간 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="2c25e-105">네트워크 사이트에서 직접 링크를 공유 하는 경우 오디오 및 비디오 연결에 대 한 대역폭 제한이 해당 두 사이트 간에 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="2c25e-106">Lync server 제어판을 사용 하 여 네트워크 사이트 정책을 구성할 수는 없지만 Lync Server 관리 셸에서 cmdlet을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="2c25e-107">Lync Server 관리 셸에서 네트워크 사이트 링크 (사이트 간 정책 라고도 함)를 만들고, 수정 하 고, 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="2c25e-108">네트워크 사이트 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2c25e-108">To create a network site link</span></span>

1.  <span data-ttu-id="2c25e-109">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2c25e-110">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2c25e-111">명령 프롬프트에서 다음 명령을 입력 하 고 구성에 유효한 값으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="2c25e-112">이 예제에서는 Reno 및 포틀랜드 네트워크 사이트 간의 대역폭\_제한을 설정 하는 Reno 포틀랜드 이라는 새 네트워크 사이트 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="2c25e-113">네트워크 사이트 및 대역폭 정책 프로필은이 명령을 실행 하기 전에 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="2c25e-114">매개 변수 설명에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c25e-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="2c25e-115">네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색 하려면 **CsNetworkBandwidthPolicyProfile** cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="2c25e-116">자세한 내용은 Lync Server 관리 셸 설명서의 [Get-help CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c25e-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="2c25e-117">네트워크 사이트 링크를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="2c25e-117">To modify a network site link</span></span>

1.  <span data-ttu-id="2c25e-118">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2c25e-119">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2c25e-120">**Set-CsNetworkInterSitePolicy** cmdlet을 사용 하 여 지정 된 네트워크 사이트 링크의 속성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="2c25e-121">(또는 둘 다) 또는 연결 된 사이트를 수정할 수 있으며 링크와 연결 된 대역폭 정책 프로필을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="2c25e-122">다음은 Reno\_포틀랜드 라는 사이트 링크의 대역폭 정책 프로필을 수정 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="2c25e-123">자세한 매개 변수 설명은 Lync Server 관리 셸 설명서의 [CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c25e-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="2c25e-124">네트워크 사이트 링크를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="2c25e-124">To delete a network site link</span></span>

1.  <span data-ttu-id="2c25e-125">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2c25e-126">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2c25e-127">네트워크 사이트 링크를 제거 하려면 **CsNetworkInterSitePolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="2c25e-128">다음 예에서는 Reno\_포틀랜드 네트워크 사이트 링크를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="2c25e-129">매개 변수 설명에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c25e-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2c25e-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c25e-130">See Also</span></span>


[<span data-ttu-id="2c25e-131">Lync Server 2013의 통화 허용 제어 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2c25e-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="2c25e-132">새로운 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="2c25e-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="2c25e-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="2c25e-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="2c25e-134">제거-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="2c25e-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="2c25e-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="2c25e-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="2c25e-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2c25e-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

