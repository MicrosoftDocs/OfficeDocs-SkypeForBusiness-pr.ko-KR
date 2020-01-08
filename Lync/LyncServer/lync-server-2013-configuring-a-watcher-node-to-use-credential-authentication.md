---
title: 'Lync Server 2013: 자격 증명 인증을 사용 하도록 감시자 노드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="96447-102">Lync Server 2013에서 자격 증명 인증을 사용 하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="96447-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96447-103">_**마지막으로 수정한 주제:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="96447-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="96447-104">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우에는 가상 트랜잭션을 실행 하도록 감시자 노드를 구성 하기 위해 약간 다른 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-104">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions.</span></span> <span data-ttu-id="96447-105">특히 신뢰할 수 있는 응용 프로그램 풀과 신뢰할 수 있는 응용 프로그램을 만들지 않아야 하며, 감시자 노드가 경계 네트워크 내의 컴퓨터에 알림을 보낼 수 있도록 하는 인증서를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-105">Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network.</span></span> <span data-ttu-id="96447-106">즉, 다음과 같은 두 개의 개별 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-106">This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="96447-107">컴퓨터의 RTC 로컬 읽기 전용 관리자 그룹의 구성원을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="96447-108">감시자 노드 구성 파일 설치</span><span class="sxs-lookup"><span data-stu-id="96447-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="96447-109">RTC 로컬 읽기 전용 관리자 그룹의 구성원 업데이트</span><span class="sxs-lookup"><span data-stu-id="96447-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="96447-110">감시자 노드가 경계 네트워크 외부에 있는 경우 감시자 노드 컴퓨터의 RTC 로컬 읽기 전용 관리자 그룹에 네트워크 서비스 계정을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-110">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer.</span></span> <span data-ttu-id="96447-111">이렇게 하려면 감시자 노드에서 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-111">To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="96447-112">**시작**을 클릭 하 고 **컴퓨터**를 마우스 오른쪽 단추로 클릭 한 다음 **관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="96447-113">서버 관리자에서 **구성을**확장 하 고 **로컬 사용자 및 그룹**을 확장 한 다음 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="96447-114">그룹 창에서 **RTC 로컬 읽기 전용 관리자**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="96447-115">**RTC 로컬 읽기 전용 관리자 속성** 대화 상자에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="96447-116">**사용자, 컴퓨터, 서비스 계정 또는 그룹 선택** 대화 상자에서 **위치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="96447-117">**위치** 대화 상자에서 감시자 노드 컴퓨터의 이름을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="96447-118">**선택할 개체 이름 입력** 상자에 **네트워크 서비스**를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="96447-119">**RTC 로컬 읽기 전용 관리자 속성** 대화 상자에서 **확인**을 클릭 한 다음 **서버 관리자**를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="96447-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="96447-120">감시자 노드 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="96447-121">감시자 노드 구성 파일 설치</span><span class="sxs-lookup"><span data-stu-id="96447-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="96447-122">감시자 노드 컴퓨터가 다시 시작 되 면 다음 단계는 Watchernode 파일을 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96447-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="96447-123">이 파일을 실행 하려면 **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 lync server **2013**을 클릭 하 고 **lync Server Management shell**을 클릭 하 여 lync server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96447-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="96447-124">Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다 (Watchernode 복사본의 실제 경로를 지정 하 고 있어야 합니다.).</span><span class="sxs-lookup"><span data-stu-id="96447-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="96447-125">앞에서 설명한 대로 명령 창에서 Watchernode를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96447-125">As noted previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="96447-126">명령 창을 열려면 <STRONG>시작</STRONG>을 클릭 하 고 <STRONG>명령 프롬프트</STRONG>를 마우스 오른쪽 단추로 클릭 한 다음 <STRONG>관리자 권한으로 실행</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-126">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="96447-127">명령 창이 열리면 앞에서 설명한 것과 같은 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-127">When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="96447-128">협상 모드는 감시자 노드가 신뢰 된 응용 프로그램 풀로 설정 될 수 없을 때마다 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96447-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="96447-129">이 모드에서는 관리자가 감시자 노드에서 테스트 사용자 암호를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96447-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

