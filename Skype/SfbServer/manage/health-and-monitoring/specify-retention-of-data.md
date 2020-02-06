---
title: 비즈니스용 Skype 서버에서 CDR 데이터 보존 지정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '요약: 비즈니스용 Skype 서버용 CDR (통화 정보 기록) 데이터를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817677"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="66f23-103">비즈니스용 Skype 서버에서 CDR 데이터 보존 지정</span><span class="sxs-lookup"><span data-stu-id="66f23-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="66f23-104">**요약:** 비즈니스용 Skype 서버용 CDR (통화 정보 기록) 데이터를 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="66f23-105">기본적으로, 60 일 후에 CDR (통화 정보 기록) 데이터가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-105">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="66f23-106">**통화 정보 기록** 페이지의 설정을 사용 하 여 오래 되거나 짧은 시간 동안 데이터를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-106">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="66f23-107">CDR를 사용 하지 않도록 설정 하는 경우 CDR를 사용 하도록 설정 하기 전에 캡처한 데이터도 제거 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-107">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66f23-108">동일한 일 수 동안 데이터를 보존 하도록 CDR 및 경력 (체감 품질)을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-108">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="66f23-109">모니터링 서버 보고서 웹 페이지에서 사용할 수 있는 CDRs (통화 정보 보고서)의 각 통화에는 CDR 및 체감 품질 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-109">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="66f23-110">CDR 및 체감 품질의 제거 기간이 서로 다른 경우 일부 통화에는 CDR 데이터만 포함 될 수 있으며, 그 외에는 체감 품질 데이터만 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-110">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="66f23-111">CDR 데이터에 대 한 지우기 설정을 구성 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="66f23-112">CDR 데이터 보존을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="66f23-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="66f23-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="66f23-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="66f23-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="66f23-115">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="66f23-116">**통화 정보 기록** 페이지에서 표의 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="66f23-117">제거를 설정 하려면 **CDRs 제거 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="66f23-118">**최대 기간 (일) 동안 CDRs 유지:** 통화 정보 기록을 보존 해야 하는 최대 일 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="66f23-119">**최대 기간 (일)에 대 한 오류 보고 데이터 유지:** 오류 보고서를 유지 해야 하는 최대 일 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="66f23-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="66f23-121">Windows PowerShell cmdlet을 사용 하 여 CDR 보존 지정</span><span class="sxs-lookup"><span data-stu-id="66f23-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="66f23-122">Windows PowerShell 및 Set-CsCdrConfiguration cmdlet을 사용 하 여 CDR 보존 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="66f23-123">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="66f23-124">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66f23-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="66f23-125">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="66f23-126">특정 위치에 대 한 CDR 보존을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="66f23-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="66f23-127">이 명령을 사용 하 여 Redmond 사이트에 대 한 CDR 데이터를 제거 하 고, 사이트를 구성 하 여 CDR 데이터와 오류 보고 데이터를 모두 20 일 동안 유지 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="66f23-128">여러 위치에 대 한 CDR 보존을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="66f23-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="66f23-129">이 명령은 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR 보존을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="66f23-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="66f23-130">자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66f23-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66f23-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66f23-131">See also</span></span>

[<span data-ttu-id="66f23-132">비즈니스용 Skype 서버의 전화 정보 기록 (CDR)</span><span class="sxs-lookup"><span data-stu-id="66f23-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
