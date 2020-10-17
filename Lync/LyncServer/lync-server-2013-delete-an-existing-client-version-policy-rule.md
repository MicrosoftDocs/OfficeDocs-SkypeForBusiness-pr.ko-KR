---
title: 'Lync Server 2013: 기존 클라이언트 버전 정책 규칙 삭제'
description: 'Lync Server 2013: 기존 클라이언트 버전 정책 규칙을 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48cb2dc6458406c988bdc2626fc000c7a9bf5d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553654"
---
# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="4fa25-103">Lync Server 2013에서 기존 클라이언트 버전 정책 규칙 삭제</span><span class="sxs-lookup"><span data-stu-id="4fa25-103">Delete an existing client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fa25-104">_**마지막으로 수정 된 항목:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="4fa25-104">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="4fa25-105">클라이언트 버전 정책은 클라이언트 버전 정책 규칙 집합으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-105">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="4fa25-106">이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온 하려고 할 때 수행 해야 하는 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-106">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="4fa25-107">Lync Server 2013 제어판에서 클라이언트 버전 정책 으로부터 개별 규칙을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-107">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="4fa25-108">Lync Server 제어판을 사용 하 여 클라이언트 버전 정책 규칙을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="4fa25-108">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4fa25-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4fa25-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fa25-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fa25-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fa25-112">왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 정책** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-112">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="4fa25-113">**클라이언트 버전 정책** 페이지에서 삭제할 규칙에 대 한 클라이언트 버전 정책을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-113">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="4fa25-114">이 규칙은 **클라이언트 버전 정책 편집** 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-114">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="4fa25-115">규칙을 삭제 하려면 규칙을 선택 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa25-115">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

