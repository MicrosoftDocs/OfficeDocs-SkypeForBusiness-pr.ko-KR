---
title: 통화 정보 기록 및 경험 수준 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0a7d6eb309c8afd13e671a12c98623c486b220d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="a94eb-102">Lync Server 2013에서 통화 정보 기록 및 경험 수준 설정 구성</span><span class="sxs-lookup"><span data-stu-id="a94eb-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a94eb-103">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a94eb-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a94eb-104">모니터링 저장소를 프런트 엔드 풀과 연결한 후 모니터링 저장소를 설정 하 고, SQL Server Reporting Services 및 모니터링 보고서를 설치한 후에 CDR (통화 정보 기록) 및 QoE (서비스 품질)를 관리할 수 있습니다. Lync Server 관리 셸을 사용 하 여 모니터링</span><span class="sxs-lookup"><span data-stu-id="a94eb-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="a94eb-105">Lync Server 관리 셸 cmdlet을 사용 하면 특정 사이트 또는 전체 Lync Server 배포에 대해 CDR 및/또는 QoE 모니터링을 설정 하 고 사용 하지 않도록 설정할 수 있습니다. 다음과 같이 간단한 명령을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="a94eb-106">Microsoft Lync Server 2013을 설치할 때 CDR 및 QoE에 대해 미리 정의 된 전역 구성 설정 모음도 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="a94eb-107">통화 정보 기록에서 사용하는 보다 일반적으로 사용되는 설정 중 일부의 기본값이 아래 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a94eb-108">속성</span><span class="sxs-lookup"><span data-stu-id="a94eb-108">Property</span></span></th>
<th><span data-ttu-id="a94eb-109">설명</span><span class="sxs-lookup"><span data-stu-id="a94eb-109">Description</span></span></th>
<th><span data-ttu-id="a94eb-110">기본값</span><span class="sxs-lookup"><span data-stu-id="a94eb-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a94eb-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="a94eb-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="a94eb-p103">CDR을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 CDR 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="a94eb-114">참</span><span class="sxs-lookup"><span data-stu-id="a94eb-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a94eb-115">은 enablepurging 설정한</span><span class="sxs-lookup"><span data-stu-id="a94eb-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="a94eb-p104">CDR 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepCallDetailForDays(CDR 레코드) 및 KeepErrorReportForDays(CDR 오류) 속성에 지정된 기간이 지난 후 기록이 삭제됩니다. False인 경우에는 CDR 레코드가 무기한 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="a94eb-119">참</span><span class="sxs-lookup"><span data-stu-id="a94eb-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a94eb-120">Keepcalldetailfordays는</span><span class="sxs-lookup"><span data-stu-id="a94eb-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="a94eb-p105">CDR 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="a94eb-123">KeepCallDetailForDays는 1에서 2562일(약 7년) 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="a94eb-124">60일</span><span class="sxs-lookup"><span data-stu-id="a94eb-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a94eb-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="a94eb-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="a94eb-126">CDR 오류 보고서가 보관 되는 일 수를 나타냅니다. 지정한 일 수 보다 오래 된 보고서는 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="a94eb-127">CDR 오류 보고서는 Microsoft Lync 2013와 같은 클라이언트 응용 프로그램에서 업로드 하는 진단 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="a94eb-128">이 속성은 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="a94eb-129">60일</span><span class="sxs-lookup"><span data-stu-id="a94eb-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a94eb-130">마찬가지로, 선택한 QoE 설정에 대한 기본값이 아래 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a94eb-131">속성</span><span class="sxs-lookup"><span data-stu-id="a94eb-131">Property</span></span></th>
<th><span data-ttu-id="a94eb-132">설명</span><span class="sxs-lookup"><span data-stu-id="a94eb-132">Description</span></span></th>
<th><span data-ttu-id="a94eb-133">기본값</span><span class="sxs-lookup"><span data-stu-id="a94eb-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a94eb-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="a94eb-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="a94eb-p107">QoE 모니터링을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 QoE 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="a94eb-137">참</span><span class="sxs-lookup"><span data-stu-id="a94eb-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a94eb-138">은 enablepurging 설정한</span><span class="sxs-lookup"><span data-stu-id="a94eb-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="a94eb-p108">QoE 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepQoEDataForDays 속성에 지정된 기간이 지난 후 레코드가 삭제됩니다. False인 경우 QoE 레코드는 무기한 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="a94eb-142">참</span><span class="sxs-lookup"><span data-stu-id="a94eb-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a94eb-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="a94eb-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="a94eb-p109">QoE 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="a94eb-146">KeepCallDetailForDays는 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="a94eb-147">60일</span><span class="sxs-lookup"><span data-stu-id="a94eb-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a94eb-p110">이러한 전역 설정을 수정해야 하는 경우 Set-CsCdrConfiguration 및 Set-CsQoEConfiguration cmdlet을 사용하면 됩니다. 예를 들어 다음 명령(Lync Server 관리 셸 내에서 실행)은 전역 범위에서 CDR 모니터링을 사용하지 않도록 설정합니다. 이를 위해 EnableCDR 속성을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p110">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets. For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="a94eb-150">모니터링을 사용하지 않도록 설정해도 프런트 엔드 풀에서 모니터링 저장소의 연결이 해제되지 않으며, 백 엔드 모니터링 데이터베이스가 제거되거나 다른 방식으로 영향을 받지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="a94eb-151">Lync Server 관리 셸을 사용 하 여 CDR 또는 QoE 모니터링과 함께 사용 하지 않도록 설정 하는 경우에는 Lync Server가 모니터링 데이터를 수집 하 고 보관 하지 못하도록 일시적으로 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="a94eb-152">이 경우 CDR 데이터 수집 및 보관을 다시 시작하려면 EnableCDR 속성을 다시 True($True)로 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="a94eb-153">마찬가지로, 다음 명령은 전역 범위에서 QoE 레코드 삭제를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="a94eb-p112">이처럼 전역 설정을 사용할 수 있을 뿐 아니라, CDR 및 QoE 구성 설정을 사이트 범위에도 할당할 수 있습니다. 이렇게 하면 모니터링을 보다 유동적으로 관리할 수 있습니다. 예를 들어 관리자는 Redmond 사이트에 대해서는 CDR 모니터링을 사용하도록 설정하고 Dublin 사이트에 대해서는 CDR 모니터링을 사용하지 않도록 설정할 수 있습니다. 사이트 범위에서 새 CDR 구성 설정을 만들려면 다음과 같은 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="a94eb-p113">사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 Redmond 사이트에 대해 CDR 모니터링이 전역 범위에서는 사용하도록 설정되고 사이트 범위에서는 사용하지 않도록 설정되어 있다고 가정해 보겠습니다. 이는 Redmond 사이트에 있는 사용자의 통화 정보 기록 정보가 보관되지 않음을 의미합니다. 그러나 다른 사이트에 있는 사용자(Redmond 사이트 설정 대신 전역 설정에 의해 관리되는 사용자)의 통화 정보 기록 정보는 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="a94eb-161">다음과 같은 명령을 사용하면 사이트 범위에서 새 QoE 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="a94eb-162">자세한 내용을 보려면 Lync Server 관리 셸 내에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a94eb-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

