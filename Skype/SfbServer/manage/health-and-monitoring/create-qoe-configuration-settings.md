---
title: 비즈니스용 Skype 서버에서 환경 품질 구성 설정 만들기
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '요약: 비즈니스용 Skype 서버의 QoE(QoE) 설정에 대해 자세히 알아보습니다.'
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816998"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="edcb3-103">비즈니스용 Skype 서버에서 환경 품질 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="edcb3-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="edcb3-104">**요약:** 비즈니스용 Skype 서버의 QoE(QoE) 설정에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="edcb3-p101">QoE(체감 품질) 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다. 이러한 메트릭은 통화 정보 기록과 같은 기타 데이터와 별도로 데이터베이스에 저장되므로 다른 데이터 기록에 관계없이 QoE를 설정 및 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="edcb3-107">비즈니스용 Skype 서버를 설치하면 단일 전역 QoE 구성 설정 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="edcb3-108">관리자에게는 또한 사이트 범위에서 사용자 지정 설정을 만드는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="edcb3-109">이러한 사이트 범위 설정을 사용할 때마다 전역 설정보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="edcb3-110">예를 들어 Redmond 사이트에 대해 사이트 범위의 설정을 만들었으면 해당 설정(전역 설정이 아니라)이 Redmond의 QoE를 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="edcb3-111">QoE 구성 설정은 비즈니스용 Skype 서버 제어판 또는 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet을 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="edcb3-112">비즈니스용 Skype 서버 제어판을 사용하여 새 설정을 만드는 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="edcb3-113">**UI 설정**</span><span class="sxs-lookup"><span data-stu-id="edcb3-113">**UI setting**</span></span>|<span data-ttu-id="edcb3-114">**PowerShell 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="edcb3-114">**PowerShell parameter**</span></span>|<span data-ttu-id="edcb3-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="edcb3-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="edcb3-116">이름</span><span class="sxs-lookup"><span data-stu-id="edcb3-116">Name</span></span>  <br/> |<span data-ttu-id="edcb3-117">ID</span><span class="sxs-lookup"><span data-stu-id="edcb3-117">Identity</span></span>  <br/> |<span data-ttu-id="edcb3-p104">만들려는 설정에 대한 고유한 식별자입니다. QoE 구성 설정은 사이트 범위에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="edcb3-120">QoE 데이터에 대한 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="edcb3-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="edcb3-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="edcb3-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="edcb3-122">QoE 레코드를 수집하고 모니터링 데이터베이스에 저장할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="edcb3-123">QoE 데이터에 대한 삭제 사용</span><span class="sxs-lookup"><span data-stu-id="edcb3-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="edcb3-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="edcb3-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="edcb3-125">**QoE 데이터 보관 최대 기간(일 수)** 속성에 정의된 기간이 경과한 후 레코드를 삭제할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="edcb3-126">QoE 데이터 보관 최대 기간(일 수)</span><span class="sxs-lookup"><span data-stu-id="edcb3-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="edcb3-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="edcb3-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="edcb3-p105">데이터베이스에서 삭제되기 전에 QoE 데이터를 저장할 기간(일)입니다. 삭제를 사용하지 않도록 설정하면 이 값이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="edcb3-130">이 New-CsQoEConfiguration cmdlet에는 비즈니스용 Skype 서버 제어판에서 사용할 수 없는 추가 옵션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="edcb3-131">자세한 내용은 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edcb3-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="edcb3-132">비즈니스용 Skype 서버 제어판을 사용하여 QoE 구성 설정을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="edcb3-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="edcb3-133">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="edcb3-134">자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edcb3-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="edcb3-135">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="edcb3-136">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="edcb3-137">**체감 품질 데이터** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="edcb3-138">**사이트 선택** 에서 정책을 적용할 사이트를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="edcb3-139">**새 체감 품질 설정** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="edcb3-140">**QoE 데이터 모니터링 사용** 을 선택하여 모니터링을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="edcb3-141">**QoE 데이터 삭제 사용** 을 선택하여 삭제를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="edcb3-142">**QoE 보관 최대 기간(일 수)** 에서 QoE 레코드를 보관할 최대 기간(일 수)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="edcb3-143">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="edcb3-144">cmdlet을 사용하여 QoE 구성 Windows PowerShell 만들기</span><span class="sxs-lookup"><span data-stu-id="edcb3-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="edcb3-145">QoE 구성 설정은 Windows PowerShell cmdlet을 사용하여 New-CsQoEConfiguration 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="edcb3-146">비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edcb3-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="edcb3-147">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="edcb3-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="edcb3-148">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="edcb3-149">QoE 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="edcb3-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="edcb3-150">이 명령은 Redmond 사이트에 적용되는 QoE 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="edcb3-151">QoE 모니터링이 사용하지 않도록 설정된 QoE 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="edcb3-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="edcb3-p109">이전 명령에서 매개 변수(필수 Identity 매개 변수 제외)가 지정되지 않았기 때문에 구성 설정의 새 컬렉션에는 모든 속성에 대해 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 단순히 적합한 매개 변수와 매개 변수 값을 포함합니다. 예를 들어 기본적으로 QoE 기록을 사용하지 않도록 설정하는 QoE(체감 품질) 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="edcb3-155">QoE 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="edcb3-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="edcb3-p110">여러 매개 변수를 포함하여 여러 속성 값을 지정할 수 있습니다. 예를 들어 다음 명령은 QoE 데이터를 30일 동안 보관하고 오전 3시에 오래된 데이터를 삭제하도록 지정하는 새 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="edcb3-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="edcb3-158">자세한 내용은 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edcb3-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

