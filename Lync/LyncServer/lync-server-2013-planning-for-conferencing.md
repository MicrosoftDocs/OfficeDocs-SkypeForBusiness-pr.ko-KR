---
title: 'Lync Server 2013: 회의 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1197dd61ea6ed871b851061d86c8653de32ddc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="a2fa6-102">Lync Server 2013의 회의 계획</span><span class="sxs-lookup"><span data-stu-id="a2fa6-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2fa6-103">_**마지막으로 수정 된 항목:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="a2fa6-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="a2fa6-104">Lync Server 2013에서는 다음과 같은 다양 한 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="a2fa6-105">웹 회의: 문서 공동 작업, 응용 프로그램 공유 및 데스크톱 공유가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="a2fa6-106">Lync Server 2013에서는 Office Web Apps와 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션의 공유 및 렌더링을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="a2fa6-107">Office Web Apps 서버를 설치 및 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="a2fa6-108">A/V(오디오/비디오) 회의: Microsoft Live Meeting 서비스나 타사 오디오 브리지 등의 외부 서비스 없이 실시간 오디오 또는 비디오 회의를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="a2fa6-109">전화 접속 회의-사용자가 타사 오디오 회의 공급자 없이도 PSTN (공중 전화망) 전화를 사용 하 여 Lync Server 2013 회의의 오디오 부분에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="a2fa6-110">IM(인스턴트 메시징) 회의: 단일 IM 세션에서 두 명 이상의 사람이 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="a2fa6-111">IM 회의에 대 한 자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 계획](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="a2fa6-112">Lync Server 2013에서는 예약 된 회의와 즉석 회의를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="a2fa6-113">Lync Server 2013, 프런트 엔드 서버를 배포할 때는 웹 회의, A/V 회의 및 전화 접속 회의 기능도 함께 배포할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="a2fa6-114">IM 회의 기능은 Lync Server 2013 프런트 엔드 서버에서 항상 IM 대화 기능과 함께 자동으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2fa6-115">Office Communicator 2007 R2 클라이언트 (Microsoft Office Outlook의 Live Meeting console 또는 회의 추가 기능 포함)를 사용 하 여 구성 된 모임이 배포에 포함 되는 경우에는 Lync로 마이그레이션한 후 모임에 다음과 같은 제한이 적용 됩니다. 서버 2013:</span><span class="sxs-lookup"><span data-stu-id="a2fa6-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a2fa6-116">모임 사용자는 문서 공동 작업, 응용 프로그램 공유 및 데스크톱 공유를 비롯 한 데이터 공동 작업 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="a2fa6-117">Office Communicator 2007 R2 클라이언트는 Lync Server 2013에서 지원 되지 않으므로 안정성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="a2fa6-118">이러한 문제가 발생 하지 않도록 하려면 Office Communicator 2007 R2 클라이언트를 사용 하 여 구성 된 모든 모임 일정을 Outlook 2010 또는 2013 Lync 용 온라인 모임 추가 기능에 대 한 lync 2010 또는 Outlook 2013을 사용 하 여 오프 라인으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="a2fa6-119">다음 섹션에서는 계획 프로세스, 구성 요소, 하드웨어와 소프트웨어 요구 사항 및 배포 프로세스를 비롯한 다양한 회의 기능 유형을 배포하는 데 필요한 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fa6-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2fa6-120">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a2fa6-120">In This Section</span></span>

  - [<span data-ttu-id="a2fa6-121">Lync Server 2013의 회의 개요</span><span class="sxs-lookup"><span data-stu-id="a2fa6-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="a2fa6-122">Lync Server 2013의 회의에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="a2fa6-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="a2fa6-123">Lync Server 2013의 회의에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="a2fa6-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="a2fa6-124">Lync Server 2013의 회의에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2fa6-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="a2fa6-125">Lync Server 2013의 회의에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="a2fa6-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="a2fa6-126">Lync Server 2013의 대규모 모임 지원</span><span class="sxs-lookup"><span data-stu-id="a2fa6-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

