---
title: 'Lync Server 2013: 경험 치 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9515186ab28a6d6085a01ee6785aa1d95914b1f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="872f5-102">Lync Server 2013에서 환경 품질 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="872f5-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="872f5-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="872f5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="872f5-104">경력 (체감 품질) 메트릭은 손실 된 네트워크 패킷 수, 배경 잡음, "지터"의 양 (패킷 지연의 차이) 등을 포함 하 여 조직에서 오디오 및 비디오 통화의 품질을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-104">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="872f5-105">이러한 메트릭은 다른 데이터 (예: 호출 정보 레코드)와는 별도로 데이터베이스에 저장 되며,이를 사용 하 여 기타 데이터 기록과 독립적으로 체감 품질를 활성화 및 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-105">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="872f5-106">Microsoft Lync Server 2013을 설치 하면 체감 품질 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="872f5-107">또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="872f5-108">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 하므로 디자인에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="872f5-109">사이트 범위 설정을 삭제 하면 전역 설정을 사용 하 여 해당 사이트에서 체감 품질가 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="872f5-110">전역 설정을 "삭제" 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-110">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="872f5-111">그러나 전역 설정은 실제로 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-111">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="872f5-112">대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-112">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="872f5-113">예를 들어 체감 품질 구성 설정 컬렉션에서 기본적으로 제거를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-113">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="872f5-114">제거를 사용할 수 없도록 전역 컬렉션을 수정 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-114">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="872f5-115">나중에 전역 설정을 삭제 하면 모든 속성이 기본값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-115">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="872f5-116">이 경우 제거를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-116">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="872f5-117">Lync Server 제어판을 사용 하거나 [remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet을 사용 하 여 체감 품질 구성 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="872f5-118">Lync Server 제어판을 사용 하 여 체감 품질 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="872f5-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="872f5-119">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="872f5-120">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="872f5-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="872f5-121">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="872f5-122">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="872f5-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="872f5-123">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="872f5-124">**경력 데이터** 페이지에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="872f5-125">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="872f5-126">Windows PowerShell Cmdlet을 사용 하 여 체감 품질 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="872f5-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="872f5-127">Windows PowerShell 및 **Remove-CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="872f5-128">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="872f5-129">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="872f5-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="872f5-130">지정 된 체감 품질 구성 설정 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="872f5-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="872f5-131">이 명령은 Redmond 사이트에 적용 된 체감 품질 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="872f5-132">사이트 범위에 적용 된 모든 체감 품질 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="872f5-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="872f5-133">이 명령은 사이트 범위에 적용 된 모든 체감 품질 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="872f5-134">체감 품질 모니터링을 사용 하지 않도록 설정 된 체감 품질 구성 설정을 모두 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="872f5-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="872f5-135">이 명령은 체감 품질 모니터링을 사용 하지 않도록 설정한 모든 체감 품질 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="872f5-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="872f5-136">자세한 내용은 [제거-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="872f5-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

