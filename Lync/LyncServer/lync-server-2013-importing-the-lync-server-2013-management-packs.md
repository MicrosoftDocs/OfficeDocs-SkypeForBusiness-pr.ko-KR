---
title: 'Lync Server 2013: Lync Server 2013 관리 팩 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2c6dd42056fe665c0d4ec53d28103745ace2c84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="b91c4-102">Lync Server 2013 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="b91c4-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b91c4-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b91c4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b91c4-104">System center Operations Manager에서 모니터링할 수 있는 항목 및 해당 항목을 모니터링 하는 방법 및 알림을 트리거하는 방법을 결정 하는 관리 팩을 설치 하 여 System Center Operations Manager의 기능을 확장할 수 있습니다. 한다고.</span><span class="sxs-lookup"><span data-stu-id="b91c4-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="b91c4-105">Lync Server 2013에는 다음과 같은 기능을 제공 하는 2 개의 System Center Operations Manager 관리 팩이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="b91c4-106">구성 요소 및 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp (사용자 관리 팩)는 이벤트 로그에 기록 되 고, 성능 카운터에서 등록 되거나, CDR (통화 정보 기록) 또는 경력 품질 (QoE)에 기록 된 Lync Server 문제를 추적 합니다. 데이터베이스.</span><span class="sxs-lookup"><span data-stu-id="b91c4-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="b91c4-107">중요 한 문제의 경우 System Center Operations Manager를 구성 하 여 전자 메일, 인스턴트 메시지 또는 SMS (Short Message Service) 메시징을 통해 관리자에 게 즉시 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="b91c4-108">SMS는 모바일 장치 간에 문자 메시지를 전송하기 위해 사용되는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b91c4-109">Operations Manager 알림을 구성 하는 방법에 대 한 자세한 내용은 TechNet 라이브러리의 구성 알림 <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b91c4-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="b91c4-110">Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp (Active Monitoring Management Pack)는 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 공개 된 휴대폰에 전화를 거는 것과 같은 주요 Lync Server 구성 요소를 테스트 합니다. 전화 네트워크 (PSTN)</span><span class="sxs-lookup"><span data-stu-id="b91c4-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="b91c4-111">이러한 테스트는 Lync Server 가상 트랜잭션 cmdlet을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="b91c4-112">예를 들어 **Test-CsIM** cmdlet을 사용해서 테스트 사용자의 쌍 간에 IM(인스턴트 메시징) 대화를 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="b91c4-113">시뮬레이션된 메시징 대화가 실패하면 알림이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="b91c4-114">관리 팩을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-114">You need to import the management packs.</span></span> <span data-ttu-id="b91c4-115">관리 팩을 가져오지 않으면 Operations Manager를 사용 하 여 Lync Server 이벤트를 모니터링 하거나 Lync Server 가상 트랜잭션을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="b91c4-116">구성 요소 및 사용자 관리 팩은 Lync Server 2013을 모니터링 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="b91c4-117">Lync Server 2013와 Lync Server 2010이 모두 설치 되어 있는 공존 시나리오에서는 lync Server 2010 컴퓨터용 Lync Server 2010 관리 팩을 계속 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b91c4-118">Lync Server 2010 용 관리 팩에는 Lync Server 2010 모니터링 관리 팩과 Lync Server 2010 그룹 채팅 모니터링 관리 팩이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="b91c4-119">다음 도구 중 하나를 사용해서 관리 팩을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="b91c4-120">**System Center Operations manager**   이 방법을 사용 하는 경우 Operations manager를 사용 하 여 Lync Server에 대 한 모니터링을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="b91c4-121">**Operations manager shell**   operations manager 셸을 사용 하 여 직접 가져오거나 System Center Operations Manager 콘솔을 사용 하 여 관리 팩을 가져올 때 발생 하는 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="b91c4-122">System Center Operations Manager를 사용 하 여 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="b91c4-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="b91c4-123">Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 및 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="b91c4-124">System Center Operations Manager에서 **관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="b91c4-125">**관리** 창에서 **관리 팩**을 마우스 오른쪽 단추로 클릭한 후 **관리 팩 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="b91c4-126">**관리 팩 선택** 대화 상자에서 **추가**를 클릭한 후 **디스크에서 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="b91c4-127">**온라인 카탈로그 연결** 대화 상자에서 작업 관리자가 온라인에서 Lync Server 관리 팩에 대 한 종속성이 있는지 확인 하지 않도록 하려면 **취소** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="b91c4-128">System Center Operations Manager 2012를 사용 하는 경우 **아니요**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="b91c4-p107">**가져올 관리 팩 선택** 대화 상자에서 **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** 및 **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** 파일을 찾아서 선택한 후 **열기**를 클릭합니다. 대화 상자에서 여러 파일을 선택하려면 첫 번째 파일을 클릭하고, Ctrl 키를 누른 상태에서 두 번째 파일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-p107">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**. To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="b91c4-p108">**관리 팩 선택** 대화 상자에서 **설치**를 클릭합니다. 오류 메시지가 표시되고 설치가 실패하면 일반적으로 관리 팩 파일이 Windows 사용자 계정 컨트롤에서 보호되는 폴더에 있기 때문일 수 있습니다. 이 경우 파일을 다른 폴더에 복사한 후 가져오기 및 설치 프로세스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="b91c4-p109">**관리 팩 선택** 대화 상자에서 **닫기**를 클릭합니다. 가져오기 및 설치 프로세스는 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-p109">In the **Select Management Packs** dialog box, click **Close**. Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="b91c4-136">Operations Manager 셸을 사용 하 여 관리 팩 가져오기</span><span class="sxs-lookup"><span data-stu-id="b91c4-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="b91c4-137">일반적으로 Operations Manager를 사용 하 여 관리 팩을 가져오는 것이 더 쉽습니다. 그러나 오류가 발생 하 고 가져오기가 실패 하면 콘솔에서 적절 한 오류 보고서를 제공 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="b91c4-138">Operations Manager 셸에서는 비교를 통해 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="b91c4-139">Operations Manager를 사용 하는 경우 관리 팩을 가져오는 동안 문제가 발생 하면 Operations Manager 셸을 사용 하 여 팩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="b91c4-140">Operations Manager 셸은 가져오기가 실패 한 이유를 확인 하는 데 도움이 되는 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="b91c4-141">System Center Operations Manager 2007 R2를 사용 하는 경우 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="b91c4-142">**시작**, **모든 프로그램**, **System Center Operations Manager 2007 R2**를 차례로 클릭 한 다음 **Operations manager Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="b91c4-143">Operations Manager 셸에서 명령 프롬프트에 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 파일 복사본의 실제 경로를 사용 하 여 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="b91c4-144">첫 번째 관리 팩을 가져온 후 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 파일의 복사본에 대한 경로를 사용해서 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="b91c4-145">Operations Manager 셸을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="b91c4-146">System Center Operations Manager 2012를 사용 하는 경우에는이 절차를 대신 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="b91c4-147">**시작**, **모든 프로그램**, **Microsoft System Center 2012**, **operations manager**, **operations manager 셸을**차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="b91c4-148">Operations Manager 셸에서 명령 프롬프트에 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 파일 복사본의 실제 경로를 사용 하 여 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="b91c4-149">첫 번째 관리 팩을 가져온 후 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 파일의 복사본에 대한 경로를 사용해서 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b91c4-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

