---
title: 'Lync Server 2013: 대역폭 정책 프로필 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66f2489b0ffaabc3744d92b38bcbf71ffcd84591
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="58127-102">Lync Server 2013에서 대역폭 정책 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="58127-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58127-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="58127-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="58127-p101">*대역폭 정책*은 실시간 오디오 및 비디오 형식의 대역폭 사용량에 대한 제한을 정의하며, 통화 허용 제어에 대한 여러 네트워크 사이트에 적용할 수 있는 *대역폭 정책 프로필*에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58127-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="58127-106">CAC 배포에서 설정 해야 하는 대역폭 제한에 대 한 지침은 계획 설명서에서 [Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-call-admission-control.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58127-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="58127-107">대역폭 정책 및 정책 프로필로 작업 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58127-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="58127-108">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="58127-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="58127-109">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="58127-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="58127-110">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="58127-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="58127-111">Get-csnetworkbandwidthpolicyprofile을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="58127-112">다음 절차에서 만들어진 예 정책은 전체 오디오 트래픽, 개별 오디오 세션, 전체 비디오 트래픽 및 개별 비디오 세션에 대한 제한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="58127-113">예를 들어, 5Mb\_링크 대역폭 정책 프로필은 다음과 같은 제한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="58127-114">오디오 제한: 2,000kbps</span><span class="sxs-lookup"><span data-stu-id="58127-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="58127-115">오디오 세션 제한: 200kbps</span><span class="sxs-lookup"><span data-stu-id="58127-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="58127-116">비디오 제한: 1,400kbps</span><span class="sxs-lookup"><span data-stu-id="58127-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="58127-117">비디오 세션 제한: 700kbps</span><span class="sxs-lookup"><span data-stu-id="58127-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="58127-p103">최소 오디오 세션 제한 값은 40kbps이며, 최소 비디오 세션 제한 값은 100kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="58127-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="58127-120">관리 셸을 사용하여 대역폭 정책 프로필을 만들려면</span><span class="sxs-lookup"><span data-stu-id="58127-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="58127-121">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="58127-p104">만들려는 각 대역폭 정책 프로필에 대해 New-CsNetworkBandwidthPolicyProfile cmdlet을 실행합니다. 예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="58127-124">Lync Server 제어판을 사용하여 대역폭 정책 프로필을 만들려면</span><span class="sxs-lookup"><span data-stu-id="58127-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="58127-125">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="58127-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="58127-126">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58127-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="58127-127">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="58127-128">**정책 프로필** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="58127-129">**새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-129">Click **New**.</span></span>

5.  <span data-ttu-id="58127-130">**새 프로필 정책** 페이지에서 **이름**을 클릭한 후 대역폭 정책 프로필에 대한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="58127-131">**오디오 제한**을 클릭하고 결합된 모든 오디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="58127-132">**오디오 세션 제한**을 클릭하고 각 개별 오디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="58127-133">**비디오 제한**을 클릭하고 결합된 모든 비디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="58127-134">**비디오 세션 제한**을 클릭하고 각 개별 비디오 세션에 허용할 최대 kbps를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="58127-135">경우에 따라 **설명**을 클릭하고 이 대역폭 정책 프로필을 설명하는 추가 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="58127-136">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-136">Click **Commit**.</span></span>

12. <span data-ttu-id="58127-137">토폴로지에 대한 대역폭 정책 프로필 만들기를 종료하려면 다른 대역폭 정책 프로필에 대한 설정을 사용하여 4-11단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="58127-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

