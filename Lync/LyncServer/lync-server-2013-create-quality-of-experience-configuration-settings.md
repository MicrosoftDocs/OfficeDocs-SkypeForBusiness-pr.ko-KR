---
title: 'Lync Server 2013: 경험 수준 구성 설정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb0f47ffd0ff2955a783a5fc2912f9f0aaa64ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a5075-102">Lync Server 2013에서 환경 품질 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="a5075-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5075-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a5075-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a5075-p101">QoE(체감 품질) 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다. 이러한 메트릭은 통화 정보 기록과 같은 기타 데이터와 별도로 데이터베이스에 저장되므로 다른 데이터 기록에 관계없이 QoE를 설정 및 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="a5075-106">Microsoft Lync Server 2013을 설치 하면 QoE 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="a5075-107">관리자에게는 또한 사이트 범위에서 사용자 지정 설정을 만드는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="a5075-108">이러한 사이트 범위 설정을 사용할 때마다 전역 설정보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="a5075-109">예를 들어 Redmond 사이트에 대해 사이트 범위의 설정을 만들었으면 해당 설정(전역 설정이 아니라)이 Redmond의 QoE를 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="a5075-110">QoE 구성 설정은 Lync Server 제어판 이나 [remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet을 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="a5075-111">Lync Server 제어판을 사용 하 여 새 설정을 만드는 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5075-112">UI 설정</span><span class="sxs-lookup"><span data-stu-id="a5075-112">UI Setting</span></span></th>
<th><span data-ttu-id="a5075-113">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5075-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="a5075-114">설명</span><span class="sxs-lookup"><span data-stu-id="a5075-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5075-115">이름</span><span class="sxs-lookup"><span data-stu-id="a5075-115">Name</span></span></p></td>
<td><p><span data-ttu-id="a5075-116">ID</span><span class="sxs-lookup"><span data-stu-id="a5075-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="a5075-p104">만들려는 설정에 대한 고유한 식별자입니다. QoE 구성 설정은 사이트 범위에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5075-119">QoE 데이터에 대한 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="a5075-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="a5075-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="a5075-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="a5075-121">QoE 레코드를 수집하고 모니터링 데이터베이스에 저장할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5075-122">QoE 데이터에 대한 삭제 사용</span><span class="sxs-lookup"><span data-stu-id="a5075-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="a5075-123">은 enablepurging 설정한</span><span class="sxs-lookup"><span data-stu-id="a5075-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="a5075-124"><strong>QoE 데이터 보관 최대 기간(일 수)</strong> 속성에 정의된 기간이 경과한 후 레코드를 삭제할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5075-125">QoE 데이터 보관 최대 기간(일 수)</span><span class="sxs-lookup"><span data-stu-id="a5075-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="a5075-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="a5075-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="a5075-p105">데이터베이스에서 삭제되기 전에 QoE 데이터를 저장할 기간(일)입니다. 삭제를 사용하지 않도록 설정하면 이 값이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a5075-129">Remove-csqoeconfiguration cmdlet에는 Lync Server 제어판에서 사용할 수 없는 추가 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="a5075-130">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">remove-csqoeconfiguration</A> 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5075-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="a5075-131">Lync Server 제어판을 사용 하 여 QoE 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a5075-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a5075-132">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a5075-133">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5075-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a5075-134">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a5075-135">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5075-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a5075-136">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **체감 품질 데이터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="a5075-137">**체감 품질 데이터** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="a5075-138">**사이트 선택**에서 정책을 적용할 사이트를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="a5075-139">**새 체감 품질 설정**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="a5075-140">**QoE 데이터 모니터링 사용**을 선택하여 모니터링을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="a5075-141">**QoE 데이터 삭제 사용**을 선택하여 삭제를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="a5075-142">**QoE 보관 최대 기간(일 수)** 에서 QoE 레코드를 보관할 최대 기간(일 수)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="a5075-143">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5075-144">Windows PowerShell Cmdlet을 사용 하 여 QoE 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="a5075-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a5075-145">Windows PowerShell 및 Remove-csqoeconfiguration cmdlet을 사용 하 여 QoE 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="a5075-146">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a5075-147">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5075-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="a5075-148">QoE 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a5075-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="a5075-149">이 명령은 Redmond 사이트에 적용되는 QoE 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="a5075-150">QoE 모니터링이 사용하지 않도록 설정된 QoE 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a5075-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="a5075-p110">이전 명령에서 매개 변수(필수 Identity 매개 변수 제외)가 지정되지 않았기 때문에 구성 설정의 새 컬렉션에는 모든 속성에 대해 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 단순히 적합한 매개 변수와 매개 변수 값을 포함합니다. 예를 들어 기본적으로 QoE 기록을 사용하지 않도록 설정하는 QoE(체감 품질) 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="a5075-154">QoE 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="a5075-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="a5075-p111">여러 매개 변수를 포함하여 여러 속성 값을 지정할 수 있습니다. 예를 들어 다음 명령은 QoE 데이터를 30일 동안 보관하고 오전 3시에 오래된 데이터를 삭제하도록 지정하는 새 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a5075-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="a5075-157">자세한 내용은 [remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5075-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

