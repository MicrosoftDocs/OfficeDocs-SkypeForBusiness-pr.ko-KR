---
title: 비즈니스용 Skype 서버에서 경험 품질 구성 설정 삭제
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '요약: 비즈니스용 Skype 서버에서 QoE(QoE) 설정을 삭제하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: b48ddb9af715cd33b11d3c2f1c7ea90b3746aa4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095282"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a1736-103">비즈니스용 Skype 서버에서 경험 품질 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="a1736-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a1736-104">**요약:** 비즈니스용 Skype 서버에서 QoE(QoE) 설정을 삭제하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a1736-p101">QoE(체감 품질) 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다. 이러한 메트릭은 통화 정보 기록과 같은 기타 데이터와 별도로 데이터베이스에 저장되므로 다른 데이터 기록에 관계없이 QoE를 설정 및 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="a1736-107">비즈니스용 Skype 서버를 설치하면 단일 전역 QoE 구성 설정 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="a1736-108">관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="a1736-109">이러한 설정은 전역 범위 또는 사이트 범위에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="a1736-110">사이트 범위의 설정을 삭제할 경우 QoE는 전역 설정을 사용하여 해당 사이트에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="a1736-111">전역 설정을 "삭제"할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="a1736-112">그러나 전역 설정을 사실상 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="a1736-113">대신에, 해당 모음에 있는 모든 속성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="a1736-114">예를 들면 기본적으로 지우기는 QoE 구성 설정 모음에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="a1736-115">지우기를 사용할 수 없도록 전역 모음을 수정한다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="a1736-116">나중에 전역 설정을 삭제하면 모든 속성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="a1736-117">따라서 이 경우에는 지우기를 다시 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="a1736-118">비즈니스용 Skype 서버 제어판 또는 [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet을 사용하여 QoE 구성 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a1736-119">비즈니스용 Skype 서버 제어판을 사용하여 QoE 구성 설정을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="a1736-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a1736-120">RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a1736-121">자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1736-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="a1736-122">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a1736-123">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="a1736-124">**체감 품질 데이터** 페이지에서 원하는 정책을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="a1736-125">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a1736-126">Cmdlet을 사용하여 QoE 구성 Windows PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="a1736-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a1736-127">QoE 구성 설정은 **Remove-CsQoEConfiguration** cmdlet과 Windows PowerShell 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="a1736-128">비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1736-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a1736-129">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="a1736-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a1736-130">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="a1736-131">지정된 QoE 구성 설정 모음을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a1736-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="a1736-132">이 명령은 Redmond 사이트에 적용된 QoE 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="a1736-133">사이트 범위에 적용된 모든 QoE 구성 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a1736-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="a1736-134">이 명령은 사이트 범주에 적용된 모든 QoE 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="a1736-135">QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a1736-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="a1736-136">이 명령은 QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a1736-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="a1736-137">자세한 내용은 [Remove-CsQoEConfiguration을 참조합니다.](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a1736-137">For details, see [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1736-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1736-138">See also</span></span>

[<span data-ttu-id="a1736-139">비즈니스용 Skype 서버에서 통화 정보 기록 및 품질 데이터베이스를 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="a1736-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)