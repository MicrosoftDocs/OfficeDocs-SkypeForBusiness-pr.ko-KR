---
title: 'Lync Server 2013: 통화 허용 제어 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20cd0f7792f8db2cf1b2d817bfe79ed6d6b16fce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="4c243-102">Lync Server 2013에서 통화 허용 제어 사용</span><span class="sxs-lookup"><span data-stu-id="4c243-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c243-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4c243-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4c243-104">CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="4c243-105">CAC 네트워크를 구성한 후에는 CAC가 대역폭 제한을 적용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="4c243-106">Lync Server 제어판을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="4c243-107">Lync Server 제어판에서 CAC를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="4c243-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4c243-108">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c243-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4c243-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c243-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4c243-111">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **전역**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="4c243-112">**전역** 페이지에서 **전역** 구성을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c243-113">Microsoft Lync Server 2013 배포에 대해 하나의 네트워크만 구성할 수 있으므로 목록에 두 개 이상의 네트워크 구성이 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="4c243-114">전역 구성의 이름은 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="4c243-115">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4c243-116">**전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택한 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="4c243-117">**커밋을**클릭 하면 구성 테스트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-117">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="4c243-118">**전역 설정 편집** 대화 상자가 닫히고 **전역** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-118">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="4c243-119">네트워크 구성에서 오류 또는 불일치가 검색 되어 제대로 작동 하지 않는 경우 (예: 모든 지역이 서로 다른 지역 경로를 통해 모든 지역에 연결 되어 있지 않은 경우) 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-119">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="4c243-120">네트워크 구성을 변경할 경우 전역 구성을 열고 **커밋을**클릭 하 여 유효성 검사를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-120">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="4c243-121">CAC를 먼저 사용 하지 않도록 설정할 필요는 없습니다. 확인란을 선택한 상태로 두고 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-121">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="4c243-122">구성을 변경 하지 않고 언제 든 지이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c243-122">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c243-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c243-123">See Also</span></span>


[<span data-ttu-id="4c243-124">Lync Server 2013의 통화 허용 제어 개요</span><span class="sxs-lookup"><span data-stu-id="4c243-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="4c243-125">Lync Server 2013의 통화 허용 제어 서비스 계획</span><span class="sxs-lookup"><span data-stu-id="4c243-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="4c243-126">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="4c243-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="4c243-127">Get-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="4c243-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="4c243-128">Set-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="4c243-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="4c243-129">제거-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="4c243-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

