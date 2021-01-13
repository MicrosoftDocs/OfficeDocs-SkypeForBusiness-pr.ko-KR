---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 및 경험 품질 설정 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '요약: 비즈니스용 Skype 서버에서 CDR 및 QoE를 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: dd8611723e3d83f8a4553ba2148ee5ae29791e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802288"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="1f072-103">비즈니스용 Skype 서버에서 통화 정보 기록 및 경험 품질 설정 구성</span><span class="sxs-lookup"><span data-stu-id="1f072-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1f072-104">**요약:** 비즈니스용 Skype 서버에서 CDR 및 QoE를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server.</span></span>
  
<span data-ttu-id="1f072-105">비즈니스용 Skype 서버에 대한 SQL Server Reporting Services 보고서를 사용하여 CDR 및 QoE 모니터링을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="1f072-106">CDR 및 QoE 구성</span><span class="sxs-lookup"><span data-stu-id="1f072-106">Configure CDR and QoE</span></span>

<span data-ttu-id="1f072-107">모니터링 저장소를 프런트 엔드 풀과 연결한 후 모니터링 저장소를 설정한 다음 SQL Server Reporting Services 및 모니터링 보고서를 설치 및 구성한 후 비즈니스용 Skype 서버 관리 셸을 사용하여 CDR(통화 정보 기록) 및 QoE(QoE) 모니터링을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="1f072-108">비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하면 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 CDR 및/또는 QoE 모니터링을 사용하고 사용하지 않도록 설정할 수 있습니다. 이 명령은 다음 명령을 사용하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="1f072-109">비즈니스용 Skype 서버를 설치할 때 CDR 및 QoE 모두에 대해 미리 정의한 전역 구성 설정 컬렉션도 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-109">When you install Skype for Business Server, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="1f072-110">통화 정보 기록에서 사용하는 보다 일반적으로 사용되는 설정 중 일부의 기본값이 아래 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="1f072-111">**속성**</span><span class="sxs-lookup"><span data-stu-id="1f072-111">**Property**</span></span>|<span data-ttu-id="1f072-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="1f072-112">**Description**</span></span>|<span data-ttu-id="1f072-113">**기본값**</span><span class="sxs-lookup"><span data-stu-id="1f072-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f072-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="1f072-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="1f072-p103">CDR을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 CDR 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="1f072-117">True</span><span class="sxs-lookup"><span data-stu-id="1f072-117">True</span></span>  <br/> |
|<span data-ttu-id="1f072-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="1f072-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="1f072-p104">CDR 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepCallDetailForDays(CDR 레코드) 및 KeepErrorReportForDays(CDR 오류) 속성에 지정된 기간이 지난 후 기록이 삭제됩니다. False인 경우에는 CDR 레코드가 무기한 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="1f072-122">True</span><span class="sxs-lookup"><span data-stu-id="1f072-122">True</span></span>  <br/> |
|<span data-ttu-id="1f072-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="1f072-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="1f072-p105">CDR 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="1f072-126">KeepCallDetailForDays는 1에서 2562일(약 7년) 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="1f072-127">60일</span><span class="sxs-lookup"><span data-stu-id="1f072-127">60 days</span></span>  <br/> |
|<span data-ttu-id="1f072-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="1f072-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="1f072-129">CDR 오류 보고서가 보관되는 일 수를 나타냅니다. 지정된 일 수보다 오래된 보고서는 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="1f072-130">CDR 오류 보고서는 비즈니스용 Skype 서버와 같은 클라이언트 응용 프로그램에서 업로드하는 진단 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server.</span></span>  <br/> <span data-ttu-id="1f072-131">이 속성은 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="1f072-132">60일</span><span class="sxs-lookup"><span data-stu-id="1f072-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="1f072-133">마찬가지로, 선택한 QoE 설정에 대한 기본값이 아래 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="1f072-134">**속성**</span><span class="sxs-lookup"><span data-stu-id="1f072-134">**Property**</span></span>|<span data-ttu-id="1f072-135">**설명**</span><span class="sxs-lookup"><span data-stu-id="1f072-135">**Description**</span></span>|<span data-ttu-id="1f072-136">**기본값**</span><span class="sxs-lookup"><span data-stu-id="1f072-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f072-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="1f072-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="1f072-p107">QoE 모니터링을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 QoE 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="1f072-140">True</span><span class="sxs-lookup"><span data-stu-id="1f072-140">True</span></span>  <br/> |
|<span data-ttu-id="1f072-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="1f072-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="1f072-p108">QoE 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepQoEDataForDays 속성에 지정된 기간이 지난 후 레코드가 삭제됩니다. False인 경우 QoE 레코드는 무기한 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="1f072-145">True</span><span class="sxs-lookup"><span data-stu-id="1f072-145">True</span></span>  <br/> |
|<span data-ttu-id="1f072-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="1f072-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="1f072-p109">QoE 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="1f072-149">KeepCallDetailForDays는 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="1f072-150">60일</span><span class="sxs-lookup"><span data-stu-id="1f072-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="1f072-151">이러한 전역 설정을 수정해야 하는 경우 Set-CsCdrConfiguration cmdlet을 사용하여 Set-CsQoEConfiguration 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="1f072-152">예를 들어 이 명령(비즈니스용 Skype 서버 관리 셸 내에서 실행)은 전역 범위에서 CDR 모니터링을 사용하지 않도록 설정합니다. 이 경우 EnableCDR 속성을 False($False).</span><span class="sxs-lookup"><span data-stu-id="1f072-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="1f072-153">모니터링을 사용하지 않도록 설정해도 프런트 엔드 풀에서 모니터링 저장소의 연결이 해제되지 않으며, 백 엔드 모니터링 데이터베이스가 제거되거나 다른 방식으로 영향을 받지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="1f072-154">비즈니스용 Skype 서버 관리 셸을 사용하여 CDR 또는 QoE 모니터링을 사용하지 않도록 설정하는 경우 비즈니스용 Skype 서버가 모니터링 데이터를 수집 및 보관하지 못하게 일시적으로 중지하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="1f072-155">이 경우 CDR 데이터 수집 및 보관을 다시 시작하려면 EnableCDR 속성을 다시 True($True)로 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="1f072-156">마찬가지로, 다음 명령은 전역 범위에서 QoE 레코드 삭제를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="1f072-p112">이처럼 전역 설정을 사용할 수 있을 뿐 아니라, CDR 및 QoE 구성 설정을 사이트 범위에도 할당할 수 있습니다. 이렇게 하면 모니터링을 보다 유동적으로 관리할 수 있습니다. 예를 들어 관리자는 Redmond 사이트에 대해서는 CDR 모니터링을 사용하도록 설정하고 Dublin 사이트에 대해서는 CDR 모니터링을 사용하지 않도록 설정할 수 있습니다. 사이트 범위에서 새 CDR 구성 설정을 만들려면 다음과 같은 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="1f072-p113">사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 Redmond 사이트에 대해 CDR 모니터링이 전역 범위에서는 사용하도록 설정되고 사이트 범위에서는 사용하지 않도록 설정되어 있다고 가정해 보겠습니다. 이는 Redmond 사이트에 있는 사용자의 통화 정보 기록 정보가 보관되지 않음을 의미합니다. 그러나 다른 사이트에 있는 사용자(Redmond 사이트 설정 대신 전역 설정에 의해 관리되는 사용자)의 통화 정보 기록 정보는 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="1f072-164">다음과 같은 명령을 사용하면 사이트 범위에서 새 QoE 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="1f072-165">자세한 내용은 비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1f072-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
