---
title: 'Lync Server 2013: 웹 팜 FQDN 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517e00baef63e3597c2f5b2b6621e62efb02ca62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="1cf0b-102">Lync Server 2013에 대한 웹 팜 FQDN 구성</span><span class="sxs-lookup"><span data-stu-id="1cf0b-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cf0b-103">_**마지막으로 수정한 주제:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="1cf0b-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="1cf0b-104">토폴로지 작성기에서 Standard Edition server, 프론트 엔드 풀, 디렉터 또는 디렉터 풀의 구성을 정의한 경우 외부 웹 서비스의 FQDN (정규화 된 도메인 이름)을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1cf0b-105">Standard Edition server 또는 프런트 엔드 풀에 속한 클라이언트의 로그온 프로세스 중에는 대역 내 프로비저닝 방식으로 구성 된 웹 서비스 Fqdn이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="1cf0b-106">외부 웹 서비스 URL을 추가 하거나 변경 해야 하는 경우 토폴로지 작성기를 사용 하 여이 항목의 절차를 사용 하 여 웹 서비스 구성을 구성 하거나 다시 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="1cf0b-107">웹 서비스에 대 한 외부 풀 FQDN을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="1cf0b-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="1cf0b-108">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1cf0b-109">토폴로지 작성기의 콘솔 트리에서 **표준 버전의 프런트 엔드**, **Enterprise Edition 프론트 종료**및 **디렉터**아래에서 편집 해야 하는 풀 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1cf0b-110">**웹 서비스** 섹션에서 **외부 웹 서비스 FQDN**을 추가 하거나 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="1cf0b-111">HTTP와 HTTPS 모두에 대 한 **수신 대기 포트** 를 검토 하 고 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="1cf0b-112">기본값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="1cf0b-113">**수신 대기 포트:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="1cf0b-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="1cf0b-114">**게시 된 포트:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="1cf0b-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="1cf0b-115">**수신 대기 포트** 는 역방향 프록시에서 요청을 수신 하도록 외부 웹 서비스가 구성 되는 포트 이며, **게시 된 포트** 는 역방향 프록시를 통해 외부적으로 게시 되 고 대역내 프로비저닝 중에 클라이언트와 통신 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="1cf0b-116">추가 및 업데이트를 완료 했으면 **확인** 을 클릭 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="1cf0b-117">**Lync Server 2013**을 마우스 오른쪽 단추로 클릭 한 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1cf0b-118">게시가 성공적으로 완료 되 면 추가 단계를 수행 해야 한다는 것을 알리는 링크가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="1cf0b-119">링크를 클릭 하면 추가 되거나 제거 되거나 변경 된 구성 요소에 대 한 구성을 업데이트 하기 위해 나열 된 각 서버에서 Lync Server 배포 마법사를 다시 실행 해야 하는 토폴로지 작성기의 변경 사항에 따라 영향을 받는 서버 목록이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="1cf0b-120">조직의 각 Standard Edition server, 프론트 엔드 풀, 디렉터 또는 디렉터 풀에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf0b-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

