---
title: 'Lync Server 2013: 위치 정책 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="5cc3f-102">Lync Server 2013에서 위치 정책 정보 보기</span><span class="sxs-lookup"><span data-stu-id="5cc3f-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cc3f-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5cc3f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5cc3f-104">Lync Server 2013에서 위치 정책을 사용 하 여 향상 된 9-1-1 (E9--1) 기능 및 사용자 또는 연락처에 대 한 위치 설정에 관련 있는 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="5cc3f-105">위치 정책은 사용자가 E9을 사용할 수 있는지 여부를 결정 합니다 (예를 들어, 긴급 통화의 경우).</span><span class="sxs-lookup"><span data-stu-id="5cc3f-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="5cc3f-106">예를 들어 위치 정책을 사용 하 여 전화 통화를 구성 하는 번호 (예: 미국 내 911), 회사 보안에서 자동으로 알릴 지 여부, 통화를 라우팅하는 방법 등을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="5cc3f-107">Lync Server 2013 제어판의 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="5cc3f-108">Lync Server 제어판에서 위치 정책을 보고, 만들고, 수정 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="5cc3f-109">위치 정책에 대 한 정보를 보려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="5cc3f-110">위치 정책을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 만들기 또는 수정을](lync-server-2013-creating-or-modifying-a-location-policy.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="5cc3f-111">위치 정책에 대 한 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="5cc3f-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="5cc3f-112">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5cc3f-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5cc3f-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5cc3f-115">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **위치 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="5cc3f-116">**위치 정책** 페이지에서 수정 하려는 위치 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="5cc3f-117">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5cc3f-118">한 번에 한 위치 정책에 대 한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="5cc3f-119">전역 이라는 단일 정책은 기본적으로 존재 하며 삭제 하거나 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-119">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="5cc3f-120">그러나 전역 정책은 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-120">However, you can modify the Global policy.</span></span> <span data-ttu-id="5cc3f-121">이 정책은 사이트 정책 또는 사용자 단위 정책을 만들지 않는 한 모든 사용자 및 연락처에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-121">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="5cc3f-122">사용자별 정책은 특정 사용자에 게 적용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc3f-122">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5cc3f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cc3f-123">See Also</span></span>


[<span data-ttu-id="5cc3f-124">Lync Server 2013에서 위치 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5cc3f-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="5cc3f-125">Lync Server 2013에서 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="5cc3f-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="5cc3f-126">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5cc3f-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="5cc3f-127">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cc3f-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="5cc3f-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cc3f-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="5cc3f-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cc3f-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="5cc3f-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cc3f-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

