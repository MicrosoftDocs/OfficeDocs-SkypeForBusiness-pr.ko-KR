---
title: 'Lync Server 2013: 새 신뢰할 수 있는 응용 프로그램 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e370c229442d90d6e962f0d73efbf4b94038926a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="29a05-102">Lync Server 2013에서 신뢰할 수 있는 새 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="29a05-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29a05-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29a05-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29a05-104">신뢰할 수 있는 응용 프로그램은 Microsoft Lync Server 2013에서 신뢰할 수 있는 Microsoft 통합 커뮤니케이션 관리 API (가) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="29a05-105">부분 [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)ma 응용 프로그램에 대 한 자세한 내용은의 "통합 커뮤니케이션 관리 API 3.0 Core SDK 설명서"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29a05-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="29a05-106">Microsoft OWA (Outlook web Access) 및 Lync Server 2013을 구성 하는 방법에 대 한 자세한 내용은 Microsoft Exchange Server 2013 설명서에서 "Outlook Web App 및 Lync Server 2010 통합 구성"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29a05-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="29a05-107">서버 역할을 추가하거나 제거할 때 토폴로지를 게시, 사용하도록 설정 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원인 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="29a05-108">적절한 관리자 권한을 위임하여 서버 역할을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="29a05-109">자세한 내용은 배포 설명서에서 [Lync Server 2013의 대리인 설치 권한](lync-server-2013-delegate-setup-permissions.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29a05-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="29a05-110">기타 구성을 변경하려는 경우에는 RTCUniversalServerAdmins 그룹 구성원 자격만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="29a05-111">신뢰할 수 있는 응용 프로그램 서버를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="29a05-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="29a05-112">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="29a05-113">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="29a05-114">**기존 배포에서 토폴로지 다운로드** 및 **확인**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="29a05-115">토폴로지를 **다른 이름으로 저장** 대화 상자에서 사용할 토폴로지 작성기 파일을 클릭 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="29a05-116">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="29a05-117">신뢰할 수 있는 응용 프로그램 풀에 대한 **풀 FQDN**을 입력하고 단일 서버로 설정할지 다중 서버로 설정할지 여부를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="29a05-118">**다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="29a05-119">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="29a05-120">최상위 노드 **Lync Server 2013**을 선택한 다음 **동작** 메뉴에서 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="29a05-121">**신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어졌으며 올바른 프런트 엔드 풀과 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a05-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

