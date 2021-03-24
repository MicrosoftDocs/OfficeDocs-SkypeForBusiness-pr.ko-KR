---
title: 비즈니스용 Skype 서버에서 CDR 구성 설정 컬렉션 만들기 또는 수정
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: '요약: 비즈니스용 Skype 서버의 CDR(통화 정보 기록)에 대해 자세히 알아보습니다.'
ms.openlocfilehash: da4383ef31b2d3ee781c445f2c935b79ea89bed8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095372"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d26fd-103">비즈니스용 Skype 서버에서 CDR 구성 설정 컬렉션 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d26fd-103">Create or modify a collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d26fd-104">**요약:** 비즈니스용 Skype 서버의 CDR(통화 정보 기록)에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-104">**Summary:** Learn about Call detail recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="d26fd-p101">CDR(통화 정보 기록)을 사용하면 피어 투 피어 메신저 대화 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="d26fd-107">비즈니스용 Skype 서버를 설치하면 CDR 구성 설정의 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-107">When you install Skype for Business Server a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="d26fd-108">관리자에게는 또한 사이트 범위에서 사용자 지정 설정을 만드는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="d26fd-109">이러한 사이트 범위의 설정은 사용될 때마다 전역 설정보다 높은 우선 순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="d26fd-110">예를 들어 레드몬드 사이트에 사이트 범위의 설정을 만들면 전역 설정이 아닌 해당 설정이 레드몬드의 CDR 관리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>
  
<span data-ttu-id="d26fd-111">비즈니스용 Skype 서버 제어판 또는 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여 CDR 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-111">You can create CDR configuration settings by using either Skype for Business Server Control Panel or the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d26fd-112">비즈니스용 Skype 서버 제어판 또는 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여 기존 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-112">You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings.</span></span> <span data-ttu-id="d26fd-113">비즈니스용 Skype 서버 제어판을 사용하여 설정을 만들거나 수정하는 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-113">If you are using Skype for Business Server Control Panel to create or modify settings, the following options will be available to you:</span></span>
  
|<span data-ttu-id="d26fd-114">**UI 설정**</span><span class="sxs-lookup"><span data-stu-id="d26fd-114">**UI setting**</span></span>|<span data-ttu-id="d26fd-115">**PowerShell 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="d26fd-115">**PowerShell parameter**</span></span>|<span data-ttu-id="d26fd-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="d26fd-116">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d26fd-117">이름</span><span class="sxs-lookup"><span data-stu-id="d26fd-117">Name</span></span>  <br/> |<span data-ttu-id="d26fd-118">ID</span><span class="sxs-lookup"><span data-stu-id="d26fd-118">Identity</span></span>  <br/> |<span data-ttu-id="d26fd-p104">CDR 구성 설정에 대한 고유 ID가 만들어집니다. 이러한 설정은 사이트 범위에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="d26fd-121">CDR 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="d26fd-121">Enable monitoring of CDRs</span></span>  <br/> |<span data-ttu-id="d26fd-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="d26fd-122">EnableCDR</span></span>  <br/> |<span data-ttu-id="d26fd-123">CDR을 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-123">Indicates whether or not CDR is enabled.</span></span>  <br/> |
|<span data-ttu-id="d26fd-124">CDR 삭제 사용</span><span class="sxs-lookup"><span data-stu-id="d26fd-124">Enable purging of CDRs</span></span>  <br/> |<span data-ttu-id="d26fd-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="d26fd-125">EnablePurging</span></span>  <br/> |<span data-ttu-id="d26fd-126">CDR을 CDR 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span>  <br/> |
|<span data-ttu-id="d26fd-127">최대 기간(일) 동안 CDR 유지</span><span class="sxs-lookup"><span data-stu-id="d26fd-127">Keep CDRs for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="d26fd-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="d26fd-128">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="d26fd-p105">CDR 기록을 CDR 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 기록은 모두 자동으로 삭제됩니다. 삭제는 삭제를 사용하도록 설정한 경우에만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span>  <br/> |
|<span data-ttu-id="d26fd-132">최대 기간(일) 동안 오류 보고서 데이터 유지</span><span class="sxs-lookup"><span data-stu-id="d26fd-132">Keep error report data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="d26fd-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="d26fd-133">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="d26fd-p106">CDR 오류 보고서를 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 보고서는 모두 자동으로 삭제됩니다. CDR 오류 보고서는 클라이언트 응용 프로그램에서 업로드하는 진단 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d26fd-137">이 New-CsCdrConfiguration Set-CsCdrConfiguration cmdlet에는 비즈니스용 Skype 서버 제어판에서 사용할 수 없는 추가 옵션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d26fd-138">자세한 [내용은 New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 및 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d26fd-138">See the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) and the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) help topics for more information.</span></span>
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d26fd-139">비즈니스용 Skype 서버 제어판을 사용하여 CDR 구성 설정을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="d26fd-139">To create CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d26fd-140">비즈니스용 Skype 서버 제어판에서 **모니터링 및 보관을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d26fd-140">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="d26fd-141">통화 정보 **기록 탭에서** 새로 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d26fd-141">On the **Call Detail Recording** tab, click **New**.</span></span>
    
