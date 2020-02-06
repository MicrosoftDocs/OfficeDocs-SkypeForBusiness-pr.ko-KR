---
title: 주요 관리 서버 구성
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 비즈니스용 Skype Server 2019에 대 한 기본 관리 서버를 구성 하 고 System Center Operations Manager를 설치 하 고 관리 팩을 가져옵니다.'
ms.openlocfilehash: a4fda367307b99bb952e6673b3b4d1c2967299c6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824002"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="6a7e5-103">주요 관리 서버 구성</span><span class="sxs-lookup"><span data-stu-id="6a7e5-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="6a7e5-104">**요약:** 주 관리 서버를 구성 하 고 System Center Operations Manager를 설치 하 고 비즈니스용 Skype 서버 2019에 대 한 관리 팩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="6a7e5-105">비즈니스용 Skype 서버 2019에 포함 된 새로운 상태 모니터링 기능을 최대한 활용 하려면 먼저 기본 관리 서버로 작동할 컴퓨터를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="6a7e5-106">그런 다음 해당 컴퓨터에 System Center Operations Manager 2012 SP1 또는 R2 또는 System Center Operations Manager 2007 R2를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="6a7e5-107">또한, 먼저 Operations Manager 백 엔드 데이터베이스로 작동 하도록 지원 되는 SQL Server 버전을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="6a7e5-108">System Center Operations Manager를 설치 하는 경우 다음을 포함 하 여 해당 제품의 모든 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="6a7e5-109">운영 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="6a7e5-109">Operational database</span></span>

- <span data-ttu-id="6a7e5-110">서버</span><span class="sxs-lookup"><span data-stu-id="6a7e5-110">Server</span></span>

- <span data-ttu-id="6a7e5-111">콘솔</span><span class="sxs-lookup"><span data-stu-id="6a7e5-111">Console</span></span>

- <span data-ttu-id="6a7e5-112">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="6a7e5-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="6a7e5-113">웹 콘솔</span><span class="sxs-lookup"><span data-stu-id="6a7e5-113">Web console</span></span>

- <span data-ttu-id="6a7e5-114">보고</span><span class="sxs-lookup"><span data-stu-id="6a7e5-114">Reporting</span></span>

