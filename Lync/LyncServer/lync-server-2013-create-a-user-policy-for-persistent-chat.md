---
title: 'Lync Server 2013: 영구 채팅에 대한 사용자 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a9bd88dd84b8b5056adf19ebc098daac54cb005
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="4d542-102">Lync Server 2013에서 영구 채팅에 대한 사용자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4d542-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d542-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="4d542-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="4d542-104">Lync 서버 제어판에서 **사용자에 게**할당할 수 있는 사용자 정책을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="4d542-105">사용자 정책은 해당 정책이 할당된 특정 사용자에 한해 전역 정책 및 사이트 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d542-106">영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="4d542-107">자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d542-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="4d542-108">영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서의 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync Server 2013에서 영구 채팅 서버 옵션을 전역적으로 또는 영구 채팅 서버 풀에 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d542-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="4d542-109">영구 채팅에 대 한 사용자 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4d542-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="4d542-110">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d542-111">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="4d542-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d542-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d542-113">Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4d542-114">배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d542-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="4d542-115">왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **영구 채팅 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="4d542-116">**새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="4d542-117">**새 영구 채팅 정책**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="4d542-118">**이름**에 새 사용자 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="4d542-119">**설명**에서 사용자 정책에 대 한 세부 정보를 제공 합니다 (예: 특정 사용자의 영구 채팅 정책).</span><span class="sxs-lookup"><span data-stu-id="4d542-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="4d542-120">사용자 정책을 통해 구체적으로 제어 되지 않는 모든 사용자의 영구 채팅을 제어 하려면 **영구 채팅 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="4d542-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d542-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

