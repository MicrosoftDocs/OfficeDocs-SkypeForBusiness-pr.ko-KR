---
title: 'Lync Server 2013: 중재 서버에 IP 주소 유형 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="cf2b1-102">Lync Server 2013의 중재 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="cf2b1-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf2b1-103">_**마지막으로 수정한 주제:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="cf2b1-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="cf2b1-104">토폴로지 작성기를 사용 하 여 다음 절차의 단계를 수행 하 여 중재 서버에 IP 주소 유형을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="cf2b1-105">중재 서버에서 IP 주소 유형을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="cf2b1-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="cf2b1-106">토폴로지 작성기의 **중재 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="cf2b1-107">또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="cf2b1-108">**속성 편집** 대화 상자에서 구성 하려는 IP 주소 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-108">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="cf2b1-109">이중 스택 구성은 **IPv4 사용** 을 선택 하 고 다음 그림과 같이 **IPv6을 사용 하도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-109">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="cf2b1-110">**중재 서버 풀에 대 한 속성 편집 대화 상자**</span><span class="sxs-lookup"><span data-stu-id="cf2b1-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="cf2b1-111">![Lync Server 일반 속성 페이지(FQDN 포함)](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server 일반 속성 페이지(FQDN 포함)")</span><span class="sxs-lookup"><span data-stu-id="cf2b1-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="cf2b1-112">**구성 된 모든 IP 주소를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-112">**Use all configured IP addresses**.</span></span> <span data-ttu-id="cf2b1-113">컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있도록 허용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-113">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf2b1-114">이 옵션은 IP 버전 6 (IPv6) 구성에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf2b1-115">**선택한 IP 주소로 서비스 사용량을 제한**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-115">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="cf2b1-116">새 서버에서 사용할 특정 주소를 지정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-116">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="cf2b1-117">이 옵션을 선택 하는 경우 기본 IP 주소에 대 한 값을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-117">If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="cf2b1-118">**주 IP 주소**</span><span class="sxs-lookup"><span data-stu-id="cf2b1-118">**Primary IP address**.</span></span> <span data-ttu-id="cf2b1-119">서버가 PSTN (공공 교환 전화 네트워크)을 제외한 모든 통신에 사용할 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-119">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="cf2b1-120">입력 하는 IP 주소는 선택 주소 유형의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-120">The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="cf2b1-121">**PSTN IP 주소**.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-121">**PSTN IP address**.</span></span> <span data-ttu-id="cf2b1-122">중재 서버가 독립 실행형 이면 PSTN IP 주소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="cf2b1-123">이 주소는 선택한 주소 유형의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf2b1-124">Lync Server 2013의 PSTN IP 주소 구성을 지원 하기 위해 추가 NIC (네트워크 인터페이스 카드)를 설치 하는 것은 collocated 중재 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="cf2b1-125">Lync Server 2013의 지원 되는 NIC 구성에 대 한 자세한 내용은 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 용 서버 하드웨어 플랫폼</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

