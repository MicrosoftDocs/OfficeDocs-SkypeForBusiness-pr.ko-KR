---
title: 비즈니스용 Skype 서버에서 CDR 구성 정보 보기
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '요약: 비즈니스용 Skype 서버에서 CDR(통화 정보 기록)을 사용하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816638"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="f919f-103">비즈니스용 Skype 서버에서 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="f919f-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="f919f-104">**요약:** 비즈니스용 Skype 서버에서 CDR(통화 정보 기록)을 사용하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="f919f-p101">CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="f919f-107">비즈니스용 Skype 서버를 설치하면 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="f919f-108">관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="f919f-109">비즈니스용 Skype 서버 제어판 또는 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여 조직에서 사용 중인 CDR 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f919f-110">비즈니스용 Skype 서버 제어판을 사용하여 CDR 구성 정보를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="f919f-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f919f-111">비즈니스용 Skype 서버 제어판에서 모니터링 **및 보관을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f919f-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="f919f-p103">모든 CDR 구성 설정에 대한 목록은 **통화 정보 기록** 탭에 표시됩니다. 설정의 각 컬렉션에 대해 컬렉션 **이름** 이 표시되고, CDR이 설정되었는지 여부(**CDR** 속성), 삭제가 설정되었는지 여부(**CDR 삭제** 속성)가 표시됩니다. 컬렉션에 대한 자세한 내용을 보려면 해당 컬렉션을 두 번 클릭하거나 적합한 컬렉션을 선택하고, **편집** 을 클릭한 후 **세부 정보 표시** 를 클릭합니다. CDR 구성 설정은 한 번에 하나의 단일 컬렉션에 대한 자세한 정보만 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f919f-115">cmdlet을 사용하여 CDR 구성 Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="f919f-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f919f-116">CDR 구성 설정은 Windows PowerShell cmdlet을 사용하여 Get-CsCdrConfiguration 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="f919f-117">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f919f-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f919f-118">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f919f-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f919f-119">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="f919f-120">CDR 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="f919f-120">To view CDR configuration information</span></span>

- <span data-ttu-id="f919f-121">모든 CDR 구성 설정에 대한 정보를 확인하려면 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="f919f-122">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f919f-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="f919f-123">자세한 내용은 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f919f-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

