---
title: 'Lync Server 2013: 네트워크 대역폭 정책 프로필 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 513bd20e9a1ecd40f061c4873e7da8bff4738f36
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="b9c45-102">Lync Server 2013에서 네트워크 대역폭 정책 프로필 정보 보기</span><span class="sxs-lookup"><span data-stu-id="b9c45-102">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9c45-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b9c45-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b9c45-104">호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="b9c45-105">Microsoft Lync Server 2013에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="b9c45-106">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="b9c45-107">Lync Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="b9c45-108">각 대역폭 정책 프로필을 하나 이상의 네트워크 사이트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="b9c45-109">다음 절차를 사용 하 여 대역폭 정책 프로필을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-109">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="b9c45-110">대역폭 정책 프로필을 만들거나 수정 하려면 [Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정을](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9c45-110">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="b9c45-111">대역폭 정책 프로필을 보려면</span><span class="sxs-lookup"><span data-stu-id="b9c45-111">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="b9c45-112">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b9c45-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b9c45-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9c45-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b9c45-115">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="b9c45-116">**대역폭 정책** 페이지에서 보려는 대역폭 정책 프로필을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="b9c45-117">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-117">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b9c45-118">Windows PowerShell Cmdlet을 사용 하 여 네트워크 대역폭 정책 프로필 정보 보기</span><span class="sxs-lookup"><span data-stu-id="b9c45-118">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b9c45-119">네트워크 대역폭 프로필은 Windows PowerShell 및 CsNetworkBandwidthPolicyProfile cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="b9c45-120">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b9c45-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9c45-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="b9c45-122">네트워크 대역폭 정책 프로필 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="b9c45-122">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="b9c45-123">모든 네트워크 대역폭 정책 프로필에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-123">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="b9c45-124">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c45-124">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="b9c45-125">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9c45-125">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9c45-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9c45-126">See Also</span></span>


[<span data-ttu-id="b9c45-127">Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="b9c45-127">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="b9c45-128">Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제</span><span class="sxs-lookup"><span data-stu-id="b9c45-128">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="b9c45-129">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="b9c45-129">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

