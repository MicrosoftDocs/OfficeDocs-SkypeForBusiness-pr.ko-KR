---
title: 'Lync Server 2013: 네트워크 사이트 링크 구성'
description: 'Lync Server 2013: 네트워크 사이트 링크 구성'
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
ms.openlocfilehash: 68b4ecce15b8f3ba5a5717c73a8f97f8a0633b58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572934"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="ee854-103">Lync Server 2013에서 네트워크 사이트 링크 구성</span><span class="sxs-lookup"><span data-stu-id="ee854-103">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee854-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ee854-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ee854-105">CAC(통화 허용 제어) 구성 내에서 직접 연결된 사이트 간의 대역폭 제한을 정의하는 네트워크 사이트 간 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-105">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="ee854-106">네트워크 사이트에서 직접 링크를 공유하는 경우 이 두 사이트 간에 오디오 및 비디오 연결에 대한 대역폭 제한이 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-106">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="ee854-107">Lync Server 제어판을 사용 하 여 네트워크 사이트 정책을 구성할 수는 없으며 Lync Server 관리 셸에서 cmdlet을 사용 해야만이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-107">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="ee854-108">Lync Server 관리 셸에서 네트워크 사이트 링크 (네트워크 간 정책이 라고도 함)를 만들고, 수정 하 고, 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-108">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="ee854-109">네트워크 사이트 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ee854-109">To create a network site link</span></span>

1.  <span data-ttu-id="ee854-110">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-110">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ee854-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ee854-112">명령 프롬프트에서 다음 명령을 입력하여 구성에 대해 올바른 값으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-112">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="ee854-113">이 예에서는 \_ 리노 및 포틀랜드 네트워크 사이트 간에 대역폭 제한을 설정 하는 리노 포틀랜드 라는 새 네트워크 사이트 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-113">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="ee854-114">네트워크 사이트 및 대역폭 정책 프로필은 이 명령을 실행하기 전에 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-114">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="ee854-115">매개 변수에 대 한 자세한 내용은 Lync Server Management Shell 설명서의 [remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee854-115">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="ee854-116">네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색하려면 **Get-CsNetworkBandwidthPolicyProfile** cmdlet을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-116">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="ee854-117">자세한 내용은 Lync Server 관리 셸 설명서에서 [get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee854-117">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="ee854-118">네트워크 사이트 링크를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="ee854-118">To modify a network site link</span></span>

1.  <span data-ttu-id="ee854-119">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-119">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ee854-120">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ee854-121">**Set-CsNetworkInterSitePolicy** cmdlet을 사용하여 해당 네트워크 사이트 링크의 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-121">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="ee854-122">연결된 사이트 중 하나(또는 둘 다)를 수정할 수 있으며 링크와 연결된 대역폭 정책 프로필을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-122">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="ee854-123">다음은 리노 포틀랜드 라는 사이트 링크의 대역폭 정책 프로필을 수정 하는 예입니다 \_ .</span><span class="sxs-lookup"><span data-stu-id="ee854-123">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="ee854-124">매개 변수에 대 한 자세한 내용은 Lync Server Management Shell 설명서의 [remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee854-124">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="ee854-125">네트워크 사이트 링크를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="ee854-125">To delete a network site link</span></span>

1.  <span data-ttu-id="ee854-126">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-126">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ee854-127">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ee854-128">**Remove-CsNetworkInterSitePolicy** cmdlet을 사용하여 네트워크 사이트 링크를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-128">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="ee854-129">다음 예에서는 리노 \_ 포틀랜드 네트워크 사이트 링크를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-129">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="ee854-130">매개 변수에 대 한 자세한 내용은 Lync Server 관리 셸 설명서에서 [remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee854-130">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee854-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee854-131">See Also</span></span>


[<span data-ttu-id="ee854-132">Lync Server 2013의 통화 허용 제어 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ee854-132">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="ee854-133">Remove-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ee854-133">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ee854-134">Remove-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ee854-134">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ee854-135">Remove-csnetworkintersitepolicy을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee854-135">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ee854-136">Remove-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ee854-136">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ee854-137">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="ee854-137">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

