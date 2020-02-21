---
title: 'Lync Server 2013: 분기 사이트에 대 한 PSTN 게이트웨이 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a47e395e74dae1eb6ec454e63fb343dcea7872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="9a70a-102">Lync Server 2013에서 분기 사이트에 대 한 PSTN 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="9a70a-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a70a-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9a70a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9a70a-104">하나 이상의 프런트 엔드 풀 또는 Standard Edition server를 포함 하는 중앙 사이트에서이 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a70a-105">절차를 수행하기 전에 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9a70a-106">Lync Server 2013&nbsp;통신 소프트웨어는 중앙 사이트에서 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="9a70a-107">중재 서버를 중앙 사이트에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="9a70a-108">PSTN 게이트웨이를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9a70a-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="9a70a-109">**시작**, **모든 프로그램**, **Microsoft Lync Server**를 차례로 클릭한 다음 **Lync Server 토폴로지 작성기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9a70a-110">콘솔 트리에서 중앙 사이트, **지점 사이트**를 차례로 확장한 다음 PSTN(공중 전화망) 게이트웨이를 정의할 분기 사이트의 이름을 확장한 후 **공유 구성 요소**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="9a70a-111">**PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭한 다음 **새 IP/PSTN 게이트웨이**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="9a70a-112">**새 IP/PSTN 게이트웨이 정의** 대화 상자에서 **게이트웨이 FQDN 또는 IP 주소**를 클릭한 다음 분기 사이트에 배포할 게이트웨이의 FQDN(정규화된 도메인 이름) 또는 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="9a70a-113">**IP/PSTN 게이트웨이용 수신 대기 포트**를 클릭한 다음 기본값을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="9a70a-114">**SIP 전송 프로토콜** 목록에서 게이트웨이가 사용하는 전송 프로토콜을 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a70a-115">보안을 위해 TLS(전송 계층 보안)를 지원하는 PSTN 게이트웨이를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="9a70a-116">PSTN 게이트웨이의 속성을 수정하려면 <STRONG>Set-CsPstnGateway</STRONG> cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70a-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="9a70a-117">자세한 내용은 Lync Server 관리 셸 도움말에서 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">설정-CsPstnGateway</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a70a-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="9a70a-118">분기 사이트 복구의 **다음 단계** : [Lync Server 2013에서 분기 사이트 복구를 위한 사용자 구성](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="9a70a-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a70a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a70a-119">See Also</span></span>


[<span data-ttu-id="9a70a-120">Lync Server 2013의 PSTN 게이트웨이 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="9a70a-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

