---
title: 'Lync Server 2013: 통화 허용 제어 기능 설정'
description: 'Lync Server 2013: 통화 허용 제어를 사용 하도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bd352d407c3b14ac90a76fd6d53ccb312cab7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551584"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1b4d9-103">Lync Server 2013에서 통화 허용 제어 사용</span><span class="sxs-lookup"><span data-stu-id="1b4d9-103">Enable call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b4d9-104">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1b4d9-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1b4d9-105">통화 허용 제어 배포에 대한 네트워크 설정을 구성한 후 CAC를 사용하도록 설정하여 대역폭 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="1b4d9-106">자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-106">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="1b4d9-107">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="1b4d9-107">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="1b4d9-108">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="1b4d9-108">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="1b4d9-109">Get-csnetworkconfiguration을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-109">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="1b4d9-110">관리 셸을 사용하여 통화 허용 제어를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1b4d9-110">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="1b4d9-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1b4d9-p101">Set-CsNetworkConfiguration cmdlet을 실행하여 네트워크에서 CAC를 사용하도록 설정합니다. 예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="1b4d9-114">네트워크에서 CAC를 사용하지 않도록 설정하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-114">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="1b4d9-115">Lync Server 제어판을 사용하여 통화 허용 제어를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1b4d9-115">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1b4d9-116">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b4d9-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="1b4d9-118">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-118">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="1b4d9-119">**전역** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-119">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="1b4d9-120">목록에서 **전역**을 클릭한 다음 **편집** 메뉴에서 **세부 정보 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-120">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="1b4d9-121">**전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-121">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b4d9-122">배포 전체에서 통화 허용 제어를 사용하지 않도록 설정하려면 이 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-122">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="1b4d9-123">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

