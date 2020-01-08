---
title: 'Lync Server 2013: 신뢰할 수 있는 새 응용 프로그램 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="196d7-102">Lync Server 2013에서 신뢰할 수 있는 새 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="196d7-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="196d7-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="196d7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="196d7-104">신뢰할 수 있는 응용 프로그램은 Microsoft Lync Server 2013에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 MA) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="196d7-105">(C) MA 응용 프로그램에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)"통합 커뮤니케이션 관리 API 3.0 Core SDK 설명서"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196d7-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="196d7-106">Microsoft OWA (Outlook Web Access) 및 Lync Server 2013를 구성 하는 방법에 대 한 자세한 내용은 Microsoft Exchange Server 2013 설명서의 "Outlook Web App 및 Lync Server 2010 통합 구성"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196d7-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="196d7-107">서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="196d7-108">또한 적절 한 관리자 권한과 서버 역할 추가 권한을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="196d7-109">자세한 내용은 배포 설명서의 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="196d7-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="196d7-110">다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="196d7-111">신뢰할 수 있는 응용 프로그램 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="196d7-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="196d7-112">도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="196d7-113">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="196d7-114">**기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="196d7-115">**다른 이름으로 토폴로지 저장** 대화 상자에서 사용할 토폴로지 작성기 파일을 클릭 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="196d7-116">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="196d7-117">신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고,이를 단일 서버 또는 다중 서버 중에서 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="196d7-118">**다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="196d7-119">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="196d7-120">최상위 노드 **Lync Server 2013**을 선택한 다음 **작업** 메뉴에서 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="196d7-121">**신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어지고 올바른 프런트 엔드 풀에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="196d7-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

