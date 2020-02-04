---
title: 'Lync Server 2013: 음성 라우팅 구성에 보류 중인 변경 내용 게시'
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
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="8b3a9-102">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="8b3a9-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b3a9-103">_**마지막으로 수정한 주제:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="8b3a9-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="8b3a9-104">**음성 라우팅** 그룹의 페이지에서 구성 설정을 변경한 후에는이 절차를 수행 하 여 보류 중인 변경 내용을 검토 하거나 게시 하거나 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b3a9-105">한 번에 한 명의 사용자만 음성 라우팅 구성 설정을 수정 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="8b3a9-106">보류 중인 모든 변경 내용은 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 동시에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-106">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command.</span></span> <span data-ttu-id="8b3a9-107">보류 중인 변경 내용을 선택적으로 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-107">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="8b3a9-108">보류 중인 변경 내용을 게시 하기 전에 <STRONG>커밋되지 않은 변경 내용 검토</STRONG> 명령을 실행 하 고 게시 하지 않으려는 구성 변경 내용을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-108">Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="8b3a9-109">보류 중인 변경 내용을 커밋하기 전에 <STRONG>음성 라우팅</STRONG> 그룹의 페이지에서 다른 위치로 이동 하면 보류 중인 변경 내용이 모두 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="8b3a9-110">그러나 보류 중인 변경 내용을 포함 하 여 현재 구성을 음성 구성 파일로 내보낸 다음 업데이트 된 구성을 가져오고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="8b3a9-111">자세한 내용은 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013에서 음성 경로 구성 파일 내보내기를</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="8b3a9-112">음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="8b3a9-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="8b3a9-113">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8b3a9-114">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8b3a9-115">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8b3a9-116">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8b3a9-117">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="8b3a9-118">**음성 라우팅** 그룹의 각 페이지에 대 한 설정을 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="8b3a9-119">보류 중인 변경 내용을 게시 하지 않고 검토 하려면 **커밋** 메뉴에서 **커밋되지 않은 변경 내용 검토** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="8b3a9-120">보류 중인 변경 내용을 취소 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="8b3a9-121">**커밋** 메뉴에서 **커밋되지 않은 변경 내용 모두 취소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="8b3a9-122">취소 하려는 보류 중인 변경 내용이 있는 **음성 라우팅** 페이지의 탭으로 이동 하 고 보류 중인 변경 내용이 있는 항목을 선택한 다음 **커밋을**클릭 하 고 **선택한 변경 내용 취소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="8b3a9-123">보류 중인 변경 내용을 모두 검토 하 고 게시 하지 않으려는 작업을 취소 한 후에는 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="8b3a9-124">모든 보류 중인 변경 내용 목록을 표시 하는 **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="8b3a9-125">Lync Server 제어판이 변경 내용을 커밋한 경우 **성공적으로 게시 된 음성 라우팅 구성** 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3a9-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

