---
title: 프론트 엔드 서버 병설 2010 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 배포의 경우 프런트 엔드 풀에서 A/V 회의 서비스, 중재 서버 또는 둘 다를 collocate 하거나 독립 실행형 서버로 배포할 수 있습니다. 표준 버전 서버 배포의 경우, 회의를 사용 하도록 설정 하면 A/V 회의 서비스는 항상 collocated.
ms.openlocfilehash: 4a488aeca543d95042f9dfeec860934f472b94c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820840"
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="c847b-104">프론트 엔드 서버 병설 2010 추가</span><span class="sxs-lookup"><span data-stu-id="c847b-104">Add Front End Server Collocations 2010</span></span>

<span data-ttu-id="c847b-105">Enterprise Edition 배포의 경우 프런트 엔드 풀에서 A/V 회의 서비스, 중재 서버 또는 둘 다를 collocate 하거나 독립 실행형 서버로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-105">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers.</span></span> <span data-ttu-id="c847b-106">표준 버전 서버 배포의 경우, 회의를 사용 하도록 설정 하면 A/V 회의 서비스는 항상 collocated.</span><span class="sxs-lookup"><span data-stu-id="c847b-106">For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="c847b-107">**기능 선택** 페이지에서 **회의** 를 선택한 경우 A/V 회의 서비스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-107">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="c847b-108">Enterprise Edition 프런트 엔드 풀은 collocated A/V 회의 서비스 또는 독립 실행형 A/V 회의 풀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-108">An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool.</span></span> <span data-ttu-id="c847b-109">회의를 선택 하지 않은 경우 Collocate A/V 회의 서비스를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-109">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="c847b-110">Standard Edition 프런트 엔드 서버 또는 Enterprise Edition 프런트 엔드 풀에서 중재 서버 역할을 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="c847b-111">직접 SIP 연결을 미디어 우회 및 DNS (Domain Name System) 부하 분산을 지 원하는 적격 PSTN (공개 교환 전화 네트워크) 게이트웨이에 배포 하는 경우 독립 실행형 중재 서버 풀이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="c847b-112">자격 있는 게이트웨이는 중재 서버 풀에 DNS 부하 분산을 사용할 수 있고 풀의 모든 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="c847b-113">또한 다음 조건 중 하나가 충족 되는 경우 IP Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 SBC (세션 경계 컨트롤러)에 연결 된 경우에는 프런트 엔드 풀에 중재 서버를 collocate 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="c847b-114">IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="c847b-115">IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="c847b-116">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 collocate 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="c847b-117">환경이 이러한 요구 사항을 충족 하지 못하는 경우에는 독립 실행형 중재 서버 풀을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c847b-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="c847b-118">일반적으로 A/V 회의 서버 또는 중재 서버의 위치를 사용 하지 않는 것이 좋습니다. 조직에서 엔터프라이즈 버전 배포의 프런트 엔드 풀에 이러한 서버 역할을 collocating 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [프런트 엔드 풀 정의 및 구성](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) requirementsFor을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c847b-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="c847b-119">A/V 회의 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서의 [회의 계획](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c847b-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="c847b-120">중재 서버를 비롯 한 Enterprise Voice 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서의 비즈니스용 [Skype Server 2015의 Enterprise Voice 계획](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c847b-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


