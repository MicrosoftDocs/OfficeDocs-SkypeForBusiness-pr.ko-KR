---
title: 'Lync Server 2013: 모니터링 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 346d4bf6840c8ce5d13b5c7843f438723fa97118
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="5238c-102">Lync Server 2013에서 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="5238c-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5238c-103">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="5238c-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="5238c-104">통합 데이터 수집 에이전트는 각 프런트 엔드 서버에서 자동으로 설치 되 고 활성화 되지만 Microsoft Lync Server 2013을 설치 하는 동안 모니터링 데이터를 자동으로 수집 하는 것을 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5238c-105">대신 프런트 엔드 서버/프런트 엔드 풀을 모니터링 데이터베이스와 연결 해야 하 고, 전역 범위 및/또는 사이트 범위에서 CDR (통화 정보 기록) 및/또는 QoE (경력 품질) 모니터링을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="5238c-106">프런트 엔드 서버 또는 프런트 엔드 풀을 모니터링 데이터베이스에 연결 하는 방법에 대 한 단계별 지침은 배포 가이드의 [Lync Server 2013에서 모니터링 저장소를 프런트 엔드 풀과 연결](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) 하는 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5238c-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="5238c-107">이러한 연결이 만들어진 후 새 Lync Server 토폴로지가 게시 된 후에도 모니터링 데이터는 수집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="5238c-108">Lync Server 2013을 설치 하면 기본적으로 CDR 및 QoE 데이터 수집이 모두 사용 하지 않도록 설정 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="5238c-109">데이터 수집을 시작 하려면 CDR 및/또는 QoE 모니터링을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="5238c-110">(CDR 및 QoE 모니터링을 모두 사용 하도록 설정할 필요는 없지만 원하는 경우에는 한 가지 유형의 모니터링을 사용 하도록 설정 하 고 다른 형식은 사용 하지 않도록 설정할 수 있습니다.) 전역 범위에서 CDR 모니터링을 사용 하도록 설정 하려면 Lync Server 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="5238c-111">또는 Lync Server 2013 제어판에서 CDR 모니터링을 사용 하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="5238c-112">Lync Server 제어판에서 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="5238c-113">**모니터링**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="5238c-114">**통화 정보 기록** 탭에서 **전역** 설정을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="5238c-115">**CDR (통화 정보 기록) 설정 편집** 창에서 **cdrs의 모니터링 사용** 을 선택 하 고 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="5238c-116">전역 범위에서 QoE 모니터링을 사용 하도록 설정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="5238c-117">원하는 경우 Lync Server 제어판 내에서 QoE 모니터링을 사용 하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="5238c-118">제어판에서 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="5238c-119">**모니터링**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="5238c-120">**경력 수준 데이터** 탭에서 **전역** 설정을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="5238c-121">**QoE (환경 품질) 설정 편집** 창에서 **QoE 데이터 모니터링 사용** 을 선택 하 고 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="5238c-122">앞서 설명한 것 처럼 위의 예에서는 전역 범위에서 모니터링을 사용 하도록 설정 합니다. 즉, 조직 전체에서 CDR 및 QoE 모니터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="5238c-123">또는 사이트 범위에서 별도의 CDR 및 QoE 구성 설정을 만든 다음 각 사이트에 대해 모니터링을 선택적으로 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238c-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="5238c-124">예를 들어 Redmond 사이트에 대해 CDR 모니터링을 사용 하도록 설정할 수는 있지만,이 경우에는 더블린 사이트에서 CDR 모니터링을 사용 하지 않도록 설정 해야</span><span class="sxs-lookup"><span data-stu-id="5238c-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="5238c-125">모니터링 구성 설정을 관리 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 통화 정보 기록 및 경험 수준 설정 구성](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5238c-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

