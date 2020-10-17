---
title: 서비스에 대한 세션 방지
description: 서비스에 대 한 세션을 차단 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563694"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="6a552-103">서비스에 대한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="6a552-103">Prevent sessions for services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a552-104">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="6a552-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="6a552-105">Microsoft Lync Server 2010 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 Lync Server 2010 서비스에 대 한 새 세션을 차단 하거나 특정 Lync Server 2010 서비스에 대해 새 세션을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-105">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="6a552-106">컴퓨터의 모든 Lync Server 서비스에 대한 새 세션을 금지하려면</span><span class="sxs-lookup"><span data-stu-id="6a552-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="6a552-107">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6a552-108">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-108">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="6a552-109">왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="6a552-110">**상태** 페이지에서 새 세션을 금지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="6a552-111">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-111">Click **Action**.</span></span>

6.  <span data-ttu-id="6a552-112">**모든 서비스에 대한 새 세션 금지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="6a552-113">특정 서비스에 대한 새 세션을 금지하려면</span><span class="sxs-lookup"><span data-stu-id="6a552-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="6a552-114">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6a552-115">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-115">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="6a552-116">왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-116">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="6a552-117">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-117">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="6a552-118">**속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-118">Click **Properties**.</span></span>

6.  <span data-ttu-id="6a552-119">필요한 경우 서비스 목록을 정렬하고 새 세션을 금지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-119">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="6a552-120">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-120">Click **Action**.</span></span>

8.  <span data-ttu-id="6a552-121">**서비스에 대한 새 세션 금지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-121">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="6a552-122">**닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a552-122">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

