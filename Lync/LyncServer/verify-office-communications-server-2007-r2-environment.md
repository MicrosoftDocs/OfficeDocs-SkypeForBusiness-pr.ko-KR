---
title: Office Communications Server 2007 R2 환경 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369ad631b772e0a73677ab3214e24083426148a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="42cc5-102">Office Communications Server 2007 R2 환경 확인</span><span class="sxs-lookup"><span data-stu-id="42cc5-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42cc5-103">_**마지막으로 수정한 주제:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="42cc5-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="42cc5-104">Office Communications Server 2007 R2를 사용 하 여 Lync Server 2013을 공존 상태로 배포 하기 전에 Office Communications Server 2007 R2 서비스가 구성 및 시작 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="42cc5-105">**Office Communications Server 2007 R2 관리 도구를 사용 하 여 풀이 시작 되었는지 확인**</span><span class="sxs-lookup"><span data-stu-id="42cc5-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="42cc5-106">Office Communications Server 2007 R2 관리 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="42cc5-107">**포리스트** 노드를 확장 하 고 **스탠더드 버전 서버** 또는 **엔터프라이즈 풀** 노드를 확장 한 다음 풀 또는 서버 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="42cc5-108">서비스가 Standard Edition server 또는 엔터프라이즈 풀에서 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="42cc5-109">![Office Communications server 2007 R2 관리 콘솔](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "office Communications Server 2007 R2 관리 콘솔")</span><span class="sxs-lookup"><span data-stu-id="42cc5-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="42cc5-110">**Office Communications Server 2007 R2에 대해 구성 된 사용자 검토**</span><span class="sxs-lookup"><span data-stu-id="42cc5-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="42cc5-111">Office Communications Server 2007 R2 관리 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="42cc5-112">**포리스트** 노드를 확장 하 고 **스탠더드 버전 서버** 또는 **엔터프라이즈 풀** 노드를 확장 한 다음 풀 또는 서버 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="42cc5-113">**사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-113">Click **Users**.</span></span>

4.  <span data-ttu-id="42cc5-114">Office Communications Server 2007 R2 사용자의 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="42cc5-115">![Ocs 관리 도구의 사용자 목록](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "ocs 관리 도구의 사용자 목록")</span><span class="sxs-lookup"><span data-stu-id="42cc5-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="42cc5-116">**레거시 XMPP 페더레이션 파트너 구성 확인**</span><span class="sxs-lookup"><span data-stu-id="42cc5-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="42cc5-117">레거시 XMPP 서버에서 관리 도구\\서비스 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="42cc5-118">Office Communications Server XMPP 게이트웨이 서비스가 시작 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cc5-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="42cc5-119">![Office Communications server XMPP 게이트웨이 서비스](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "office communications Server Xmpp 게이트웨이 서비스")</span><span class="sxs-lookup"><span data-stu-id="42cc5-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

