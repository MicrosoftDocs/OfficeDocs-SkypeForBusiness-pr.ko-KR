---
title: 'Lync Server 2013: 장치 업데이트 로그 파일에 대 한 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d75086f0532205c2897f7e86d49f50072aaa89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="a4827-102">Lync Server 2013에서 장치 업데이트 로그 파일에 대 한 설정 수정</span><span class="sxs-lookup"><span data-stu-id="a4827-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4827-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a4827-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a4827-104">Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 조직에 디바이스 업데이트 정보가 기록 되는 방식에 대 한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="a4827-105">다음 표에서는 수정할 수 있는 설정 및 설정을 수정 하는 데 사용 되는 도구를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="a4827-106">로그 설정은 전체적으로 변경 하거나 사이트별로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4827-107">변경 하려면</span><span class="sxs-lookup"><span data-stu-id="a4827-107">To change</span></span></th>
<th><span data-ttu-id="a4827-108">사용</span><span class="sxs-lookup"><span data-stu-id="a4827-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4827-109">로그 파일의 최대 크기 (바이트)</span><span class="sxs-lookup"><span data-stu-id="a4827-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="a4827-110">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="a4827-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a4827-111">또는</span><span class="sxs-lookup"><span data-stu-id="a4827-111">-or-</span></span></p>
<p><span data-ttu-id="a4827-112">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a4827-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4827-113">캐시에 보유할 수 있는 정보의 최대 양 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="a4827-114">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="a4827-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a4827-115">또는</span><span class="sxs-lookup"><span data-stu-id="a4827-115">-or-</span></span></p>
<p><span data-ttu-id="a4827-116">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a4827-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4827-117">로그 파일에 캐시 된 정보를 쓰는 빈도 (분)</span><span class="sxs-lookup"><span data-stu-id="a4827-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="a4827-118">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="a4827-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a4827-119">또는</span><span class="sxs-lookup"><span data-stu-id="a4827-119">-or-</span></span></p>
<p><span data-ttu-id="a4827-120">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a4827-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4827-121">로그 파일 유지 기간 (일)</span><span class="sxs-lookup"><span data-stu-id="a4827-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="a4827-122">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="a4827-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a4827-123">또는</span><span class="sxs-lookup"><span data-stu-id="a4827-123">-or-</span></span></p>
<p><span data-ttu-id="a4827-124">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a4827-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4827-125">삭제 해야 하는 만료 된 파일을 확인 하는 시간 (일)</span><span class="sxs-lookup"><span data-stu-id="a4827-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="a4827-126">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a4827-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4827-127">허용할 로그 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="a4827-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="a4827-128">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a4827-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4827-129">유지할 로그 파일 형식</span><span class="sxs-lookup"><span data-stu-id="a4827-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="a4827-130">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a4827-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="a4827-131">Lync Server 제어판을 사용 하 여 로깅 설정을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="a4827-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a4827-132">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a4827-133">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4827-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a4827-134">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 로그 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="a4827-135">**장치 로그 구성** 페이지에서 변경 하려는 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="a4827-136">**로그 설정 편집** 대화 상자에서 다음 설정 중 하나를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="a4827-137">**최대 파일 크기 (바이트)**   로그 파일을 제거 하기 전까지 될 수 있는 최대 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="a4827-138">기본값은 1024000 바이트 (1 MB)입니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="a4827-139">**최대 캐시 크기 (바이트)**   캐시를 삭제 하 고 데이터를 로그 파일에 기록 하기 전에 로그 파일 캐시에 보유할 수 있는 최대 정보 양 (바이트)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="a4827-140">기본값은 512000 바이트 (0.5 MB)입니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="a4827-141">**캐시 플러시 시간 (분) (1-60)**   은 로그 파일 캐시에 저장 된 정보를 실제 로그 파일에 쓰는 빈도 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="a4827-142">데이터가 기록 된 후 캐시가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="a4827-143">기본값은 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="a4827-144">**로그 파일 유지 일 수 (1-365)**   로그 파일을 제거 하기 전에 보관할 날짜 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="a4827-145">기본값은 10 일입니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="a4827-146">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a4827-147">Windows PowerShell Cmdlet을 사용 하 여 로깅 설정 변경</span><span class="sxs-lookup"><span data-stu-id="a4827-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a4827-148">Windows PowerShell 및 **Set-CsDeviceUpdateConfiguration** cmdlet을 사용 하 여 장치 업데이트 로그 파일 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="a4827-149">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4827-150">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4827-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="a4827-151">다음 예제에서는 **Set-CsDeviceUpdateConfiguration** 를 사용 하 여 설정을 수정할 수 있는 몇 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="a4827-152">최대 로그 파일 크기 및 로그 정리 간격 수정</span><span class="sxs-lookup"><span data-stu-id="a4827-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="a4827-153">다음 명령은 Redmond 사이트에 적용 된 장치 업데이트 로그 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="a4827-154">이 예제에서는 최대 로그 파일 크기가 204800 바이트로 설정 되 고 로그 정리 간격은 14 일로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="a4827-155">로그 정리 시간 (일) 수정</span><span class="sxs-lookup"><span data-stu-id="a4827-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="a4827-156">이 명령은 Redmond 사이트의 로그 정리 시간을 3:00 AM으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4827-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="a4827-157">자세한 내용은 [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4827-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

