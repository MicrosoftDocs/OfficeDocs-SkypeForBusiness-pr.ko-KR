---
title: 중재 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb9b2c7cf8da1d454f310a8ac999dddbc7d34f68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="65aee-102">중재 서버 구성</span><span class="sxs-lookup"><span data-stu-id="65aee-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65aee-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="65aee-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="65aee-104">이 절차에서는 레거시 Office Communications Server 2007 R2 중재 서버 대신 Lync server 2013 조정 서버를 사용 하도록 Lync Server 2013 풀을 구성 하는 단계에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="65aee-105">서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="65aee-106">또한 적절 한 관리자 권한 및 서버 역할 추가 권한을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="65aee-107">자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서에서 설치 권한 위임을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65aee-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="65aee-108">다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65aee-109">Lync Server 2013와 작동 하는 정규화 된 PSTN 게이트웨이, IP Pbx 및 SIP 트렁크 서비스를 찾는 방법에 대 한 최신 정보는에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>"Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65aee-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="65aee-110">토폴로지 작성기를 사용 하 여 중재 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="65aee-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="65aee-111">토폴로지 작성기에서 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="65aee-112">왼쪽 창에서 **PSTN 게이트웨이로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="65aee-113">**PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭 한 다음 **새 IP/PSTN 게이트웨이**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="65aee-114">다음 정보를 사용 하 여 **새 IP/PSTN 게이트웨이 정의** 페이지를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="65aee-115">게이트웨이 FQDN 또는 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="65aee-116">게이트웨이에서 TLS 프로토콜을 사용 하는 경우 게이트웨이의 FQDN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="65aee-117">**IP/PSTN 게이트웨이의 기본 수신 포트** 값을 적용 하거나, 수정 된 경우 새 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="65aee-118">**Sip 전송 프로토콜**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="65aee-119">왼쪽 창에서 **Enterprise Edition 프런트 엔드 풀** 또는 **Standard Edition 서버로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="65aee-120">풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="65aee-121">**중재 서버**에서 **수신 대기 포트**를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="65aee-122">다음으로 새로 만든 PSTN 게이트웨이를 선택 하 고 **추가**를 클릭 하 여 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="65aee-123">**토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="65aee-124">**작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="65aee-125">**게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65aee-126"><A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">새로운 Lync server 2013 조정 서버를 사용 하</A> 여 음성 경로가 올바른 중재 서버를 가리키고 있는지 확인 하려면 다음 항목을 완료 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="65aee-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

