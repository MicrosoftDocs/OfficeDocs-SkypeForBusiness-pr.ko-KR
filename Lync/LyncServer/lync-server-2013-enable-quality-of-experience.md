---
title: 'Lync Server 2013: 환경 품질 사용'
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
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="d74ac-102">Lync Server 2013에서 환경 품질 사용</span><span class="sxs-lookup"><span data-stu-id="d74ac-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d74ac-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d74ac-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d74ac-104">환경 품질 (체감 품질)은 통화 및 세션과 관련 된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 형식에 대 한 미디어 품질과 정보를 표시 하는 숫자 데이터를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="d74ac-105">자세한 내용은 계획 설명서의 [Lync Server 2013에서 모니터링 계획 수립](lync-server-2013-planning-for-monitoring.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d74ac-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="d74ac-106">조직의 전체 조직 또는 각 사이트에 대해 체감 품질을 사용 하도록 설정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d74ac-107">체감 품질을 사용 하도록 설정 하려면 먼저 모니터링과 모니터링 백 엔드 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="d74ac-108">자세한 내용은 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d74ac-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="d74ac-109">Lync Server 제어판을 사용 하 여 체감 품질을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d74ac-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d74ac-110">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="d74ac-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d74ac-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d74ac-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d74ac-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="d74ac-114">**경력 데이터** 페이지에서 테이블의 적절 한 컬렉션을 클릭 하 고 **작업**을 클릭 한 다음 **체감 품질 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d74ac-115">Windows PowerShell Cmdlet을 사용 하 여 체감 품질 사용</span><span class="sxs-lookup"><span data-stu-id="d74ac-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d74ac-116">Windows PowerShell 및 **Set-CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="d74ac-117">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d74ac-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d74ac-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="d74ac-119">단일 위치에 대해 체감 품질을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d74ac-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="d74ac-120">체감 품질을 사용 하도록 설정 하려면 EnableQoE 매개 변수를 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="d74ac-121">단일 위치에 대해 체감 품질를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d74ac-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="d74ac-122">체감 품질를 사용 하지 않으려면 EnableQoE 매개 변수를 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-122">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="d74ac-123">이는 모니터링을 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-123">This does not uninstall monitoring.</span></span> <span data-ttu-id="d74ac-124">체감 품질 데이터의 컬렉션 및 저장소를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-124">It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="d74ac-125">단일 명령을 사용 하 여 여러 위치에서 체감 품질을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d74ac-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="d74ac-126">이 명령은 현재 조직에서 사용 중인 모든 체감 품질 구성 설정에 대해 체감 품질을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74ac-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="d74ac-127">자세한 내용은 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d74ac-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d74ac-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d74ac-128">See Also</span></span>


[<span data-ttu-id="d74ac-129">Lync Server 2013의 모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="d74ac-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="d74ac-130">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="d74ac-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

