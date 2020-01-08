---
title: 서비스에 대한 세션 방지
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f3ed7c788db120782966541bfea9813328d90c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="65bd2-102">서비스에 대한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="65bd2-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65bd2-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="65bd2-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="65bd2-104">Microsoft Lync Server 2010 제어판을 사용 하 여 특정 컴퓨터에서 실행 중인 모든 Lync Server 2010 서비스에 대 한 새 세션을 방지 하거나 특정 Lync Server 2010 서비스에 대 한 새 세션을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="65bd2-105">컴퓨터의 모든 Lync Server 서비스에 대해 새 세션을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="65bd2-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="65bd2-106">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="65bd2-107">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="65bd2-108">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="65bd2-109">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 새 세션을 방지 하려는 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="65bd2-110">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-110">Click **Action**.</span></span>

6.  <span data-ttu-id="65bd2-111">**모든 서비스에 대해 새 세션 금지를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="65bd2-112">특정 서비스에 대 한 새 세션을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="65bd2-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="65bd2-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="65bd2-114">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="65bd2-115">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="65bd2-116">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="65bd2-117">**속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="65bd2-118">필요한 경우 서비스 목록을 정렬 하 고 새 세션을 방지 하려는 서비스를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="65bd2-119">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-119">Click **Action**.</span></span>

8.  <span data-ttu-id="65bd2-120">**서비스에 대해 새 세션 금지를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="65bd2-121">**닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bd2-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

