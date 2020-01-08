---
title: 'Lync Server 2013: 네트워크 대역폭 정책 프로필 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c33f781e8818dbefa3dc37b3f17c789099e6add
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="0a0d7-102">Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제</span><span class="sxs-lookup"><span data-stu-id="0a0d7-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a0d7-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a0d7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a0d7-104">호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="0a0d7-105">Microsoft Lync Server 2013에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="0a0d7-106">전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="0a0d7-107">Lync Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="0a0d7-108">네트워크 대역폭 정책 프로필을 삭제 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="0a0d7-109">네트워크 대역폭 정책 프로필을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정을](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="0a0d7-110">대역폭 정책 프로필을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="0a0d7-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="0a0d7-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a0d7-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a0d7-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a0d7-114">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="0a0d7-115">**대역폭 정책** 페이지에서 삭제 하려는 대역폭 정책 프로필을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a0d7-116">한 번에 여러 프로필을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-116">You can delete more than one profile at a time.</span></span> <span data-ttu-id="0a0d7-117">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-117">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="0a0d7-118">또는 모든 프로필을 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-118">Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="0a0d7-119">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0a0d7-120">네트워크 사이트와 연결 된 대역폭 정책 프로필은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="0a0d7-121">프로필을 삭제 하려면 먼저 네트워크 사이트와의 연결을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="0a0d7-122">네트워크 사이트를 수정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a0d7-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a0d7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a0d7-123">See Also</span></span>


[<span data-ttu-id="0a0d7-124">Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="0a0d7-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="0a0d7-125">Lync Server 2013에서 네트워크 대역폭 정책 프로필 정보 보기</span><span class="sxs-lookup"><span data-stu-id="0a0d7-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="0a0d7-126">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="0a0d7-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="0a0d7-127">제거-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="0a0d7-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

