---
title: 'Lync Server 2013: 음성 라우팅 구성에 보류 중인 변경 내용 게시'
description: 'Lync Server 2013: 음성 라우팅 구성에 보류 중인 변경 내용을 게시 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7a56b9a07606932a34dea7149a799dbb60b376
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565454"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="45c4f-103">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="45c4f-103">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45c4f-104">_**마지막으로 수정 된 항목:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="45c4f-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="45c4f-105">**음성 라우팅** 그룹의 페이지에서 구성 설정을 변경한 후 다음 절차를 수행하여 대기 중인 변경 내용을 검토, 게시 또는 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45c4f-106">한 번에 한 명의 사용자만 음성 라우팅 구성 설정을 수정하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="45c4f-p101">대기 중인 모든 변경 내용은 <STRONG>모두 커밋</STRONG> 명령을 실행하여 동시에 게시되어야 합니다. 대기 중인 변경 내용을 선택해서 게시할 수 없습니다. 대기 중인 변경 내용을 게시하기 전에 <STRONG>커밋되지 않은 변경 내용 검토</STRONG> 명령을 실행하고 게시하지 않을 구성 변경 내용을 모두 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="45c4f-110">대기 중인 변경 내용을 커밋하기 전에 <STRONG>음성 라우팅</STRONG> 그룹의 페이지에서 이동할 경우 대기 중인 모든 변경 내용이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-110">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="45c4f-111">단, 대기 중인 모든 변경 사항을 비롯한 현재 구성을 음성 구성 파일로 내보낸 다음 업데이트된 구성을 가져오고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="45c4f-112">자세한 내용은 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013에서 음성 경로 구성 파일 내보내기를</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45c4f-112">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="45c4f-113">음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소하려면</span><span class="sxs-lookup"><span data-stu-id="45c4f-113">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="45c4f-114">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="45c4f-115">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45c4f-115">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="45c4f-116">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="45c4f-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45c4f-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="45c4f-118">왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-118">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="45c4f-119">**음성 라우팅** 그룹의 각 페이지에서 구성 설정을 원하는 대로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-119">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="45c4f-120">대기 중인 변경 내용을 게시하지 않고 검토하려면 **커밋** 메뉴에서 **커밋되지 않은 변경 내용 검토**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-120">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="45c4f-121">대기 중인 변경 내용을 취소하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-121">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="45c4f-122">**커밋** 메뉴에서 **커밋되지 않은 모든 변경 내용 취소**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-122">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="45c4f-123">취소할 대기 중인 변경 내용이 있는 **음성 라우팅** 페이지의 탭으로 이동하고 대기 중인 변경 내용이 포함된 항목을 선택한 후 **커밋**, **선택한 변경 내용 취소**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-123">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="45c4f-124">대기 중인 변경 내용을 모두 검토하고 게시하지 않을 변경 내용을 취소했으면 **커밋**, **모두 커밋**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-124">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="45c4f-125">대기 중인 모든 변경 내용에 대한 목록이 표시되는 **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-125">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="45c4f-126">Lync Server 제어판이 변경 내용을 커밋한 경우 **성공적으로 게시 된 음성 라우팅 구성** 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c4f-126">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

