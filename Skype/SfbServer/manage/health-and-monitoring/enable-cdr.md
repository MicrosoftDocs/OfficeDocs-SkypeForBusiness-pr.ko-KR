---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 사용
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: '요약: 비즈니스용 Skype 서버에서 CDR (통화 정보 기록) 레코드를 사용 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 6c4460ac004ee15893b81f09f7bd59943365e64c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817978"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="df3df-103">비즈니스용 Skype 서버에서 통화 정보 기록 사용</span><span class="sxs-lookup"><span data-stu-id="df3df-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="df3df-104">**요약:** 비즈니스용 Skype 서버에서 CDR (통화 정보 기록) 레코드를 사용 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="df3df-105">CDR (통화 정보 기록)는 인스턴스 메시징, VoIP (Voice over 인터넷 프로토콜) 통화, 응용 프로그램 공유, 파일 전송, 모임 등 피어 투 피어 활동에 대 한 사용 및 진단 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="df3df-106">사용 현황 데이터는 ROI (투자 수익률)를 계산 하는 데 사용할 수 있으며, 진단 데이터를 사용 하 여 피어 투 피어 활동 및 모임 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="df3df-107">조직의 전체 조직 또는 각 사이트에 대해 CDR를 사용 하도록 설정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="df3df-108">CDR를 사용 하려면 모니터링과 모니터링 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="df3df-109">자세한 내용은 [모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df3df-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="df3df-110">비즈니스용 Skype Server 제어판에서 CDR를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="df3df-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="df3df-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="df3df-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="df3df-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="df3df-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="df3df-114">**통화 정보 기록** 페이지의 표에서 해당 사이트를 클릭 하 고 **작업**을 클릭 한 다음 **CDR 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df3df-115">CDR는 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df3df-116">Windows PowerShell cmdlet을 사용 하 여 CDR 사용</span><span class="sxs-lookup"><span data-stu-id="df3df-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="df3df-117">Windows PowerShell 및 **Set-CsCdrConfiguration** cmdlet을 사용 하 여 CDR를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="df3df-118">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="df3df-119">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df3df-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="df3df-120">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="df3df-121">단일 위치에 대해 CDR를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="df3df-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="df3df-122">CDR를 사용 하지 않으려면 EnableCDR 매개 변수를 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="df3df-123">단일 위치에 대해 CDR를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="df3df-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="df3df-124">CDR를 사용 하지 않으려면 EnableCDR 매개 변수를 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="df3df-125">CDR를 사용 하지 않도록 설정 하면 모니터링이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="df3df-126">이 메서드는 CDR 데이터의 수집 및 저장소를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="df3df-127">단일 명령을 사용 하 여 여러 위치에서 CDR를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="df3df-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="df3df-128">이 명령은 현재 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df3df-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="df3df-129">자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df3df-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="df3df-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df3df-130">See also</span></span>

[<span data-ttu-id="df3df-131">모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="df3df-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="df3df-132">모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="df3df-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
