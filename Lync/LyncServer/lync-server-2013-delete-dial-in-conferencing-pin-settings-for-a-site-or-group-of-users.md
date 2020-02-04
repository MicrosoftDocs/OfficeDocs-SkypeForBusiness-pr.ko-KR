---
title: 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae81fd45c2679c8b4d2ab0bf6813fbb405905224
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="e2a9d-102">Lync Server 2013에서 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="e2a9d-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2a9d-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e2a9d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e2a9d-104">사용자 수준 또는 사이트 수준 PIN 정책을 삭제 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e2a9d-105">글로벌 PIN 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="e2a9d-106">사용자 또는 사이트 PIN 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="e2a9d-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="e2a9d-107">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e2a9d-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2a9d-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2a9d-110">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="e2a9d-111">**고정 정책** 페이지의 검색 필드에 삭제 하려는 정책의 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="e2a9d-112">정책 목록에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="e2a9d-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a9d-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

