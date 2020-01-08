---
title: 'Lync Server 2013: 분기 사이트에 대한 PSTN 게이트웨이 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="ea89f-102">Lync Server 2013에서 분기 사이트에 대한 PSTN 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="ea89f-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea89f-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ea89f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ea89f-104">하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버가 포함 된 중앙 사이트에서이 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea89f-105">절차를 수행 하기 전에 다음 조건이 충족 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ea89f-106">Lync Server 2013&nbsp;통신 소프트웨어는 중앙 사이트에 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="ea89f-107">중재 서버는 중앙 사이트에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="ea89f-108">PSTN 게이트웨이를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="ea89f-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="ea89f-109">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ea89f-110">콘솔 트리에서 중앙 사이트를 확장 하 고, **지점**사이트를 확장 하 고, 다음에 대 한 PSTN (공용 전환 전화 네트워크) 게이트웨이를 정의 하려는 지점 사이트의 이름을 확장 한 다음 **공유 구성 요소**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="ea89f-111">**PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭 한 다음 **새 IP/PSTN 게이트웨이**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="ea89f-112">**새 IP/PSTN 게이트웨이 정의** 대화 상자에서 **게이트웨이 Fqdn 또는 IP 주소**를 클릭 한 다음 지점 사이트에서 배포 하려는 게이트웨이의 FQDN (정규화 된 도메인 이름) 또는 ip 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="ea89f-113">**IP/PSTN 게이트웨이의 수신 대기 포트**를 클릭 한 다음 기본값을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="ea89f-114">**SIP 전송 프로토콜** 목록에서 게이트웨이에서 사용 하는 전송 프로토콜을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea89f-115">보안상의 이유로 TLS (전송 계층 보안)를 지 원하는 PSTN 게이트웨이를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="ea89f-116">이 <STRONG>(가) Cmdlet 집합-CsPstnGateway</STRONG> 를 사용 하 여 PSTN 게이트웨이의 속성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea89f-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="ea89f-117">자세한 내용은 Lync Server 관리 셸 도움말에서 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea89f-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="ea89f-118">지점 사이트 복원에 대 한 **다음 단계** : [Lync Server 2013에서 지점 사이트 복원에 대 한 사용자 구성](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="ea89f-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea89f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea89f-119">See Also</span></span>


[<span data-ttu-id="ea89f-120">Lync Server 2013의 PSTN 게이트웨이 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="ea89f-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

