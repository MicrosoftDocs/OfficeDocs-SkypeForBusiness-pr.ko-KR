---
title: 'Lync Server 2013: 경험 수준 사용'
description: 'Lync Server 2013: 환경 품질을 사용 하도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43746227395477596ff5e39809cf819c110287ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547874"
---
# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="9a075-103">Lync Server 2013의 경험 수준 사용</span><span class="sxs-lookup"><span data-stu-id="9a075-103">Enable Quality of Experience in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a075-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9a075-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9a075-105">QoE(체감 품질)는 통화 및 세션에 포함된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 유형에 대한 정보 및 미디어의 품질을 나타내는 숫자 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="9a075-106">자세한 내용은 계획 설명서에서 [Lync Server 2013의 모니터링 계획](lync-server-2013-planning-for-monitoring.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a075-106">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="9a075-107">다음 절차를 사용하여 전체 조직이나 조직의 각 사이트에 대해 QoE를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a075-108">QoE를 사용하도록 설정하려면 먼저 모니터링 및 모니터링 백 엔드 데이터베이스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="9a075-109">자세한 내용은 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a075-109">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="9a075-110">Lync Server 제어판을 사용 하 여 QoE을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9a075-110">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9a075-111">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9a075-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a075-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a075-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9a075-114">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **체감 품질 데이터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="9a075-115">**체감 품질 데이터** 페이지의 테이블에서 적합한 컬렉션을 클릭하고 **동작**, **QoE 사용**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-115">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a075-116">Windows PowerShell Cmdlet을 사용 하 여 QoE 사용</span><span class="sxs-lookup"><span data-stu-id="9a075-116">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9a075-117">Windows PowerShell 및 **remove-csqoeconfiguration** cmdlet을 사용 하 여 QoE을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-117">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="9a075-118">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9a075-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a075-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="9a075-120">단일 위치에서 QoE를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9a075-120">To enable QoE for a single location</span></span>

  - <span data-ttu-id="9a075-121">QoE를 사용하도록 설정하려면 EnableQoE 매개 변수를 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="9a075-122">단일 위치에서 QoE를 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9a075-122">To disable QoE for a single location</span></span>

  - <span data-ttu-id="9a075-p105">QoE를 사용하지 않도록 설정하려면 EnableQoE 매개 변수를 False($False)로 설정합니다. 이 경우 모니터링이 제거되지는 않습니다. 다만 컬렉션과 QoE 데이터 저장소가 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="9a075-126">단일 명령을 사용하여 여러 위치에서 QoE를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9a075-126">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="9a075-127">다음 명령을 사용하면 조직에서 현재 사용 중인 모든 QoE 구성 설정에 대해 QoE를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a075-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="9a075-128">자세한 내용은 [remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a075-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a075-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a075-129">See Also</span></span>


[<span data-ttu-id="9a075-130">Lync Server 2013의 모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="9a075-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="9a075-131">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="9a075-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

