---
title: 'Lync Server 2013: Lync 채팅방 시스템 관리 웹 포털에 대한 환경 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef7596e65c44f871da8c26a0526a389dde72a45
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="2789f-102">Lync 채팅방 시스템 관리 웹 포털에 대한 Lync Server 2013 환경 구성</span><span class="sxs-lookup"><span data-stu-id="2789f-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2789f-103">_**마지막으로 수정한 주제:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="2789f-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="2789f-104">Lync 채팅방 시스템 (LRS) 관리 웹 포털을 사용 하려면 다음 필수 구성 요소를 설치 하거나 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2789f-105">서버가 Kerberos 및 NTLM 인증을 모두 사용 하도록 구성 되었고 도메인에 가입 되지 않은 컴퓨터에서 LRS가 실행 되는 경우 Kerberos 인증이 실패 하 고 사용자가 관리 포털에서 LRS의 상태를 볼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="2789f-106">이 문제를 해결 하려면 ntlm 인증 또는 NTLM 및 TLS DSK 인증 (Kerberos 불포함)을 사용 하 여 서버를 구성 하거나 LRS 컴퓨터를 도메인에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="2789f-107">Lync server 2013 누적 업데이트 설치: Lync Server 토폴로지에서는 7 월 2013입니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="2789f-108">업데이트를 다운로드 하거나 포함 된 항목을 보려면 [Lync Server 2013 업데이트](http://go.microsoft.com/fwlink/p/?linkid=323959)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2789f-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="2789f-109">SIP 지원 Active Directory 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="2789f-110">LRS 관리 웹 포털은 이러한 자격 증명을 사용 하 여 Lync Server에서 정보를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="2789f-111">추천 사용자 이름은 LRSApp입니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="2789f-112">이름 LRSSupportAdminGroup를 사용 하 여 Active Directory 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="2789f-113">그룹 범위가 전역 및 그룹 유형으로 보안으로 지정 된 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="2789f-114">SIP 사용이 가능이 그룹에 추가 된 사용자는 채팅방 목록을 볼 수 있도록 승인 되 고 로그 수집과 같은 특정 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="2789f-115">이름 LRSFullAccessAdminGroup를 사용 하 여 Active Directory 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="2789f-116">그룹 범위가 글로벌이 고 그룹 유형이 보안으로 설정 된 그룹을 만듭니다 .이 그룹에 추가 된 SIP는 모든 관리 포털 기능을 사용할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="2789f-117">(images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "보안 그룹 역할이 있는 관리자 그룹의") ![보안 그룹 역할 목록이 있는 관리자 그룹 목록]</span><span class="sxs-lookup"><span data-stu-id="2789f-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="2789f-118">LRSFullAccessAdminGroup를 LRSSupportAdminGroup의 구성원으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="2789f-119">![LRSSupportAdminGroup 속성 멤버 페이지](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 속성 멤버 페이지")</span><span class="sxs-lookup"><span data-stu-id="2789f-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="2789f-120">이름 LRSSupport를 사용 하 여 SIP 활성화 된 Active Directory 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="2789f-121">이 사용자를 LRSSupportAdminGroup에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="2789f-122">![LRSSupportAdminGroup 속성 멤버 페이지](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 속성 멤버 페이지")</span><span class="sxs-lookup"><span data-stu-id="2789f-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="2789f-123">Microsoft 다운로드 센터에서 제공 되는 Visual Studio 2010 SP1 및 Visual Web Developer 2010 SP1 용 ASP.NET MVC 4를 설치 [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)합니다.</span><span class="sxs-lookup"><span data-stu-id="2789f-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