3. <span data-ttu-id="d26fd-p108">**사이트 선택** 대화 상자에서 새 구성 설정을 만들 사이트를 선택합니다. 대화 상자가 빈 상태이면 이미 사이트가 모두 CDR 구성 설정 컬렉션에 할당되었다는 의미입니다. 각 사이트는 단일 CDR 컬렉션으로 제한됩니다. 따라서 설정을 삭제한 후 다시 만들거나, 간단히 기존 설정을 수정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>
    
4. <span data-ttu-id="d26fd-146">**새 통화 정보 기록 설정 만들기** 대화 상자에서 원하는 항목을 선택한 다음 **커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d26fd-147">비즈니스용 Skype 서버 제어판을 사용하여 기존 CDR 구성 설정을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="d26fd-147">To modify existing CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d26fd-148">비즈니스용 Skype 서버 제어판에서 **모니터링 및 보관을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d26fd-148">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="d26fd-149">수정할 설정 컬렉션을 두 번 클릭하거나 컬렉션을 선택하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="d26fd-150">한 번에 한 컬렉션만 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="d26fd-151">여러 컬렉션을 동일하게 변경하기 위해 비즈니스용 Skype 서버 관리 셸을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-151">To make the same changes to multiple collections, use the Skype for Business Server Management Shell instead.</span></span>
    
3. <span data-ttu-id="d26fd-152">**통화 정보 기록 설정 편집** 대화 상자에서 원하는 항목을 선택한 다음 **커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d26fd-153">cmdlet을 사용하여 CDR 구성 Windows PowerShell 만들기</span><span class="sxs-lookup"><span data-stu-id="d26fd-153">Creating CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d26fd-154">CDR 구성 설정은 **New-CsCdrConfiguration** cmdlet을 사용하여 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d26fd-155">비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d26fd-155">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d26fd-156">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="d26fd-156">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d26fd-157">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-157">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d26fd-158">새 CDR 구성 설정 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d26fd-158">To create a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="d26fd-159">다음 명령을 실행하면 레드몬드 사이트에 적용되는 새 CDR 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-159">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="d26fd-160">CDR(통화 정보 기록)을 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d26fd-160">To create a collection of CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="d26fd-p111">이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 CDR(통화 정보 기록)을 기본적으로 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면 다음과 같은 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d26fd-164">새 CDR 구성 설정 컬렉션을 만들 때 여러 속성 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="d26fd-164">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="d26fd-p112">여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 CDR(통화 정보 기록)을 30일 동안, 오류 보고서를 90일 동안 보관하는 새 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26fd-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

<span data-ttu-id="d26fd-167">자세한 내용은 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d26fd-167">For more information, see the help topic for the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
