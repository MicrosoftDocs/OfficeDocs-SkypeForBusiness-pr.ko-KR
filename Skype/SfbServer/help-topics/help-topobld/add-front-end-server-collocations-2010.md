---
title: 프런트 엔드 서버 배치 2010 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 배포의 경우 프런트 엔드 풀에 A/V 회의 서비스, 중재 서버 또는 이 두 가지를 모두 배치하거나 각각을 독립 실행형 서버로 배포할 수 있습니다. Standard Edition Server 배포의 경우 회의가 사용하도록 설정되어 있으면 A/V 회의 서비스가 항상 배치됩니다.
ms.openlocfilehash: 86bef8bdcbdd36033e64912bdce2d9ea3469e45c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216519"
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="0a616-104">프런트 엔드 서버 배치 2010 추가</span><span class="sxs-lookup"><span data-stu-id="0a616-104">Add Front End Server Collocations 2010</span></span>

<span data-ttu-id="0a616-p102">Enterprise Edition 배포의 경우 프런트 엔드 풀에 A/V 회의 서비스, 중재 서버 또는 이 두 가지를 모두 배치하거나 각각을 독립 실행형 서버로 배포할 수 있습니다. Standard Edition Server 배포의 경우 회의가 사용하도록 설정되어 있으면 A/V 회의 서비스가 항상 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-p102">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers. For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="0a616-p103">**기능 선택** 페이지에서 **회의**가 선택되어 있으면 A/V 회의 서비스는 필수입니다. Enterprise Edition 프런트 엔드 풀은 배치된 A/V 회의 서비스 또는 독립 실행형 A/V 회의 풀을 사용할 수 있습니다. 회의가 선택되어 있지 않으면 A/V 회의 서비스 배치를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-p103">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page. An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool. If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="0a616-110">Standard Edition 프런트 엔드 서버 또는 Enterprise Edition 프런트 엔드 풀에 중재 서버 역할을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="0a616-111">미디어 바이패스 및 DNS (Domain Name System) 부하 분산을 지 원하는 정규 PSTN (공중 전화망) 게이트웨이에 직접 SIP 연결을 배포 하는 경우 독립 실행형 중재 서버 풀을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="0a616-112">정규 게이트웨이는 중재 서버 풀에 대 한 DNS 부하 분산을 가능 하 게 하 고 풀의 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="0a616-113">또한 다음 조건 중 하나라도 충족 되 면 IP-Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 세션 경계 컨트롤러 (SBC)에 연결 하는 경우에도 프런트 엔드 풀에 중재 서버를 함께 배치할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="0a616-114">IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="0a616-115">IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="0a616-116">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 함께 배치할 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="0a616-117">사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a616-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="0a616-118">일반적으로 조직에 고가용성 및 확장성이 있는 경우에는 A/V 회의 서버 또는 중재 서버의 배치를 사용 하지 않는 것이 좋습니다. 엔터프라이즈 버전 배포의 프런트 엔드 풀에서 이러한 서버 역할을 배치에 대 한 자세한 내용은 Deployment 설명서의 [Define And Configure A 프런트 엔드 풀](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) requirementsFor을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a616-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="0a616-119">A/V 회의 기능 및 구성 요소에 대한 자세한 내용은 계획 설명서의 [회의 계획](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a616-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0a616-120">중재 서버를 포함 하 여 Enterprise Voice 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서에서 [비즈니스용 Skype 서버 2015의 Enterprise Voice 계획](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a616-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


