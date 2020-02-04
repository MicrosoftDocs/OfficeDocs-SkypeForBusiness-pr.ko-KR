---
title: 'Lync Server 2013: CDR 데이터 보존 지정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32eee413b25da3231d5633e89571bbc08deb1f38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="fda3e-102">Lync Server 2013에서 CDR 데이터 보존 지정</span><span class="sxs-lookup"><span data-stu-id="fda3e-102">Specifying retention of CDR data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fda3e-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fda3e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fda3e-104">기본적으로, 60 일 후에 CDR (통화 정보 기록) 데이터가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-104">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="fda3e-105">**통화 정보 기록** 페이지의 설정을 사용 하 여 오래 되거나 짧은 시간 동안 데이터를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-105">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="fda3e-106">CDR를 사용 하지 않도록 설정 하는 경우 CDR를 사용 하도록 설정 하기 전에 캡처한 데이터도 제거 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-106">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fda3e-107">동일한 일 수 동안 데이터를 보존 하도록 CDR 및 경력 (체감 품질)을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-107">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="fda3e-108">모니터링 서버 보고서 웹 페이지에서 사용할 수 있는 CDRs (통화 정보 보고서)의 각 통화에는 CDR 및 체감 품질 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-108">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="fda3e-109">CDR 및 체감 품질의 제거 기간이 서로 다른 경우 일부 통화에는 CDR 데이터만 포함 될 수 있으며, 그 외에는 체감 품질 데이터만 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-109">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="fda3e-110">CDR 데이터에 대 한 지우기 설정을 구성 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-110">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="fda3e-111">CDR 데이터 보존을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="fda3e-111">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="fda3e-112">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fda3e-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fda3e-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fda3e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fda3e-115">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="fda3e-116">**통화 정보 기록** 페이지에서 표의 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="fda3e-117">제거를 설정 하려면 **CDRs 제거 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-117">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="fda3e-118">**최대 기간 (일) 동안 CDRs 유지:** 통화 정보 기록을 보존 해야 하는 최대 일 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="fda3e-119">**최대 기간 (일)에 대 한 오류 보고 데이터 유지:** 오류 보고서를 유지 해야 하는 최대 일 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="fda3e-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fda3e-121">Windows PowerShell Cmdlet을 사용 하 여 CDR 보존 지정</span><span class="sxs-lookup"><span data-stu-id="fda3e-121">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fda3e-122">Windows PowerShell 및 Set-CsCdrConfiguration cmdlet을 사용 하 여 CDR 보존 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="fda3e-123">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fda3e-124">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fda3e-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="fda3e-125">특정 위치에 대 한 CDR 보존을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="fda3e-125">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="fda3e-126">이 명령을 사용 하 여 Redmond 사이트에 대 한 CDR 데이터를 제거 하 고, 사이트를 구성 하 여 CDR 데이터와 오류 보고 데이터를 모두 20 일 동안 유지 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-126">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="fda3e-127">여러 위치에 대 한 CDR 보존을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="fda3e-127">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="fda3e-128">이 명령은 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR 보존을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda3e-128">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="fda3e-129">자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fda3e-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fda3e-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fda3e-130">See Also</span></span>


[<span data-ttu-id="fda3e-131">Lync Server 2013의 CDR (통화 정보 기록)</span><span class="sxs-lookup"><span data-stu-id="fda3e-131">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

