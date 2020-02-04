---
title: 'Lync Server 2013: 조직의 디바이스에 대 한 소프트웨어 업데이트 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="46c7d-102">Lync Server 2013의 장치 소프트웨어 업데이트 보기</span><span class="sxs-lookup"><span data-stu-id="46c7d-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c7d-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="46c7d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="46c7d-104">Lync Server 2013에서 장치 업데이트 웹 서비스를 사용 하 여 조직의 장치에 대 한 소프트웨어 업데이트를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="46c7d-105">이러한 업데이트는에서 [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)Microsoft 지원 웹 사이트의 .cab (캐비닛) 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="46c7d-106">.Cab 파일을 다운로드 한 후에는 **가져오기-CSDeviceUpdate** cmdlet을 실행 하 여 .cab 파일에서 장치 업데이트 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="46c7d-107">**가져오기-csdeviceupdate** cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [가져오기-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46c7d-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="46c7d-108">조직에 새 업데이트를 배포 하기 전에 테스트 장치에서 올바르게 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="46c7d-109">UC 장치용 소프트웨어 업데이트를 보려면</span><span class="sxs-lookup"><span data-stu-id="46c7d-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="46c7d-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="46c7d-111">의 Microsoft 지원 웹 사이트 [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)에서 Lync Server 2013 컴퓨터의 위치 (예를 들어 C:\\업데이트\\를 다운로드 하는 경우)에 .cab 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="46c7d-112">다음 cmdlet 중 하나를 실행 하 여 C\\:\\업데이트 항목 업데이트 .cab 파일에서 장치 업데이트 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="46c7d-113">.Cab 파일이 업데이트 될 서비스를 실행 하는 컴퓨터와 같은 컴퓨터에 있는 경우 (서비스: Redmond-websvc-2) 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="46c7d-114">.Cab 파일이 업데이트 되는 서비스를 실행 하는 컴퓨터가 아닌 다른 컴퓨터에 있는 경우 (서비스: Redmond-websvc-3) 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="46c7d-115">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="46c7d-116">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46c7d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="46c7d-117">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="46c7d-118">**장치 업데이트** 페이지의 목록에서 업데이트를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="46c7d-119">**보류 중인 업데이트를 취소 합니다.**</span><span class="sxs-lookup"><span data-stu-id="46c7d-119">**Cancel a pending update.**</span></span> <span data-ttu-id="46c7d-120">선택한 업데이트가 조직의 장치에 배포 되지 않도록 하려면 **동작** 메뉴를 클릭 한 다음 **보류 중인 업데이트 취소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="46c7d-121">**업데이트를 승인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="46c7d-121">**Approve an update.**</span></span> <span data-ttu-id="46c7d-122">선택한 업데이트를 조직의 장치에 배포할 수 있도록 하려면 **동작** 메뉴를 클릭 한 다음 **승인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="46c7d-123">**업데이트를 복원 합니다.**</span><span class="sxs-lookup"><span data-stu-id="46c7d-123">**Restore an update.**</span></span> <span data-ttu-id="46c7d-124">이전에 승인 된 업데이트를 조직의 장치에 배포할 수 있도록 하려면 **동작** 메뉴를 클릭 한 다음 **복원을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c7d-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46c7d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46c7d-125">See Also</span></span>


[<span data-ttu-id="46c7d-126">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="46c7d-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

