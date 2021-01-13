---
title: 비즈니스용 Skype 서버에서 CDR 구성 설정의 기존 컬렉션 삭제
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '요약: 비즈니스용 Skype 서버에서 CDR 구성 설정을 제거하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: ca6691d6a1a19e0d9219a256986b683b719da885
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816968"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="5201d-103">비즈니스용 Skype 서버에서 CDR 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="5201d-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="5201d-104">**요약:** 비즈니스용 Skype 서버에서 CDR 구성 설정을 제거하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="5201d-p101">CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="5201d-107">비즈니스용 Skype 서버를 설치하면 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="5201d-108">관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="5201d-109">사이트 범위에서 구성된 설정은 기본적으로 전역 범위에서 구성된 설정보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="5201d-110">사이트 범위 설정을 삭제할 경우 해당 사이트에서 전역 설정을 사용하여 CDR이 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="5201d-111">전역 설정을 "삭제"할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="5201d-112">그러나 전역 설정을 사실상 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="5201d-113">대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="5201d-114">예를 들어, CDR 구성 설정의 컬렉션에서는 기본적으로 삭제를 사용할 수 있도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="5201d-115">삭제를 사용하지 않도록 전역 컬렉션을 수정한다고 가정해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="5201d-116">나중에 전역 설정을 삭제하면 모든 속성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="5201d-117">따라서 이 경우에는 지우기를 다시 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="5201d-118">비즈니스용 Skype 서버 제어판 또는 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여 CDR 구성 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="5201d-119">비즈니스용 Skype 서버 제어판을 사용하여 CDR 구성 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="5201d-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5201d-120">비즈니스용 Skype 서버 제어판에서 모니터링 및 **보관을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5201d-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="5201d-p104">**통화 정보 기록** 탭에서 제거하려는 CDR 설정의 컬렉션을 선택합니다. 여러 컬렉션을 선택하려면 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 추가 컬렉션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="5201d-123">**편집** 을 클릭한 다음 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="5201d-124">비즈니스용 Skype 서버 제어판 대화 상자에서 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5201d-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5201d-125">Cmdlet을 사용하여 CDR 구성 Windows PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="5201d-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5201d-126">통화 정보 기록 구성 설정은 **remove-CsCdrConfiguration** cmdlet과 Windows PowerShell 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="5201d-127">비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5201d-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5201d-128">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5201d-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5201d-129">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="5201d-130">CDR 구성 설정의 지정된 컬렉션을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="5201d-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="5201d-131">이 명령은 Redmond 사이트에 적용된 CDR 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="5201d-132">사이트 범위에 적용된 모든 CDR 구성 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="5201d-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="5201d-133">이 명령은 사이트 범위에 적용된 모든 CDR 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="5201d-134">자세한 내용은 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5201d-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5201d-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5201d-135">See also</span></span>

[<span data-ttu-id="5201d-136">비즈니스용 Skype 서버에서 통화 정보 기록 및 경험 품질 데이터베이스를 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="5201d-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

