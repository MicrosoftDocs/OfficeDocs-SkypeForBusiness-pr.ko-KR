---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 및 환경 품질 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '요약: 비즈니스용 Skype 서버에서 CDR 및 체감 품질를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 8a83e5920de60d664e76590d2b5b2a9f36b589ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197726"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="44037-103">비즈니스용 Skype 서버에서 통화 정보 기록 및 환경 품질 설정 구성</span><span class="sxs-lookup"><span data-stu-id="44037-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="44037-104">**요약:** 비즈니스용 Skype 서버에서 CDR 및 체감 품질를 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="44037-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server.</span></span>
  
<span data-ttu-id="44037-105">비즈니스용 Skype 서버용 SQL Server Reporting Services 보고서를 사용 하 여 CDR 및 체감 품질 모니터링을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="44037-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="44037-106">CDR 및 체감 품질 구성</span><span class="sxs-lookup"><span data-stu-id="44037-106">Configure CDR and QoE</span></span>

<span data-ttu-id="44037-107">프런트 엔드 풀과 모니터링 저장소를 연결 하 고 모니터링 저장소를 설정한 다음 설치 및 구성 SQL Server Reporting Services 및 모니터링 보고서를 사용 하 여, CDR (통화 정보 기록) 및 경력 (체감 품질)을 관리할 수 있습니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 모니터링</span><span class="sxs-lookup"><span data-stu-id="44037-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="44037-108">비즈니스용 skype 서버 관리 셸 cmdlet을 사용 하면 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 CDR 및/또는 체감 품질 모니터링을 활성화 및 비활성화할 수 있습니다. 다음과 같이 간단한 명령으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="44037-109">비즈니스용 Skype 서버를 설치 하는 경우에는 CDR 및 체감 품질에 대해 미리 정의 된 전역 구성 설정 모음도 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-109">When you install Skype for Business Server, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="44037-110">통화 정보 기록에 사용 되는 일반적으로 사용 되는 일부 설정에 대 한 기본값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="44037-111">**속성**</span><span class="sxs-lookup"><span data-stu-id="44037-111">**Property**</span></span>|<span data-ttu-id="44037-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="44037-112">**Description**</span></span>|<span data-ttu-id="44037-113">**기본값**</span><span class="sxs-lookup"><span data-stu-id="44037-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44037-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="44037-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="44037-115">CDR를 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44037-115">Indicates whether or not CDR is enabled.</span></span> <span data-ttu-id="44037-116">True 인 경우 모든 CDR 레코드가 수집 되 고 모니터링 데이터베이스에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-116">If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="44037-117">False</span><span class="sxs-lookup"><span data-stu-id="44037-117">True</span></span>  <br/> |
|<span data-ttu-id="44037-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="44037-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="44037-119">CDR 레코드를 데이터베이스에서 정기적으로 삭제할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44037-119">Indicates whether or not CDR records will periodically be deleted from the database.</span></span> <span data-ttu-id="44037-120">True 인 경우 KeepCallDetailForDays 속성 (CDR 레코드) 및 KeepErrorReportForDays (CDR 오류의 경우)에서 지정한 기간 후 레코드가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-120">If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors).</span></span> <span data-ttu-id="44037-121">False 인 경우, CDR 레코드가 무기한 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-121">If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="44037-122">False</span><span class="sxs-lookup"><span data-stu-id="44037-122">True</span></span>  <br/> |
|<span data-ttu-id="44037-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="44037-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="44037-124">CDR 레코드가 데이터베이스에 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-124">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="44037-125">그러나이는 제거가 활성화 된 경우에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="44037-125">However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="44037-126">KeepCallDetailForDays는 1 ~ 2562 일 (약 7 년) 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="44037-127">60 일</span><span class="sxs-lookup"><span data-stu-id="44037-127">60 days</span></span>  <br/> |
|<span data-ttu-id="44037-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="44037-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="44037-129">CDR 오류 보고서 보관 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 보고서는 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="44037-130">CDR 오류 보고서는 비즈니스용 Skype 서버와 같은 클라이언트 응용 프로그램에서 업로드 하는 진단 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="44037-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server.</span></span>  <br/> <span data-ttu-id="44037-131">이 속성은 1에서 2562 일 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="44037-132">60 일</span><span class="sxs-lookup"><span data-stu-id="44037-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="44037-133">마찬가지로, 선택한 체감 품질 설정에 대 한 기본값이이 표에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="44037-134">**속성**</span><span class="sxs-lookup"><span data-stu-id="44037-134">**Property**</span></span>|<span data-ttu-id="44037-135">**설명**</span><span class="sxs-lookup"><span data-stu-id="44037-135">**Description**</span></span>|<span data-ttu-id="44037-136">**기본값**</span><span class="sxs-lookup"><span data-stu-id="44037-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44037-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="44037-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="44037-138">체감 품질 모니터링을 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44037-138">Indicates whether or not QoE monitoring is enabled.</span></span> <span data-ttu-id="44037-139">True 인 경우 모든 체감 품질 레코드가 수집 되 고 모니터링 데이터베이스에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-139">If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="44037-140">False</span><span class="sxs-lookup"><span data-stu-id="44037-140">True</span></span>  <br/> |
|<span data-ttu-id="44037-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="44037-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="44037-142">체감 품질 레코드를 데이터베이스에서 정기적으로 삭제할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44037-142">Indicates whether or not QoE records will periodically be deleted from the database.</span></span> <span data-ttu-id="44037-143">True 인 경우 KeepQoEDataForDays 속성에 지정 된 기간 후에 레코드가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-143">If True, records will be deleted after the time period specified by the KeepQoEDataForDays property.</span></span> <span data-ttu-id="44037-144">False 인 경우 체감 품질 레코드는 무한정 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-144">If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="44037-145">False</span><span class="sxs-lookup"><span data-stu-id="44037-145">True</span></span>  <br/> |
|<span data-ttu-id="44037-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="44037-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="44037-147">체감 품질 레코드가 데이터베이스에 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-147">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="44037-148">그러나이는 제거가 활성화 된 경우에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="44037-148">However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="44037-149">KeepCallDetailForDays는 1에서 2562 일 사이의 모든 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="44037-150">60 일</span><span class="sxs-lookup"><span data-stu-id="44037-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="44037-151">이러한 전역 설정을 수정 해야 하는 경우 CsCdrConfiguration 및 CsQoEConfiguration cmdlet을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="44037-152">예를 들어 비즈니스용 Skype 서버 관리 셸에서 실행 되는이 명령은 전역 범위에서 CDR 모니터링을 사용 하지 않도록 설정 합니다. 이것은 EnableCDR 속성을 False ($False)로 설정 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="44037-153">모니터링을 사용 하지 않도록 설정 해도 프런트 엔드 풀의 모니터링 저장소는 분리 되지 않으며 백엔드 모니터링 데이터베이스에 대 한 제거 또는 영향을 받지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="44037-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="44037-154">비즈니스용 Skype Server Management Shell을 사용 하 여 CDR 또는 체감 품질 모니터링을 비활성화 하는 경우, 일시적으로 비즈니스용 Skype Server가 모니터링 데이터를 수집 및 보관 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="44037-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="44037-155">이 경우,이 경우 CDR 데이터를 수집 하 고 보관 하는 작업을 다시 시작 하려면 EnableCDR 속성을 True ($True)로 다시 설정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="44037-156">마찬가지로,이 명령은 전역 범위에서 체감 품질 레코드 제거를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="44037-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="44037-157">전역 설정 외에 CDR 및 체감 품질 구성 설정은 사이트 범위에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-157">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope.</span></span> <span data-ttu-id="44037-158">이렇게 하면 모니터링할 때 추가적으로 관리 유연성을 제공 합니다. 예를 들어 관리자는 Redmond 사이트에 대해 CDR 모니터링을 사용 하도록 설정할 수 있지만, 더블린 사이트에 대 한 CDR 모니터링을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44037-158">This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site.</span></span> <span data-ttu-id="44037-159">사이트 범위에서 새 CDR 구성 설정을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44037-159">To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="44037-160">사이트 범위에서 구성한 설정이 전역 범위에서 구성 된 설정 보다 우선 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="44037-160">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="44037-161">예를 들어, 전역 범위에서 CDR 모니터링을 사용 하도록 설정 했지만 사이트 범위 (Redmond 사이트의 경우)에서 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="44037-161">For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="44037-162">이는 레드먼드 사이트의 사용자에 대 한 통화 정보 기록 정보가 보관 되지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="44037-162">That means that call detail recording information will not be archived for users in the Redmond site.</span></span> <span data-ttu-id="44037-163">그러나 다른 사이트 (즉, Redmond 사이트 설정 대신 전역 설정에서 관리 하는 사용자)의 사용자에 게는 통화 정보 기록 정보가 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44037-163">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="44037-164">다음과 같은 명령을 사용 하 여 사이트 범위에서 새 체감 품질 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44037-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="44037-165">자세한 내용은 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 하세요.</span><span class="sxs-lookup"><span data-stu-id="44037-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
