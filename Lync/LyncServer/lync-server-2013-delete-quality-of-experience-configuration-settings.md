---
title: 'Lync Server 2013: 경험 수준 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c64e7083b4968229a3e878fe5ad4cde258095c14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="026b7-102">Lync Server 2013에서 환경 품질 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="026b7-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="026b7-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="026b7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="026b7-p101">QoE(체감 품질) 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다. 이러한 메트릭은 통화 정보 기록과 같은 기타 데이터와 별도로 데이터베이스에 저장되므로 다른 데이터 기록에 관계없이 QoE를 설정 및 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="026b7-106">Microsoft Lync Server 2013을 설치 하면 QoE 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="026b7-107">관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="026b7-108">이러한 설정은 전역 범위 또는 사이트 범위에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="026b7-109">사이트 범위의 설정을 삭제할 경우 QoE는 전역 설정을 사용하여 해당 사이트에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="026b7-p103">또한 전역 설정을 “삭제”할 수도 있습니다. 그러나 전역 설정을 사실상 삭제되지 않습니다. 대신에, 해당 모음에 있는 모든 속성이 기본값으로 다시 설정됩니다. 예를 들면 기본적으로 지우기는 QoE 구성 설정 모음에서 사용할 수 있습니다. 지우기를 사용할 수 없도록 전역 모음을 수정한다고 가정하겠습니다. 나중에 전역 설정을 삭제하면 모든 속성이 기본값으로 다시 설정됩니다. 따라서 이 경우에는 지우기를 다시 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of QoE configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="026b7-117">Lync Server 제어판을 사용 하거나 [remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet을 사용 하 여 QoE 구성 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="026b7-118">Lync Server 제어판을 사용 하 여 QoE 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="026b7-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="026b7-119">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="026b7-120">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="026b7-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="026b7-121">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="026b7-122">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="026b7-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="026b7-123">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **체감 품질 데이터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="026b7-124">**체감 품질 데이터** 페이지에서 원하는 정책을 클릭하고 **편집**을 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="026b7-125">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="026b7-126">Windows PowerShell Cmdlet을 사용 하 여 QoE 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="026b7-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="026b7-127">QoE 구성 설정은 Windows PowerShell 및 **remove-csqoeconfiguration** cmdlet을 사용 하 여 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="026b7-128">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="026b7-129">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="026b7-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="026b7-130">지정된 QoE 구성 설정 모음을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="026b7-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="026b7-131">이 명령은 Redmond 사이트에 적용된 QoE 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="026b7-132">사이트 범위에 적용된 모든 QoE 구성 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="026b7-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="026b7-133">이 명령은 사이트 범주에 적용된 모든 QoE 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="026b7-134">QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="026b7-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="026b7-135">이 명령은 QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="026b7-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="026b7-136">자세한 내용은 [Remove-remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="026b7-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

