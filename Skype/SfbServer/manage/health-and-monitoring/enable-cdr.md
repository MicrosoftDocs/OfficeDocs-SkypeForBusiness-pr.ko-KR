---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 사용
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: '요약: 비즈니스용 Skype 서버에서 CDR(통화 정보 기록) 레코드를 사용하도록 설정하는 방법을 학습합니다.'
ms.openlocfilehash: e2f652eeef77c336fb34be07c123f1ef026d458c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095232"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="633bc-103">비즈니스용 Skype 서버에서 통화 정보 기록 사용</span><span class="sxs-lookup"><span data-stu-id="633bc-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="633bc-104">**요약:** 비즈니스용 Skype 서버에서 CDR(통화 정보 기록) 레코드를 사용하도록 설정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="633bc-p101">CDR(통화 정보 기록)은 인스턴트 메시징, VoIP(Voice over Internet Protocol) 통화, 응용 프로그램 공유, 파일 전송, 모임 등의 피어 투 피어 활동에 대한 사용 및 진단 정보를 기록합니다. 이러한 사용 데이터는 ROI(투자 수익률)를 계산하는 데 사용하고, 진단 데이터는 피어-투-피어 활동 및 모임 관련 문제를 해결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="633bc-107">다음 절차에 따라 조직의 각 사이트 또는 조직 전체에 대해 CDR을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="633bc-108">CDR을 사용하도록 설정하려면 먼저 모니터링 및 모니터링 데이터베이스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="633bc-109">자세한 내용은 [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="633bc-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="633bc-110">비즈니스용 Skype 서버 제어판에서 CDR을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="633bc-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="633bc-111">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="633bc-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="633bc-113">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **통화 정보 기록** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="633bc-114">**통화 정보 기록** 페이지의 표에서 적절한 사이트를 클릭하고 **동작** 을 클릭한 후에 **CDR 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="633bc-115">CDR은 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="633bc-116">cmdlet을 사용하여 CDR Windows PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="633bc-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="633bc-117">CDR은 **Set-CsCdrConfiguration** cmdlet과 Windows PowerShell 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="633bc-118">비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="633bc-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="633bc-119">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="633bc-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="633bc-120">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="633bc-121">단일 위치에 대해 CDR을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="633bc-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="633bc-122">CDR을 사용하도록 설정하려면 EnableCDR 매개 변수를 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="633bc-123">단일 위치에 대해 CDR을 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="633bc-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="633bc-124">CDR을 사용하지 않도록 설정하려면 EnableCDR 매개 변수를 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="633bc-125">CDR을 사용 안 하게 해서 모니터링이 제거되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="633bc-126">CDR 데이터 수집 및 저장을 일시 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="633bc-127">단일 명령을 사용하여 여러 위치에서 CDR을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="633bc-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="633bc-128">다음 명령은 조직에서 현재 사용 중인 모든 CDR 구성 설정에 대해 CDR을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="633bc-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="633bc-129">자세한 내용은 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="633bc-129">For more information, see the help topic for the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="633bc-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="633bc-130">See also</span></span>

[<span data-ttu-id="633bc-131">모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="633bc-131">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="633bc-132">모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="633bc-132">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)