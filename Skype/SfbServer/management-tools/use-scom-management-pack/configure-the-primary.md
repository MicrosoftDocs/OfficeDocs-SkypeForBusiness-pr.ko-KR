---
title: 주요 관리 서버 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: '요약: 기본 관리 서버를 구성하고 System Center Operations Manager를 설치하고 비즈니스용 Skype 서버 2015용 관리 팩을 가져올 수 있습니다.'
ms.openlocfilehash: be7e484814e241b4aebb042a23497ed4806693e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814868"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="933bd-103">주요 관리 서버 구성</span><span class="sxs-lookup"><span data-stu-id="933bd-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="933bd-104">**요약:** 기본 관리 서버를 구성하고 System Center Operations Manager를 설치하고 비즈니스용 Skype 서버 2015용 관리 팩을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="933bd-105">비즈니스용 Skype 서버 2015에 포함된 새로운 상태 모니터링 기능을 모두 활용하려면 먼저 기본 관리 서버로 사용할 컴퓨터를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="933bd-106">그런 다음 해당 컴퓨터에 System Center Operations Manager 2012 SP1 또는 R2 또는 System Center Operations Manager 2007 R2를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="933bd-107">또한 Operations Manager 백 엔드 데이터베이스로 작동하려면 먼저 지원되는 SQL Server 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="933bd-108">System Center Operations Manager를 설치할 때 다음을 포함하여 해당 제품의 모든 구성 요소를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="933bd-109">운영 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="933bd-109">Operational database</span></span>

- <span data-ttu-id="933bd-110">서버</span><span class="sxs-lookup"><span data-stu-id="933bd-110">Server</span></span>

- <span data-ttu-id="933bd-111">콘솔</span><span class="sxs-lookup"><span data-stu-id="933bd-111">Console</span></span>

- <span data-ttu-id="933bd-112">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="933bd-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="933bd-113">웹 콘솔</span><span class="sxs-lookup"><span data-stu-id="933bd-113">Web console</span></span>

- <span data-ttu-id="933bd-114">보고</span><span class="sxs-lookup"><span data-stu-id="933bd-114">Reporting</span></span>

