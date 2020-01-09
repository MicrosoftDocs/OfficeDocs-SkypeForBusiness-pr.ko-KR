---
title: 비즈니스용 Skype 서버에서 환경 품질 구성 설정 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '요약: 비즈니스용 Skype 서버에서 체감 품질 (환경 품질) 설정을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 134ebe39f41ca051db4ff79eafb094dcc929b5e8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992425"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f7205-103">비즈니스용 Skype 서버에서 환경 품질 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="f7205-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="f7205-104">**요약:** 비즈니스용 Skype 서버에서 체감 품질 (환경 품질) 설정을 삭제 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="f7205-105">경력 (체감 품질) 메트릭은 손실 된 네트워크 패킷 수, 배경 잡음, "지터"의 양 (패킷 지연의 차이) 등을 포함 하 여 조직에서 오디오 및 비디오 통화의 품질을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-105">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="f7205-106">이러한 메트릭은 다른 데이터 (예: 호출 정보 레코드)와는 별도로 데이터베이스에 저장 되며,이를 사용 하 여 기타 데이터 기록과 독립적으로 체감 품질를 활성화 및 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-106">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="f7205-107">비즈니스용 Skype 서버를 설치 하면 체감 품질 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="f7205-108">또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="f7205-109">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 하므로 디자인에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="f7205-110">사이트 범위 설정을 삭제 하면 전역 설정을 사용 하 여 해당 사이트에서 체감 품질가 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="f7205-111">전역 설정을 "삭제" 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="f7205-112">그러나 전역 설정은 실제로 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="f7205-113">대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="f7205-114">예를 들어 체감 품질 구성 설정 컬렉션에서 기본적으로 제거를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="f7205-115">제거를 사용할 수 없도록 전역 컬렉션을 수정 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="f7205-116">나중에 전역 설정을 삭제 하면 모든 속성이 기본값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="f7205-117">이 경우 제거를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="f7205-118">비즈니스용 Skype Server 제어판을 사용 하거나 [remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet을 사용 하 여 체감 품질 구성 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f7205-119">비즈니스용 Skype 서버 제어판을 사용 하 여 체감 품질 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="f7205-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f7205-120">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f7205-121">자세한 내용은 **대리인 설정 사용**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7205-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f7205-122">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f7205-123">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="f7205-124">**경력 데이터** 페이지에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="f7205-125">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f7205-126">Windows PowerShell Cmdlet을 사용 하 여 체감 품질 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="f7205-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f7205-127">Windows PowerShell 및 **Remove-CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="f7205-128">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f7205-129">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7205-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f7205-130">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="f7205-131">지정 된 체감 품질 구성 설정 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="f7205-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="f7205-132">이 명령은 Redmond 사이트에 적용 된 체감 품질 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="f7205-133">사이트 범위에 적용 된 모든 체감 품질 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="f7205-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="f7205-134">이 명령은 사이트 범위에 적용 된 모든 체감 품질 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="f7205-135">체감 품질 모니터링을 사용 하지 않도록 설정 된 체감 품질 구성 설정을 모두 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="f7205-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="f7205-136">이 명령은 체감 품질 모니터링을 사용 하지 않도록 설정한 모든 체감 품질 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7205-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="f7205-137">자세한 내용은 [제거-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7205-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7205-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7205-138">See also</span></span>

[<span data-ttu-id="f7205-139">비즈니스용 Skype 서버에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="f7205-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

