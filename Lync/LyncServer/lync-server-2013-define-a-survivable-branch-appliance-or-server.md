---
title: 'Lync Server 2013: Sba (survivable Branch 기기 또는 서버 정의'
description: 'Lync Server 2013: Sba (survivable Branch 기기 또는 서버를 정의 합니다.'
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
ms.openlocfilehash: 946aec82f33dffe268fefb3548b8db2f5c19e1a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567764"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="0d042-103">Lync Server 2013에서 Sba (survivable Branch 기기 또는 서버 정의</span><span class="sxs-lookup"><span data-stu-id="0d042-103">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d042-104">_**마지막으로 수정 된 항목:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="0d042-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="0d042-105">SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버를 토폴로지에 추가할 때 정의하지 않은 경우 중앙 사이트에서 이 절차를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-105">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="0d042-106">Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="0d042-106">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="0d042-107">**시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0d042-108">콘솔 트리에서 중앙 사이트를 확장 하 고 **분기 사이트**를 확장 한 다음 Sba (survivable branch 기기 또는 Sba (survivable 분기 서버를 배포 하려는 분기 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-108">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="0d042-109">**Sba (survivable branch**기기를 마우스 오른쪽 단추로 클릭 한 다음 **새 sba (survivable 브랜치 기기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-109">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0d042-110"><STRONG>Sba (survivable 분기 어플라이언스</STRONG> 는 Sba (survivable 분기 서버 및 Sba (survivable 분기 기기를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-110"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="0d042-111">**Sba (survivable Branch 어플라이언스 정의** 대화 상자에서 **FQDN**을 클릭 하 고이 분기 사이트에 배포할 Sba (survivable Branch 기기 또는 sba (survivable 분기 서버의 fqdn (정규화 된 도메인 이름)을 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-111">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0d042-112">Sba (survivable 분기 기기를 정의 하는 경우 <STRONG>FQDN</STRONG> 에 입력 하는 이름은 <STRONG>servicePrincipalName</STRONG> 특성에 할당 한 sba (survivable Branch 기기 FQDN과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-112">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="0d042-113">자세한 내용은 <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Sba (survivable Branch 어플라이언스 To Active Directory to a Lync Server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d042-113">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="0d042-114">**프런트 엔드 풀**을 클릭 하 고이 Sba (survivable branch 기기 또는 Sba (survivable 분기 서버가 연결 되는 중앙 사이트에서 프런트 엔드 서버 (사용자 서비스 풀)를 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-114">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="0d042-115">에 **지 서버**를 클릭 하 고 분기 사이트의 원격 사용자에 게 PSTN 연결을 제공 하기 위해이 Sba (survivable branch 기기 또는 Sba (survivable 분기 서버가 연결 되는에 지 풀을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-115">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="0d042-116">**게이트웨이 FQDN 또는 IP 주소**를 클릭 한 다음 인바운드 또는 아웃 바운드 PSTN 통화를 라우팅하기 위해 Sba (survivable branch 기기 또는 Sba (survivable 분기 서버가 연결 된 게이트웨이 피어의 FQDN 또는 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-116">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0d042-117">SBA(Survivable Branch Appliance)를 정의하는 경우 이는 SBA(Survivable Branch Appliance) 내의 중재 서버에서 PSTN 연결을 위해 연결하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-117">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="0d042-118">**IP/PSTN 게이트웨이의 수신 대기 포트**를 클릭하고 기본 포트를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-118">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="0d042-119">**Sip 전송 프로토콜**에서 Sba (survivable branch 기기 또는 Sba (survivable 분기 서버가 사용 하는 전송 프로토콜을 클릭 한 후 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-119">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d042-120">보안상의 이유로, TLS(전송 계층 보안)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-120">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="0d042-121">SBA(Survivable Branch Appliance)를 정의하는 경우 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하여 SBA(Survivable Branch Appliance)에서 TLS 프로토콜을 지원하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d042-121">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="0d042-122">콘솔 트리에서 새 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버를 마우스 오른쪽 단추로 클릭하고 **토폴로지**를 클릭한 후에 **게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0d042-122">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="0d042-123">**다음 단계**: [Lync server 2013를 사용 하 여 sba (survivable Branch 기기 또는 서버 배포-분기 사이트 작업](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="0d042-123">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

