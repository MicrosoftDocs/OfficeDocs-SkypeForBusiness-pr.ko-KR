---
title: 원격 통화 제어 사용
description: 원격 통화 제어를 사용 하도록 설정 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8009ffc927ad3f7a4f83ad3505100f3a9d4e82d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551134"
---
# <a name="enable-remote-call-control"></a><span data-ttu-id="9628a-103">원격 통화 제어 사용</span><span class="sxs-lookup"><span data-stu-id="9628a-103">Enable remote call control</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9628a-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9628a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9628a-105">원격 통화 제어는 Lync Server 2013을 사용 하 여 사용자가 데스크톱 PBX (private branch exchange) 전화를 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-105">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="9628a-106">레거시 환경에서 원격 통화 제어를 배포 했으며이를 Lync Server 2013로 마이그레이션하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-106">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="9628a-107">SIP/CSTA 게이트웨이를 설치하고 PBX와 통신하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-107">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="9628a-108">Lync Server 2013 파일럿 풀을 배포 하는 경우이 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-108">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="9628a-109">토폴로지를 병합 하 고 정책 및 설정을 마이그레이션한 후에는 CSTA 요청을 SIP/CSTA 게이트웨이로 라우팅하도록 Lync Server 2013을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-109">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="9628a-110">이 단계는 자동화된 마이그레이션 이후에 수행되는 수동 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-110">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="9628a-111">CSTA 요청의 라우팅을 구성하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-111">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="9628a-112">이전에 권한이 부여 된 호스트 항목 제거 (Lync Server 2013에서 *신뢰할 수 있는 서버 항목* 으로 알려진)</span><span class="sxs-lookup"><span data-stu-id="9628a-112">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="9628a-113">레거시 배포에서 사용자를 마이그레이션하는 경우에는 Lync Server 2013 파일럿 풀에서 새 신뢰할 수 있는 응용 프로그램 항목을 구성 하기 전에 SIP/CSTA 게이트웨이에 대해 만든 기존의 모든 권한이 부여 된 호스트 항목을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-113">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="9628a-114">권한 있는 레거시 호스트 항목을 제거 하는 방법에 대 한 자세한 내용은 [권한이 부여 된 호스트 항목 제거](remove-an-authorized-host-entry.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9628a-114">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="9628a-115">원격 통화 제어에 대 한 고정 경로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-115">Configure a static route for remote call control.</span></span> <span data-ttu-id="9628a-116">원격 통화 제어를 지원할 개별 풀에 대해 고정 경로를 구성할 수도 있고, 풀 수준 고정 경로를 사용 하 여 구성 되지 않은 각 풀이 전역 고정 경로를 사용 하도록 전역 고정 경로를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-116">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="9628a-117">고정 경로를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성을](lync-server-2013-configure-a-static-route-for-remote-call-control.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9628a-117">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="9628a-118">원격 통화 제어를 지원하려는 각 풀에서 원격 통화 제어를 위한 트러스트된 응용 프로그램 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-118">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="9628a-119">신뢰할 수 있는 응용 프로그램 항목을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성을](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9628a-119">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="9628a-120">TCP (전송 제어 프로토콜)를 사용 하 여 Lync Server 2013에 연결 하는 SIP/CSTA 게이트웨이를 배포한 경우에는 토폴로지 작성기에서 게이트웨이의 IP 주소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-120">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="9628a-121">IP 주소를 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 " [Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) "를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9628a-121">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="9628a-122">원격 통화 제어를 사용 하도록 설정 하 고 회선 서버 URI (Uniform Resource Identifier) 및 줄 URI를 할당 하 여 Lync 2013 사용자를 원격 통화 제어로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-122">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="9628a-123">레거시 배포에서 Lync Server 2013으로 사용자를 마이그레이션하는 경우 원격 통화 제어 설정이 다른 사용자 설정과 함께 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-123">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="9628a-124">레거시 배포에서 주소록 전화 번호 정규화 규칙을 사용자 지정한 경우 정책 및 설정에 대한 자동화된 마이그레이션이 완료된 후 몇 가지 수동 작업을 수행하여 사용자 지정된 정규화 규칙을 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-124">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="9628a-125">정규화 규칙을 사용자 지정하지 않은 경우 주소록은 남은 토폴로지와 함께 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="9628a-125">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="9628a-126">사용자 지정된 정규화된 규칙을 수동으로 마이그레이션하는 방법에 대한 자세한 내용은 [Migrate Address Book](migrate-address-book.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9628a-126">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