- <span data-ttu-id="6a7e5-115">데이터 웨어하우스</span><span class="sxs-lookup"><span data-stu-id="6a7e5-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a7e5-116">System Center Operations Manager 2012를 설치 하려면 먼저 "[Microsoft Report Viewer 2010 재배포 가능 패키지](https://www.microsoft.com/en-us/download/details.aspx?id=6442)"를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="6a7e5-117">이러한 제품과 설치에 대 한 자세한 내용은 다음 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="6a7e5-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="6a7e5-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="6a7e5-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="6a7e5-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="6a7e5-120">비즈니스용 Skype 서버 배포 당 하나의 루트 관리 서버만을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="6a7e5-121">비즈니스용 Skype 서버 2019 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="6a7e5-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="6a7e5-122">관리 팩을 설치 하 여 system center operations Manager에서 모니터링할 수 있는 항목을 지정 하는 소프트웨어, 해당 항목을 모니터링 하는 방법, 알림을 트리거하는 방법 등 시스템 센터 Operations Manager의 기능을 확장할 수 있습니다. 보고.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="6a7e5-123">비즈니스용 Skype 서버 2019에는 다음 기능을 제공 하는 두 가지 System Center Operations Manager 관리 팩이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="6a7e5-124">**구성 요소 및 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp (사용자 관리 팩)는** 이벤트 로그에 기록 된 비즈니스용 Skype 서버 문제를 추적 하 고, 성능 카운터에 등록 하거나, cdrs (통화 정보 레코드) 또는 체감 품질 (환경 품질) 데이터베이스에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="6a7e5-125">중요 한 문제의 경우 관리자에 게 전자 메일, 인스턴트 메시지 또는 SMS 메시지를 즉시 알리기 위해 System Center Operations Manager를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="6a7e5-126">(SMS 또는 짧은 메시지 서비스는 모바일 장치 간에 문자 메시지를 전송 하는 데 사용 되는 기술입니다.)</span><span class="sxs-lookup"><span data-stu-id="6a7e5-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="6a7e5-127">Operations Manager 알림을 구성 하는 방법에 대 한 자세한 내용은 [알림 구성을](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="6a7e5-128">**능동 모니터링 관리 팩** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp)은 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 PSTN (공개 통신 네트워크)에 있는 휴대폰으로 전화를 거는 등의 비즈니스용 Skype Server 구성 요소를 사전 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="6a7e5-129">이러한 테스트는 비즈니스용 Skype 서버 가상 트랜잭션 cmdlet을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="6a7e5-130">예를 들어 **test-CsIM** cmdlet은 한 쌍의 테스트 사용자 간에 인스턴트 메시징 대화를 시뮬레이트하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="6a7e5-131">이 시뮬레이트된 대화에 실패 하면 경고가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="6a7e5-132">관리 팩 가져오기는 매우 중요 한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="6a7e5-133">관리 팩을 가져오지 않으면 Operations Manager를 사용 하 여 비즈니스용 Skype Server 이벤트를 모니터링 하거나 비즈니스용 Skype 서버 가상 트랜잭션을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="6a7e5-134">구성 요소 및 사용자 관리 팩은 비즈니스용 Skype 서버 2019만 모니터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="6a7e5-135">비즈니스용 skype 서버 2019와 비즈니스용 Skype Server 2015이 모두 설치 되어 있는 공존 시나리오에서는 비즈니스용 skype server 2015 컴퓨터에 대해 비즈니스용 Skype Server 2015 관리 팩을 계속 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="6a7e5-136">비즈니스용 Skype server 2019의 관리 팩에는 비즈니스용 Skype 서버 2019 구성 요소와 사용자 관리 팩 및 비즈니스용 Skype 서버 2019 액티브 모니터링 관리 팩이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="6a7e5-137">다음 도구 중 하나를 사용 하 여 관리 팩을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="6a7e5-138">**System Center Operations Manager** 이 방법을 사용 하는 경우 Operations Manager를 사용 하 여 비즈니스용 Skype Server에 대 한 모니터링을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="6a7e5-139">**Operations Manager Shell** Operations Manager Shell을 사용 하 여 직접 가져오거나 System Center Operations Manager 콘솔을 사용 하 여 관리 팩을 가져올 때 발생 하는 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="6a7e5-140">System Center Operations Manager를 사용 하 여 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="6a7e5-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="6a7e5-141">Microsoft 웹 다운로드에서 SkypeForBusiness2019ManagementPacks를 다운로드 하 고 msi를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="6a7e5-142">System Center Operations Manager에서 **관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="6a7e5-143">관리 창에서 **관리 팩**을 마우스 오른쪽 단추로 클릭 한 다음 **관리 팩 가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="6a7e5-144">**관리 팩 선택** 대화 상자에서 **추가**를 클릭 한 다음 **디스크에서 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="6a7e5-145">**온라인 카탈로그 연결** 대화 상자에서 **아니요**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="6a7e5-146">**가져올 관리 팩 선택** 대화 상자에서 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 및 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp 파일을 찾아 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="6a7e5-147">대화 상자에서 여러 파일을 선택 하려면 첫 번째 파일을 클릭 한 다음 Ctrl 키를 누른 채 후속 파일을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="6a7e5-148">**관리 팩 선택** 대화 상자에서 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="6a7e5-149">오류 메시지가 표시 되 고 설치가 실패 하는 경우 일반적으로 관리 팩 파일이 Windows 사용자 계정 컨트롤에서 보호 하는 폴더에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="6a7e5-150">이 문제가 발생 하면 파일을 다른 폴더에 복사한 다음 가져오기 및 설치 프로세스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="6a7e5-151">**관리 팩 선택** 대화 상자에서 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="6a7e5-152">가져오기 및 설치 프로세스를 완료 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="6a7e5-153">Operations Manager Shell을 사용 하 여 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="6a7e5-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="6a7e5-154">일반적으로 Operations Manager 콘솔을 사용 하 여 관리 팩을 가져오는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="6a7e5-155">그러나 오류가 발생 하 고 가져오기에 실패 하는 경우 콘솔은 항상 적절 한 오류 보고서를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="6a7e5-156">비교를 통해 Operations Manager 셸은 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="6a7e5-157">Operations Manager를 사용 하는 경우 관리 팩을 가져올 때 문제가 발생 하면 Operations Manager Shell을 사용 하 여 팩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="6a7e5-158">Operations Manager 셸이 제공 하는 정보를 통해 가져오기에 실패 한 이유를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="6a7e5-159">**시작**, **모든 프로그램**, **Microsoft System Center 2012**을 클릭 하 고 **Operations Manager**를 클릭 한 다음 **operations manager Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="6a7e5-160">Operations Manager 셸에서 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 파일의 실제 경로를 사용 하 여 명령 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="6a7e5-161">첫 번째 관리 팩을 가져온 후에는 파일 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp의 복사본 경로를 사용 하 여 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7e5-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
