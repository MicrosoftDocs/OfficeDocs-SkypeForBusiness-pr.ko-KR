---
title: 'Lync Server 2013: SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="99c18-102">Lync Server 2013에서 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 정의</span><span class="sxs-lookup"><span data-stu-id="99c18-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c18-103">_**마지막으로 수정한 주제:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="99c18-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="99c18-104">Survivable Branch 기기 또는 서버를 토폴로지에 추가할 때이를 정의 하지 않은 경우 중앙 사이트에서이 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="99c18-105">Survivable Branch 기기 또는 Survivable Branch 서버를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="99c18-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="99c18-106">**시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="99c18-107">콘솔 트리에서 중앙 사이트를 확장 하 고, **분기 사이트**를 확장 한 다음 Survivable branch 기기 또는 Survivable branch 서버를 배포 하려는 지점 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="99c18-108">**Survivable Branch 기기**를 마우스 오른쪽 단추로 클릭 한 다음 **새 Survivable branch 기기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="99c18-109"><STRONG>Survivable Branch 기기</STRONG> 는 Survivable branch 서버와 Survivable branch 기기를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="99c18-110">**Survivable Branch 기기 정의** 대화 상자에서 **fqdn**을 클릭 하 고이 지점 사이트에서 배포할 Survivable branch 기기의 fqdn (정규화 된 도메인 이름) 또는 Survivable Branch 서버를 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="99c18-111">Survivable Branch 기기를 정의 하는 경우 <STRONG>FQDN</STRONG> 에 입력 하는 이름은 <STRONG>servicePrincipalName</STRONG> 특성에 할당 한 Survivable Branch 기기 FQDN과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="99c18-112">자세한 내용은 <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Lync Server 2013에서 Active Directory에 Survivable Branch 기기 추가</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99c18-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="99c18-113">**프런트 엔드 풀**을 클릭 하 고이 Survivable branch 기기 또는 Survivable branch 서버에서 연결할 중앙 사이트의 프런트 엔드 서버 (사용자 서비스 풀)를 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="99c18-114">**Edge server**를 클릭 하 고,이 Survivable branch 기기 또는 Survivable branch 서버에서 연결 하는 edge 풀을 클릭 하 여 지점 사이트의 원격 사용자에 게 PSTN 연결을 제공 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="99c18-115">**게이트웨이 FQDN 또는 IP 주소**를 클릭 한 다음 인바운드 또는 아웃 바운드 PSTN 호출 라우팅에 Survivable branch 기기 또는 Survivable Branch 서버가 연결 된 게이트웨이 피어의 FQDN 또는 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="99c18-116">Survivable Branch 기기를 정의 하는 경우, Survivable Branch 기기 내의 중재 서버가 PSTN 연결을 위해 연결 하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="99c18-117">**IP/PSTN 게이트웨이의 수신 대기 포트**를 클릭 한 다음 기본 포트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="99c18-118">**Sip 전송 프로토콜**에서 Survivable branch 기기 또는 Survivable branch 서버에서 사용할 전송 프로토콜을 클릭 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99c18-119">보안상의 이유로 TLS (전송 계층 보안)를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="99c18-120">Survivable Branch 기기를 정의 하는 경우에는 Survivable Branch 기기 공급 업체 문서를 참조 하 여 Survivable Branch 기기가 TLS 프로토콜을 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="99c18-121">콘솔 트리에서 새 Survivable Branch 기기 또는 서버를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c18-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="99c18-122">**다음 단계**: [Lync server 2013-branch 사이트 작업을 사용 하 여 Survivable Branch 기기 또는 서버 배포](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="99c18-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

