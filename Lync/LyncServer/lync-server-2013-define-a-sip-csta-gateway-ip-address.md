---
title: 'Lync Server 2013: SIP/CSTA 게이트웨이 IP 주소 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3a88aa2209617a93b0feebf7c1cc6d8cccd0cf7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516385"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="0f9eb-102">Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의</span><span class="sxs-lookup"><span data-stu-id="0f9eb-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f9eb-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0f9eb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0f9eb-104">Lync Server가 TCP (전송 제어 프로토콜) 연결을 사용 하 여 원격 통화 제어를 위해 배포한 SIP/CSTA 게이트웨이에 연결 하는 경우에는 토폴로지 작성기에서 게이트웨이의 IP 주소를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="0f9eb-105">TLS (전송 계층 보안) 연결을 지 원하는 게이트웨이에는이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="0f9eb-106">TLS 연결을 지 원하는 모든 게이트웨이에서는 [Lync Server 2013의 원격 통화 제어에 lync 사용자 사용 컨트롤](lync-server-2013-enable-lync-users-for-remote-call-control.md)의 단계를 수행 하 여이 절차를 건너뛰고 원격 통화 제어의 배포를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="0f9eb-107">토폴로지 작성기를 사용 하 여 SIP/CSTA 게이트웨이 IP 주소를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="0f9eb-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="0f9eb-108">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0f9eb-109">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="0f9eb-110">기존 토폴로지를 다운로드 하는 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="0f9eb-111">**신뢰할 수 있는 응용 프로그램 서버** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="0f9eb-112">[Lync Server 2013의 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)에 설명 된 대로 앞서 만든 신뢰할 수 있는 응용 프로그램 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="0f9eb-113">**이 풀에 대 한 구성 데이터 복제 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="0f9eb-114">**선택한 IP 주소로 서비스 사용 제한을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="0f9eb-115">기본 설정은 구성 된 **모든 IP 주소를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="0f9eb-116">**기본 IP 주소** 텍스트 상자에 SIP/CSTA 게이트웨이의 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="0f9eb-117">중앙 관리 저장소에서 토폴로지를 업데이트 하려면 콘솔 트리에서 **Lync Server**를 클릭 하 고 **작업** 창에서 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f9eb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f9eb-118">See Also</span></span>


[<span data-ttu-id="0f9eb-119">Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성</span><span class="sxs-lookup"><span data-stu-id="0f9eb-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="0f9eb-120">Lync Server 2013에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성</span><span class="sxs-lookup"><span data-stu-id="0f9eb-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

