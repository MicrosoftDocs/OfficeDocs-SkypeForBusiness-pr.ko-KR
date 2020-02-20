---
title: 'Lync Server 2013: 경험 수준 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7eea129439e216c3fb2542a68fc021d1e64fe14c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="3f318-102">Lync Server 2013의 경험 수준 설정 수정</span><span class="sxs-lookup"><span data-stu-id="3f318-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f318-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3f318-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3f318-p101">QoE(체감 품질) 데이터는 기본적으로 60일 후에 삭제됩니다. **체감 품질 데이터** 페이지의 설정을 사용하여 데이터를 60일 이상 보존하거나 60일보다 짧게 보존할 수 있습니다. QoE를 사용하지 않도록 설정한 경우 QoE를 사용하도록 설정하기 전에 캡처한 데이터도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f318-p102">CDR(통화 정보 기록) 및 QoE의 데이터 보존 일수는 동일하게 구성해야 합니다. 모니터링 보고서 홈 페이지에 제공되는 CDR(통화 정보 보고서)의 각 통화에는 CDR 및 QoE 정보가 포함됩니다. CDR 및 QoE의 삭제 기간이 다를 경우 일부 통화에는 CDR 데이터만 포함되고 또 다른 일부 통화에는 QoE 데이터만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="3f318-110">다음 절차는 QoE 데이터에 대한 삭제 설정을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="3f318-111">Lync Server 제어판을 사용 하 여 QoE 데이터의 보존을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="3f318-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3f318-112">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3f318-113">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f318-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3f318-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3f318-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f318-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3f318-116">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **체감 품질 데이터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="3f318-117">**체감 품질 데이터** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="3f318-118">삭제를 설정하려면 **QoE 삭제 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="3f318-119">**최대 기간(일) 동안 QoE 유지**에서 QoE 데이터를 보존할 최대 일수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="3f318-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3f318-121">Windows PowerShell Cmdlet을 사용 하 여 QoE 보존 지정</span><span class="sxs-lookup"><span data-stu-id="3f318-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3f318-122">QoE 보존 설정은 Windows PowerShell 및 **remove-csqoeconfiguration** cmdlet을 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="3f318-123">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3f318-124">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f318-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="3f318-125">특정 위치에 대한 QoE 보존을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="3f318-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="3f318-126">이 명령은 Redmond 사이트에 대해 QoE 데이터 삭제를 사용하도록 설정하고 20일 동안 QoE 데이터를 유지하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="3f318-127">여러 위치에 대한 QoE 보존을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="3f318-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="3f318-128">이 명령은 조직에서 사용 중인 모든 QoE 구성 설정에 대해 QoE 보존을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f318-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="3f318-129">자세한 내용은 [remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f318-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f318-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f318-130">See Also</span></span>


[<span data-ttu-id="3f318-131">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="3f318-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

