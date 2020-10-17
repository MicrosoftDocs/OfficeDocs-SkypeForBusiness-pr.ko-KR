---
title: 'Lync Server 2013: 영구 채팅에 대 한 글로벌 정책 구성'
description: 'Lync Server 2013: 영구 채팅에 대 한 글로벌 정책을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 830074c31791ee8ff489d9a67af189be609c7f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544944"
---
# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="86b3a-103">Lync Server 2013에서 영구 채팅에 대 한 글로벌 정책 구성</span><span class="sxs-lookup"><span data-stu-id="86b3a-103">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b3a-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="86b3a-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="86b3a-105">기본 전역 정책을 단독으로 사용 하 여 배포의 모든 사용자에 대해 영구 채팅 설정을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-105">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="86b3a-106">사이트 및 사용자에 대 한 추가 정책을 지정 하 여 특정 사용자 및 사이트에 대해 영구 채팅을 사용할지 여부를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-106">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="86b3a-107">글로벌 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-107">You cannot delete the global policy.</span></span> <span data-ttu-id="86b3a-108">글로벌 정책을 삭제하려고 하면 구성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-108">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86b3a-109">영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-109">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="86b3a-110">자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="86b3a-110">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="86b3a-111">영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서에서 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013의 전역 또는 영구 채팅 서버 풀에 대해 영구 채팅 서버 옵션 구성</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="86b3a-111">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="86b3a-112">영구 채팅에 대 한 글로벌 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="86b3a-112">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="86b3a-113">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-113">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="86b3a-114">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-114">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="86b3a-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="86b3a-115">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="86b3a-116">Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-116">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="86b3a-117">자세한 내용은 배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="86b3a-117">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="86b3a-118">Lync Server 제어판에서 **영구 채팅**을 클릭 하 고 **영구 채팅 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-118">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="86b3a-119">정책 목록에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="86b3a-120">**영구적 채팅 정책 편집 - 전역**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="86b3a-121">**이름**에서 글로벌 정책의 새 이름을 지정합니다(기본값인 "전역"을 사용하지 않으려는 경우).</span><span class="sxs-lookup"><span data-stu-id="86b3a-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="86b3a-122">**설명**에 사용자 정책에 대 한 자세한 정보를 제공 합니다 (예:: centralsitename에 대 한 글로벌 정책).</span><span class="sxs-lookup"><span data-stu-id="86b3a-122">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="86b3a-123">사이트 정책 또는 사용자 정책을 통해 제어 되지 않는 모든 사이트 및 사용자에 대해 영구 채팅을 제어 하려면 **영구 채팅 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="86b3a-124">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="86b3a-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

