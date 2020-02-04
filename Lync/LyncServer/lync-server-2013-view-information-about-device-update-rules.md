---
title: 'Lync Server 2013: 장치 업데이트 규칙에 대 한 정보 보기'
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
ms.openlocfilehash: 6e26b67aba2bf792b3248e7771f938a8bced1668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="1d6ac-102">Lync Server 2013에서 장치 업데이트 규칙에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1d6ac-102">View information about Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d6ac-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1d6ac-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1d6ac-104">업데이트를 적용 하는 디바이스의 유형, 모델 및 브랜드를 포함 하 여 이미 가져온 장치 업데이트 규칙에 대 한 세부 정보를 확인 합니다. 업데이트 버전 및 형식 업데이트에 대 한 로캘 및 풀을 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="1d6ac-105">정보는 승인, 배포 (승인), 회수 (복원), 사용 하지 않기로 결정 한 모든 가져온 장치 업데이트 규칙에 대해 사용할 수 있습니다 (재설정).</span><span class="sxs-lookup"><span data-stu-id="1d6ac-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="1d6ac-106">Lync Server 제어판 또는 Windows PowerShell에서이 정보에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d6ac-107">규칙 가져오기, 승인, 다시 설정, 복원 및 제거 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-device-update-rules.md">Lync Server 2013의 장치 업데이트 규칙</A>에 나열 된 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="1d6ac-108">Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="1d6ac-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1d6ac-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d6ac-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d6ac-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d6ac-112">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 업데이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="1d6ac-113">가져온 규칙은 **장치 업데이트** 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1d6ac-114">Windows PowerShell Cmdlet을 사용 하 여 디바이스 업데이트 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="1d6ac-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1d6ac-115">모든 장치 업데이트 규칙에 대 한 자세한 내용은 Windows PowerShell 및 **CsDeviceUpdateRule** cmdlet을 사용 하 여 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="1d6ac-116">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d6ac-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="1d6ac-118">모든 장치 업데이트 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="1d6ac-118">To view all your device update rules</span></span>

  - <span data-ttu-id="1d6ac-119">다음 명령은 조직에서 사용 하도록 구성 된 모든 장치 업데이트 규칙에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="1d6ac-120">명령은 각 장치 업데이트 규칙에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
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

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="1d6ac-121">특정 웹 서버의 모든 장치 업데이트 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="1d6ac-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="1d6ac-122">특정 컴퓨터에서 디바이스 업데이트 규칙을 보려면 Filter 매개 변수 다음에 서버 Id와 와일드 카드 문자 (\*)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="1d6ac-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6ac-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="1d6ac-124">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목을 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="1d6ac-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

