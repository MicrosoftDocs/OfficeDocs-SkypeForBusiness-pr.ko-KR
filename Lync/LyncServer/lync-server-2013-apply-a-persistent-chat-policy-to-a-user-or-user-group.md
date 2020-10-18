---
title: 'Lync Server 2013: 사용자 또는 사용자 그룹에 영구 채팅 정책 적용'
description: 'Lync Server 2013: 사용자 또는 사용자 그룹에 영구 채팅 정책을 적용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 168fa795303bbcf3f3eef4bfc817aa98d763d1ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573484"
---
# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="67b5e-103">Lync Server 2013의 사용자 또는 사용자 그룹에 영구 채팅 정책 적용</span><span class="sxs-lookup"><span data-stu-id="67b5e-103">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67b5e-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="67b5e-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="67b5e-105">사용자가 Lync Server 2013를 사용할 수 있도록 설정 된 경우에는 영구 채팅 서버에 대해 적절 한 정책을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-105">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67b5e-106">영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="67b5e-107">자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67b5e-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="67b5e-108">영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서에서 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013의 전역 또는 영구 채팅 서버 풀에 대해 영구 채팅 서버 옵션 구성</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67b5e-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="67b5e-109">이전에 만든 영구 채팅 사용자 정책을 하나 이상의 사용자 계정 또는 사용자 그룹에 적용 하려면이 항목의 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-109">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="67b5e-110">사용자 계정에 영구 채팅 사용자 정책을 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="67b5e-110">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="67b5e-111">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-111">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67b5e-112">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="67b5e-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67b5e-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67b5e-114">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-114">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="67b5e-115">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-115">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="67b5e-116">**영구 채팅 정책**아래의 **Lync Server 사용자 편집** 에서 적용할 영구 채팅 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-116">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67b5e-117"><STRONG> &lt; 자동 &gt; </STRONG> 설정은 기본 유효 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-117">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="67b5e-118">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-118">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="67b5e-119">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67b5e-119">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

