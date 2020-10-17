---
title: 'Lync Server 2013: 장치 업데이트 규칙에 대 한 정보 보기'
description: 'Lync Server 2013: 장치 업데이트 규칙에 대 한 정보를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4aecfd0dd778b576ea4a672e550f9e27d7ca463e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569634"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="01f1b-103">Lync Server 2013의 장치 업데이트 규칙에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="01f1b-103">View information about Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f1b-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="01f1b-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="01f1b-105">업데이트를 적용할 장치의 유형, 모델 및 브랜드를 포함 하 여 이미 가져온 장치 업데이트 규칙에 대 한 세부 정보를 확인 합니다. 업데이트의 버전 및 유형 업데이트에 대 한 로캘 및 풀을 사용할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-105">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="01f1b-106">가져온 모든 장치 업데이트 규칙, 즉 승인 보류 중 (승인 됨), 회수 (복원 됨) 및 사용 하지 않기로 결정 한 (다시 설정)에 대 한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-106">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="01f1b-107">Lync Server 제어판 또는 Windows PowerShell에서이 정보에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-107">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01f1b-108">규칙 가져오기, 승인, 다시 설정, 복원 및 제거 방법에 대 한 자세한 내용은 <A href="lync-server-2013-device-update-rules.md">Lync Server 2013의 장치 업데이트 규칙</A>에 나열 된 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="01f1b-108">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="01f1b-109">Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="01f1b-109">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="01f1b-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="01f1b-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="01f1b-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="01f1b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="01f1b-113">왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **장치 업데이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-113">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="01f1b-114">가져온 규칙은 **장치 업데이트** 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-114">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="01f1b-115">Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="01f1b-115">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="01f1b-116">또한 Windows PowerShell 및 **get-csdeviceupdaterule** cmdlet을 사용 하 여 모든 장치 업데이트 규칙에 대 한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-116">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="01f1b-117">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01f1b-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="01f1b-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="01f1b-119">모든 장치 업데이트 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="01f1b-119">To view all your device update rules</span></span>

  - <span data-ttu-id="01f1b-120">다음 명령은 조직에서 사용 하도록 구성 된 모든 장치 업데이트 규칙에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-120">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="01f1b-121">이 명령은 각 장치 업데이트 규칙에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f1b-121">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="01f1b-122">특정 웹 서버에서 모든 장치 업데이트 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="01f1b-122">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="01f1b-123">특정 컴퓨터에서 장치 업데이트 규칙을 보려면 Filter 매개 변수 다음에 서버 Id와 와일드 카드 문자 ()를 사용 합니다 \* .</span><span class="sxs-lookup"><span data-stu-id="01f1b-123">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="01f1b-124">예제:</span><span class="sxs-lookup"><span data-stu-id="01f1b-124">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="01f1b-125">자세한 내용은 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="01f1b-125">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

