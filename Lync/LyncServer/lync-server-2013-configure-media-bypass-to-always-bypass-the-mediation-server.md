---
title: 'Lync Server 2013: 중재 서버를 항상 우회 하도록 미디어 우회 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0023fba32b24243dc4bf2a12659700ace6dea91a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="cd605-102">Lync Server 2013에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="cd605-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd605-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="cd605-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd605-104">이 항목에서는 특정 사용자가 피어 (공공 교환 전화 네트워크 (PSTN) 게이트웨이, IP-PBX 또는 인터넷 통신 서비스 공급자 (ITSP)의 세션 경계 컨트롤러 (SBC)에 대 한 모든 트렁크 연결에 미디어 바이패스를 이미 구성 했다고 가정 합니다. 미디어를 사용 하 여 중재 서버를 우회 하려는 사이트 또는 서비스</span><span class="sxs-lookup"><span data-stu-id="cd605-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="cd605-105">호출 허용 제어를 사용 하는 동안 항상 중재 서버를 우회 하도록 미디어를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="cd605-106">이러한 설정은 호환 되지 않으므로 Lync Server 제어판 사용자 인터페이스의 상호 배타적인 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="cd605-107">피어에 연결 된 개별 트렁크 연결에 대해 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 미디어 바이패스에 대 한 전역 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="cd605-108">이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우, 트렁크 연결에서 미디어 바이패스를 구성한 Lync 끝점과 피어 간에 연결이 양호한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="cd605-109">Lync Server 끝점 및 모든 피어가 미디어 바이패스에 대해 사용 하도록 설정 된 중재 서버에 연결 되어 있지 않은 경우에는 다음 경우에 사이트 및 지역 정보를 사용 하도록 글로벌 미디어 우회 설정을 구성 해야 합니다. 미디어 바이패스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="cd605-110">이를 통해 미디어가 중재 서버를 우회 하는 시기를 결정 하는 데 더 많은 제어가 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="cd605-111">이렇게 하려면 [Lync server 2013에서 미디어 구성 건너뛰기 전역 설정의 단계를 사용 하 여 사이트 및 지역 정보를 사용 하](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) 고 [lync server 2013의 네트워크 사이트에 서브넷을 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="cd605-112">항상 중재 서버를 우회 하기 위해 미디어 우회를 전역적으로 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="cd605-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="cd605-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cd605-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd605-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="cd605-115">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="cd605-116">목록에서 **전역** 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="cd605-117">**전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="cd605-118">**항상 무시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="cd605-119">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cd605-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd605-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd605-120">See Also</span></span>


[<span data-ttu-id="cd605-121">Lync Server 2013에서 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="cd605-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="cd605-122">Lync Server 2013의 글로벌 미디어 우회 옵션</span><span class="sxs-lookup"><span data-stu-id="cd605-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="cd605-123">Lync Server 2013의 미디어 바이패스 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="cd605-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="cd605-124">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="cd605-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

