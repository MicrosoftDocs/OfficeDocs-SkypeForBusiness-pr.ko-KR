---
title: 'Lync Server 2013: 프런트 엔드 서버에 IP 주소 유형 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ab774cc5b0f15ed04d3803741b6355230130fb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="0cf73-102">Lync Server 2013의 프런트 엔드 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="0cf73-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cf73-103">_**마지막으로 수정한 주제:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="0cf73-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="0cf73-104">토폴로지 작성기를 사용 하 여 프런트 엔드 서버에 IP 주소 유형을 배포 하려면 다음 절차의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="0cf73-105">프런트 엔드 서버에 IP 주소 유형을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="0cf73-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="0cf73-106">**Enterprise Edition 프런트 엔드 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-106">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="0cf73-107">또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="0cf73-108">**속성 편집** 대화 상자에서 구성 하려는 IP 주소 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-108">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="0cf73-109">이중 스택 구성은 **IPv4 사용** 을 선택 하 고 다음 그림과 같이 **IPv6을 사용 하도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-109">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0cf73-110">**프런트 엔드 서버 풀의 속성 편집 대화 상자**</span><span class="sxs-lookup"><span data-stu-id="0cf73-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="0cf73-111">![프런트 엔드 서버 속성 편집 대화 상자](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "프런트 엔드 서버 속성 편집 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="0cf73-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="0cf73-112">**구성 된 모든 IP 주소를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-112">**Use all configured IP addresses**.</span></span> <span data-ttu-id="0cf73-113">컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있도록 허용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-113">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0cf73-114">이 옵션은 IP 버전 6 (IPv6) 구성에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="0cf73-115">**선택한 IP 주소로 서비스 사용량을 제한**합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-115">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="0cf73-116">새 서버에서 사용할 특정 주소를 지정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-116">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="0cf73-117">이 옵션을 선택 하는 경우 **기본 IP 주소**에 대 한 값을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-117">If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="0cf73-118">**주 IP 주소**</span><span class="sxs-lookup"><span data-stu-id="0cf73-118">**Primary IP address**.</span></span> <span data-ttu-id="0cf73-119">서버가 PSTN (공공 교환 전화 네트워크)을 제외한 모든 통신에 사용할 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-119">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="0cf73-120">입력 하는 IP 주소는 선택 주소 유형의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-120">The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="0cf73-121">**PSTN IP 주소**.</span><span class="sxs-lookup"><span data-stu-id="0cf73-121">**PSTN IP address**.</span></span> <span data-ttu-id="0cf73-122">Lync Server 2013의 PSTN IP 주소 구성을 지원 하기 위해 추가 NIC (네트워크 인터페이스 카드)를 설치 하는 것은 collocated 중재 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf73-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="0cf73-123">Lync Server 2013의 지원 되는 NIC 구성에 대 한 자세한 내용은 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf73-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

