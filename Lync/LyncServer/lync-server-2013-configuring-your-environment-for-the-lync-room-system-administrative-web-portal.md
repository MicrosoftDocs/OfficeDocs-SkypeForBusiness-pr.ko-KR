---
title: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털에 대 한 환경 구성'
description: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털에 대 한 환경 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942e1db799a7336a3eafb5571e82584694ddbf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542204"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="27a06-103">Lync 대화방 시스템 관리 웹 포털에 대 한 Lync Server 2013 환경 구성</span><span class="sxs-lookup"><span data-stu-id="27a06-103">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27a06-104">_**마지막으로 수정 된 항목:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="27a06-104">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="27a06-105">LRS (Lync 대화방 시스템) 관리 웹 포털을 사용 하려면 다음 필수 구성 요소를 설치 하거나 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-105">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="27a06-106">서버가 Kerberos 인증과 NTLM 인증을 모두 사용 하 여 구성 되었지만 도메인에 가입 되지 않은 컴퓨터에서 LRS가 실행 되 고 있으면 Kerberos 인증이 실패 하 고 사용자에 게 관리 포털의 LRS 상태가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-106">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="27a06-107">이 문제를 해결 하려면 NTLM 인증 또는 NTLM 및 DSK 인증 (Kerberos 제외)을 사용 하 여 서버를 구성 하거나 LRS 컴퓨터를 도메인에 참가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-107">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="27a06-108">Lync server 토폴로지에서 Lync Server 2013 누적 업데이트: 7 월 2013을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-108">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="27a06-109">업데이트를 가져오거나 여기에 포함 된 항목을 확인 하려면 [Lync Server 2013 용 업데이트](https://go.microsoft.com/fwlink/p/?linkid=323959)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27a06-109">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="27a06-110">SIP 사용이 가능한 Active Directory 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-110">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="27a06-111">LRS 관리 웹 포털은 이러한 자격 증명을 사용 하 여 Lync Server에서 정보를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-111">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="27a06-112">권장 사용자 이름은 LRSApp입니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-112">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="27a06-113">이름이 LRSSupportAdminGroup 인 Active Directory 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-113">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="27a06-114">그룹 범위가 글로벌이 고 그룹 유형이 Security 인 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-114">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="27a06-115">SIP 사용이 그룹에 추가 된 사용자는 대화방 목록을 확인 하 고 로그 수집과 같은 특정 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-115">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="27a06-116">이름이 LRSFullAccessAdminGroup 인 Active Directory 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-116">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="27a06-117">그룹 범위가 글로벌이 고 그룹 유형이 Security 인 그룹을 만듭니다 .이 그룹에 추가 된 SIP 사용 사용자에 게는 모든 관리자 포털 기능을 사용할 수 있는 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-117">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="27a06-118">![보안 그룹 역할이 포함 된 관리자 그룹 목록](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "보안 그룹 역할이 포함 된 관리자 그룹 목록")</span><span class="sxs-lookup"><span data-stu-id="27a06-118">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="27a06-119">LRSFullAccessAdminGroup을 LRSSupportAdminGroup의 구성원으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-119">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="27a06-120">![LRSSupportAdminGroup Properties Members 페이지](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members 페이지")</span><span class="sxs-lookup"><span data-stu-id="27a06-120">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="27a06-121">이름이 LRSSupport 인 SIP 사용 Active Directory 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-121">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="27a06-122">이 사용자를 LRSSupportAdminGroup에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-122">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="27a06-123">![LRSSupportAdminGroup Properties Members 페이지](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members 페이지")</span><span class="sxs-lookup"><span data-stu-id="27a06-123">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="27a06-124">Microsoft 다운로드 센터에서 사용할 수 있는 Visual Studio 2010 SP1 및 Visual Web Developer 2010 s p 1 용 ASP.NET MVC 4를 설치 [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a06-124">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

