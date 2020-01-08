---
title: 'Lync Server 2013: 환경 구성 설정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 947fb50c057fdcc04fe7d1b30d25bc8f5a5f4a02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a7746-102">Lync Server 2013에서 환경 품질 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="a7746-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7746-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a7746-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a7746-104">경력 (체감 품질) 메트릭은 손실 된 네트워크 패킷 수, 배경 잡음, "지터"의 양 (패킷 지연의 차이) 등을 포함 하 여 조직에서 오디오 및 비디오 통화의 품질을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-104">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="a7746-105">이러한 메트릭은 다른 데이터 (예: 호출 정보 레코드)와는 별도로 데이터베이스에 저장 되며,이를 사용 하 여 기타 데이터 기록과 독립적으로 체감 품질를 활성화 및 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-105">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="a7746-106">Microsoft Lync Server 2013을 설치 하면 체감 품질 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="a7746-107">또한 관리자는 사이트 범위에서 사용자 지정 설정을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="a7746-108">이러한 사이트 범위 설정이 사용 될 때마다 전역 설정 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="a7746-109">예를 들어 Redmond 사이트에 대 한 사이트 범위 설정을 만드는 경우 전역 설정이 아닌 해당 설정을 사용 하 여 Redmond의 체감 품질를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="a7746-110">Lync Server 제어판 또는 [CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet 중 하나를 사용 하 여 체감 품질 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="a7746-111">Lync Server 제어판을 사용 하 여 새 설정을 만드는 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7746-112">UI 설정</span><span class="sxs-lookup"><span data-stu-id="a7746-112">UI Setting</span></span></th>
<th><span data-ttu-id="a7746-113">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7746-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="a7746-114">설명</span><span class="sxs-lookup"><span data-stu-id="a7746-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7746-115">이름</span><span class="sxs-lookup"><span data-stu-id="a7746-115">Name</span></span></p></td>
<td><p><span data-ttu-id="a7746-116">Identity</span><span class="sxs-lookup"><span data-stu-id="a7746-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="a7746-117">만들려는 설정의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-117">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="a7746-118">체감 품질 구성 설정은 사이트 범위 에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-118">QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7746-119">체감 품질 데이터 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="a7746-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="a7746-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="a7746-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="a7746-121">체감 품질 레코드를 수집 하 여 모니터링 데이터베이스에 저장할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7746-122">체감 품질 데이터 제거 사용</span><span class="sxs-lookup"><span data-stu-id="a7746-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="a7746-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="a7746-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="a7746-124"><strong>최대 기간에 대해 체감 품질 데이터 유지 (days)</strong> 속성에 정의 된 기간이 경과한 후 레코드를 제거할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7746-125">최대 기간 (일) 동안 체감 품질 데이터 유지</span><span class="sxs-lookup"><span data-stu-id="a7746-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="a7746-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="a7746-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="a7746-127">데이터베이스에서 삭제 되기 전에 데이터가 저장 되는 일 수 체감 품질.</span><span class="sxs-lookup"><span data-stu-id="a7746-127">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="a7746-128">제거를 사용할 수 없는 경우이 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-128">This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a7746-129">새로운 CsQoEConfiguration cmdlet에는 Lync Server 제어판에서 사용할 수 없는 추가 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="a7746-130">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">새로운 CsQoEConfiguration</A> 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7746-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="a7746-131">Lync Server 제어판을 사용 하 여 체감 품질 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a7746-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a7746-132">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a7746-133">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7746-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a7746-134">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a7746-135">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7746-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a7746-136">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="a7746-137">**경력 데이터** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="a7746-138">**사이트 선택**에서 정책을 적용할 사이트를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="a7746-139">**새로운 환경 품질 설정**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="a7746-140">모니터링을 켜려면 **체감 품질 데이터 모니터링 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="a7746-141">제거를 켜려면 **체감 품질 데이터 제거 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="a7746-142">**최대 기간 (일 수)에 대해 체감 품질 유지**를 선택 하 고, 체감 품질 레코드를 보존 해야 하는 최대 기간 (일)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="a7746-143">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a7746-144">Windows PowerShell Cmdlet을 사용 하 여 체감 품질 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="a7746-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a7746-145">Windows PowerShell 및 New-CsQoEConfiguration cmdlet을 사용 하 여 체감 품질 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="a7746-146">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a7746-147">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7746-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="a7746-148">체감 품질 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a7746-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="a7746-149">이 명령은 Redmond 사이트에 적용 된 체감 품질 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="a7746-150">체감 품질 모니터링을 사용 하지 않도록 설정 된 체감 품질 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a7746-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="a7746-151">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-151">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="a7746-152">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-152">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="a7746-153">예를 들어 기본적으로 체감 품질 녹화 사용 안 함을 허용 하는 환경 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-153">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="a7746-154">체감 품질 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="a7746-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="a7746-155">여러 매개 변수를 포함 하 여 여러 속성 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-155">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="a7746-156">예를 들어이 명령은 체감 품질 데이터를 30 일간 유지 하 고 3:00 AM에 오래 된 데이터를 제거 하도록 새 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7746-156">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="a7746-157">자세한 내용은 [새 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7746-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