- <span data-ttu-id="933bd-115">데이터 웨어하우스</span><span class="sxs-lookup"><span data-stu-id="933bd-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="933bd-116">System Center Operations Manager[2012를](https://www.microsoft.com/download/details.aspx?id=6442)설치하기 전에 "Microsoft Report Viewer 2010 재배포 가능한 패키지"를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="933bd-117">이러한 제품 및 설치에 대한 자세한 내용은 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="933bd-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="933bd-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="933bd-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="933bd-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="933bd-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="933bd-120">비즈니스용 Skype 서버 배포당 루트 관리 서버는 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="933bd-121">비즈니스용 Skype 서버 2015 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="933bd-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="933bd-122">System Center Operations Manager에서 모니터링할 수 있는 항목, 해당 항목을 모니터링할 방법 및 경고가 트리거 및 보고되는 방법을 표시하는 소프트웨어 등 관리 팩을 설치하여 System Center Operations Manager의 기능을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="933bd-123">비즈니스용 Skype 서버 2015에는 다음 기능을 제공하는 두 가지 System Center Operations Manager 관리 팩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="933bd-124"> 구성 요소 및 사용자 관리 팩(Microsoft.LS.2015.Monitoring.ComponentAndUser.mp)은 이벤트 로그에 기록되거나, 성능 카운터에 등록되거나, CDRS(통화 정보 기록) 또는 QoE(QoE) 데이터베이스에 기록된 비즈니스용 Skype 서버 문제를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="933bd-125">중요한 문제의 경우 전자 메일, 인스턴트 메시지 또는 SMS 메시징을 통해 관리자에게 즉시 알리도록 System Center Operations Manager를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="933bd-126">SMS(Short Message Service)는 모바일 장치에서 다른 모바일 장치로 문자 메시지를 보내는 데 사용되는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="933bd-127">Operations Manager 알림 구성에 대한 자세한 내용은 알림 [구성을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="933bd-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="933bd-128">Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp(Active **Monitoring Management** Pack)는 시스템에 로그인하거나 인스턴트 메시지를 변경하거나 PSTN(전화망)에 있는 전화로 전화를 걸기 등 주요 비즈니스용 Skype 서버 구성 요소를 능동적으로 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="933bd-129">이러한 테스트는 비즈니스용 Skype 서버 가상 트랜잭션 cmdlet을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="933bd-130">예를 들어 **Test-CsIM** cmdlet은 한 쌍의 테스트 사용자 간의 인스턴트 메시징 대화를 시뮬레이션하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="933bd-131">이 시뮬레이션된 대화가 실패하면 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="933bd-132">관리 팩을 가져오는 것은 중요한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="933bd-133">관리 팩을 가져오지 않은 경우 Operations Manager를 사용하여 비즈니스용 Skype 서버 이벤트를 모니터링하거나 비즈니스용 Skype 서버 가상 트랜잭션을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="933bd-134">구성 요소 및 사용자 관리 팩은 비즈니스용 Skype 서버 2015만 모니터링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="933bd-135">비즈니스용 Skype 서버 2015와 Lync Server 2013이 모두 설치된 동시 사용 시나리오에 있는 경우 Lync Server 2013 컴퓨터에 Lync Server 2013 관리 팩을 계속 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="933bd-136">비즈니스용 Skype 서버 2015 관리 팩에는 비즈니스용 Skype 서버 2015 구성 요소 및 사용자 관리 팩과 비즈니스용 Skype 서버 2015 활성 모니터링 관리 팩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="933bd-137">다음 도구 중 하나를 사용해서 관리 팩을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="933bd-138">**System Center Operations Manager** 이 방법을 사용하면 Operations Manager를 사용하여 비즈니스용 Skype 서버에 대한 모니터링을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="933bd-139">**Operations Manager 셸** Operations Manager 셸을 사용하여 직접 가져오거나 System Center Operations Manager 콘솔을 사용하여 관리 팩을 가져올 때 발생하는 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="933bd-140">System Center Operations Manager를 사용하여 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="933bd-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="933bd-141">Microsoft SkypeForBusiness2015ManagementPacks.msi 다운로드하여 msi를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="933bd-142">System Center Operations Manager에서 관리 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="933bd-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="933bd-143">관리 창에서 **관리 팩** 을 마우스 오른쪽 단추로 클릭한 후 **관리 팩 가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="933bd-144">**관리 팩 선택** 대화 상자에서 **추가** 를 클릭한 후 **디스크에서 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="933bd-145">온라인 카탈로그 **연결** 대화 상자에서 아니요를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="933bd-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="933bd-146">관리 **팩을 선택하여** 가져오기 대화 상자에서 파일을 찾아서 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 클릭한 다음 **열기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="933bd-147">대화 상자에서 여러 파일을 선택하려면 첫 번째 파일을 클릭한 다음 Ctrl 키를 잡고 후속 파일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="933bd-148">**관리 팩 선택** 대화 상자에서 **설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="933bd-149">오류 메시지가 표시되고 설치가 실패하면 일반적으로 관리 팩 파일이 Windows 사용자 계정 컨트롤에서 보호되는 폴더에 있기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="933bd-150">이 경우 파일을 다른 폴더에 복사한 다음 가져오기 및 설치 프로세스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="933bd-151">**관리 팩 선택** 대화 상자에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="933bd-152">가져오기 및 설치 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="933bd-153">Operations Manager 셸을 사용하여 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="933bd-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="933bd-154">일반적으로 Operations Manager 콘솔을 사용하여 관리 팩을 가져오는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="933bd-155">그러나 오류가 발생하고 가져오기에 실패하면 콘솔에서 항상 적절한 오류 보고서를 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="933bd-156">이에 비해 Operations Manager 셸은 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="933bd-157">Operations Manager를 사용하는 경우 관리 팩을 가져올 때 문제가 발생하는 경우 Operations Manager 셸을 사용하여 팩을 가져오면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="933bd-158">Operations Manager 셸에서 제공하는 정보를 통해 가져오기 실패 이유를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="933bd-159">**시작,** 모든 **프로그램,** **Microsoft System Center 2012,** **Operations Manager** 및 **Operations Manager 셸을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="933bd-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="933bd-160">Operations Manager 셸에서 파일 복사본의 실제 경로를 사용하여 명령 프롬프트에 다음 명령을 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp Enter를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="933bd-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="933bd-161">첫 번째 관리 팩을 가져온 후 파일 복사본에 대한 경로를 사용하여 프로세스를 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="933bd-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
