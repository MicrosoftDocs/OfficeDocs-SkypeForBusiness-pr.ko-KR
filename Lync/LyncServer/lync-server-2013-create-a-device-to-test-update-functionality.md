---
title: 'Lync Server 2013: 업데이트 기능을 테스트할 장치 만들기'
description: 'Lync Server 2013: 업데이트 기능을 테스트할 장치를 만듭니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d45d8970dc72abc8ea6095c879272394e34c54d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542174"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="4f9be-103">Lync Server 2013에서 업데이트 기능을 테스트할 장치 만들기</span><span class="sxs-lookup"><span data-stu-id="4f9be-103">Create a device to test update functionality in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f9be-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4f9be-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4f9be-105">테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-105">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="4f9be-106">장치를 전역적으로 (전체 Lync Server 환경에서) 또는 단일 사이트 내에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-106">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="4f9be-107">MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-107">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="4f9be-108">추가 하는 장치는 Lync Server 제어판의 **테스트 장치** 페이지에 있는 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-108">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="4f9be-109">테스트 장치를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="4f9be-109">To add a test device</span></span>

1.  <span data-ttu-id="4f9be-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f9be-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f9be-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4f9be-112">왼쪽 탐색 모음에서 **클라이언트**, **테스트 장치**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-112">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="4f9be-113">**새로 만들기**를 클릭 한 다음 **전역 테스트 장치나** **사이트 테스트 장치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-113">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="4f9be-114">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-114">Do one of the following:</span></span>
    
      - <span data-ttu-id="4f9be-115">**전역 테스트 장치**를 클릭 한 경우 다음 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-115">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="4f9be-116">**사이트 테스트 장치**를 클릭 한 경우 사용 가능한 사이트 목록에서 사이트를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-116">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="4f9be-117">**새 테스트 장치**에서 장치 **이름**에 장치의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-117">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="4f9be-118">**식별자 유형에**서 **MAC 주소** 또는 **일련 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-118">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="4f9be-119">**고유 식별자** 상자에 장치의 MAC 주소나 일련 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-119">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="4f9be-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4f9be-121">Windows PowerShell Cmdlet을 사용 하 여 테스트 장치 만들기</span><span class="sxs-lookup"><span data-stu-id="4f9be-121">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4f9be-122">Windows PowerShell 및 New-CsTestDevice cmdlet을 사용 하 여 테스트 장치를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-122">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="4f9be-123">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4f9be-124">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f9be-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="4f9be-125">이 cmdlet을 사용 하 여 테스트 장치를 만들 때는 다음 두 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-125">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="4f9be-126">IdentifierType로 (~) 또는 서 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-126">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="4f9be-127">장치 Id를 지정할 때 범위를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-127">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="4f9be-128">전역 범위에서 새 장치를 만들려면 다음과 같은 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-128">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="4f9be-129">사이트 범위에서 테스트 장치를 만들려면 다음과 같은 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-129">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="4f9be-130">MAC 주소를 사용 하 여 테스트 장치를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4f9be-130">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="4f9be-131">이 명령은 IdentifierType으로 MAC 주소를 사용 하 여 전역 범위에서 테스트 장치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-131">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="4f9be-132">일련 번호를 사용 하 여 테스트 장치를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4f9be-132">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="4f9be-133">이 명령은 사이트 범위 (Redmond 사이트의 경우)에서 새 테스트 장치를 만들고 일련 번호를 IdentifierType으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9be-133">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="4f9be-134">자세한 내용은 [새-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f9be-134">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

