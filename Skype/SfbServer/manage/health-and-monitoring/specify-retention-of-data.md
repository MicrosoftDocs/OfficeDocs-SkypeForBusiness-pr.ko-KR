---
title: 비즈니스용 Skype 서버에서 CDR 데이터 보존 지정
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '요약: 비즈니스용 Skype 서버의 CDR(통화 정보 기록) 데이터를 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: abf6461a76ced9d3ba07e4c5157dd4d14bab60a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104394"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="0c925-103">비즈니스용 Skype 서버에서 CDR 데이터 보존 지정</span><span class="sxs-lookup"><span data-stu-id="0c925-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="0c925-104">**요약:** 비즈니스용 Skype 서버에 대한 CDR(통화 정보 기록) 데이터를 관리하는 방법을 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="0c925-p101">기본적으로 CDR(통화 정보 기록) 데이트는 60일 이후에 삭제됩니다. **통화 정보 기록** 페이지의 설정을 사용하여 데이터를 60일 이상 보존하거나 60일보다 짧게 보존할 수 있습니다. CDR을 사용하지 않도록 설정한 경우 CDR을 사용하도록 설정하기 전에 캡처한 데이터도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c925-p102">CDR 및 QoE(체감 품질)의 데이터 보존 일수는 동일하게 구성해야 합니다. 모니터링 서버 보고서 홈 페이지에 있는 CDR(통화 정보 보고서)의 각 통화에는 CDR 및 QoE 정보가 포함됩니다. CDR 및 QoE의 삭제 기간이 다를 경우 일부 통화에는 CDR 데이터만 포함되고 또 다른 일부 통화에는 QoE 데이터만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="0c925-111">CDR 데이터에 대한 삭제 설정을 구성하려면 다음 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="0c925-112">CDR 데이터 보존 기간을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="0c925-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="0c925-113">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="0c925-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0c925-115">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **통화 정보 기록** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="0c925-116">**통화 정보 기록** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="0c925-117">삭제를 설정하려면 **CDR(통화 정보 기록) 삭제 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="0c925-118">**최대 기간(일) 동안 통화 정보 기록 유지:** 에서 통화 정보 기록을 보존할 최대 일수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="0c925-119">**최대 기간(일) 동안 오류 보고서 데이터 유지:** 에서 오류 보고서를 보존할 최대 일수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="0c925-120">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0c925-121">cmdlet을 사용하여 CDR Windows PowerShell 지정</span><span class="sxs-lookup"><span data-stu-id="0c925-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0c925-122">Windows PowerShell 및 Set-CsCdrConfiguration cmdlet을 사용하여 CDR 보존 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="0c925-123">비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c925-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0c925-124">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="0c925-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0c925-125">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="0c925-126">특정 위치에 대한 CDR 보존을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="0c925-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="0c925-127">이 명령은 Redmond 사이트에 대해 CDR 데이터 삭제를 사용하도록 설정하고 20일 동안 CDR 데이터 및 오류 보고서 데이터를 유지하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="0c925-128">여러 위치에 대한 CDR 보존을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="0c925-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="0c925-129">이 명령은 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR 보존을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0c925-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="0c925-130">자세한 내용은 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c925-130">For more information, see the help topic for the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c925-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c925-131">See also</span></span>

[<span data-ttu-id="0c925-132">비즈니스용 Skype 서버의 CDR(통화 정보 기록)</span><span class="sxs-lookup"><span data-stu-id="0c925-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)