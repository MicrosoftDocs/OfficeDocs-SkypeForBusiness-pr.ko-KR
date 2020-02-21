---
title: 'Lync Server 2013: 영구 채팅에 대 한 사이트 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e910b9266259f8a37a3e1f1576c084c3ac7e1e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="a6474-102">Lync Server 2013에서 영구 채팅에 대 한 사이트 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a6474-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6474-103">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a6474-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a6474-104">배포한 각 사이트에 대해 사이트별 영구 채팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="a6474-105">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6474-106">영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="a6474-107">자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6474-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="a6474-108">영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서에서 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013의 전역 또는 영구 채팅 서버 풀에 대해 영구 채팅 서버 옵션 구성</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6474-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="a6474-109">사이트에 대 한 영구 채팅 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a6474-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="a6474-110">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6474-111">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="a6474-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6474-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6474-113">왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **영구적 채팅 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a6474-114">Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a6474-115">자세한 내용은 배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6474-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="a6474-116">**새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="a6474-117">**사이트 선택**에서 정책을 적용할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="a6474-118">**새 영구적 채팅 정책**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="a6474-119">**이름**에서 새 사이트 정책의 이름을 지정합니다(예: Redmond).</span><span class="sxs-lookup"><span data-stu-id="a6474-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="a6474-120">**설명**에서 사이트 정책에 대한 자세한 설명을 입력합니다(예: Redmond용 채팅방 정책).</span><span class="sxs-lookup"><span data-stu-id="a6474-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="a6474-121">사이트 정책을 통해 제어 되지 않는 모든 사이트에 대해 영구 채팅을 제어 하려면 **영구 채팅 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="a6474-122">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6474-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

