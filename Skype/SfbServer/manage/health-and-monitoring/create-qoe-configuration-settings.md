---
title: 비즈니스용 Skype 서버에서 환경 품질 구성 설정 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '요약: 비즈니스용 Skype 서버의 체감 품질 (환경 품질) 설정에 대해 알아보세요.'
ms.openlocfilehash: 254e6f1032026f715c30017f984bc2906f46e0df
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992795"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="90120-103">비즈니스용 Skype 서버에서 환경 품질 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="90120-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="90120-104">**요약:** 비즈니스용 Skype 서버의 체감 품질 (환경 품질) 설정에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="90120-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="90120-105">경력 (체감 품질) 메트릭은 손실 된 네트워크 패킷 수, 배경 잡음, "지터"의 양 (패킷 지연의 차이) 등을 포함 하 여 조직에서 오디오 및 비디오 통화의 품질을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-105">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="90120-106">이러한 메트릭은 다른 데이터 (예: 호출 정보 레코드)와는 별도로 데이터베이스에 저장 되며,이를 사용 하 여 기타 데이터 기록과 독립적으로 체감 품질를 활성화 및 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-106">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="90120-107">비즈니스용 Skype 서버를 설치 하면 체감 품질 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="90120-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="90120-108">또한 관리자는 사이트 범위에서 사용자 지정 설정을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="90120-109">이러한 사이트 범위 설정이 사용 될 때마다 전역 설정 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90120-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="90120-110">예를 들어 Redmond 사이트에 대 한 사이트 범위 설정을 만드는 경우 전역 설정이 아닌 해당 설정을 사용 하 여 Redmond의 체감 품질를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="90120-111">체감 품질 구성 설정은 비즈니스용 Skype 서버 제어판 또는 [CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet을 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="90120-112">비즈니스용 Skype Server 제어판을 사용 하 여 새 설정을 만드는 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="90120-113">**UI 설정**</span><span class="sxs-lookup"><span data-stu-id="90120-113">**UI setting**</span></span>|<span data-ttu-id="90120-114">**PowerShell 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="90120-114">**PowerShell parameter**</span></span>|<span data-ttu-id="90120-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="90120-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="90120-116">이름</span><span class="sxs-lookup"><span data-stu-id="90120-116">Name</span></span>  <br/> |<span data-ttu-id="90120-117">Identity</span><span class="sxs-lookup"><span data-stu-id="90120-117">Identity</span></span>  <br/> |<span data-ttu-id="90120-118">만들려는 설정의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="90120-118">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="90120-119">체감 품질 구성 설정은 사이트 범위 에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-119">QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="90120-120">체감 품질 데이터 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="90120-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="90120-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="90120-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="90120-122">체감 품질 레코드를 수집 하 여 모니터링 데이터베이스에 저장할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="90120-123">체감 품질 데이터 제거 사용</span><span class="sxs-lookup"><span data-stu-id="90120-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="90120-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="90120-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="90120-125">**최대 기간에 대해 체감 품질 데이터 유지 (days)** 속성에 정의 된 기간이 경과한 후 레코드를 제거할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="90120-126">최대 기간 (일) 동안 체감 품질 데이터 유지</span><span class="sxs-lookup"><span data-stu-id="90120-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="90120-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="90120-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="90120-128">데이터베이스에서 삭제 되기 전에 데이터가 저장 되는 일 수 체감 품질.</span><span class="sxs-lookup"><span data-stu-id="90120-128">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="90120-129">제거를 사용할 수 없는 경우이 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90120-129">This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="90120-130">새로운 CsQoEConfiguration cmdlet에는 비즈니스용 Skype Server 제어판에서 사용할 수 없는 추가 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="90120-131">자세한 내용은 [새로운 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90120-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="90120-132">비즈니스용 Skype 서버 제어판을 사용 하 여 체감 품질 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="90120-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="90120-133">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="90120-134">자세한 내용은 **대리인 설정 사용**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90120-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="90120-135">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90120-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="90120-136">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="90120-137">**경력 데이터** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="90120-138">**사이트 선택**에서 정책을 적용할 사이트를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="90120-139">**새로운 환경 품질 설정**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="90120-140">모니터링을 켜려면 **체감 품질 데이터 모니터링 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="90120-141">제거를 켜려면 **체감 품질 데이터 제거 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="90120-142">**최대 기간 (일 수)에 대해 체감 품질 유지**를 선택 하 고, 체감 품질 레코드를 보존 해야 하는 최대 기간 (일)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="90120-143">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90120-144">Windows PowerShell Cmdlet을 사용 하 여 체감 품질 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="90120-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90120-145">Windows PowerShell 및 New-CsQoEConfiguration cmdlet을 사용 하 여 체감 품질 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="90120-146">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="90120-147">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90120-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="90120-148">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="90120-149">체감 품질 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="90120-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="90120-150">이 명령은 Redmond 사이트에 적용 된 체감 품질 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90120-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="90120-151">체감 품질 모니터링을 사용 하지 않도록 설정 된 체감 품질 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="90120-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="90120-152">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90120-152">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="90120-153">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-153">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="90120-154">예를 들어 기본적으로 체감 품질 녹화 사용 안 함을 허용 하는 환경 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-154">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="90120-155">체감 품질 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="90120-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="90120-156">여러 매개 변수를 포함 하 여 여러 속성 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90120-156">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="90120-157">예를 들어이 명령은 체감 품질 데이터를 30 일간 유지 하 고 3:00 AM에 오래 된 데이터를 제거 하도록 새 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="90120-157">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="90120-158">자세한 내용은 [새 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90120-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

