---
title: 'Lync Server 2013: 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c7c7d6be1ee0e73ee87d71676dddfdcf7954d03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="42cde-102">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42cde-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="42cde-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="42cde-104">Lync Server 2013 통신 소프트웨어 배포에는 Active Directory 도메인 서비스 준비, 프런트 엔드 서버 및 다른 핵심 Lync Server 2013 내부 구성 요소 배포, 추가 서버 역할 및 기능 배포 등이 포함 되어 있습니다. 외부 사용자 액세스 및 Enterprise Voice 등의 조직에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42cde-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="42cde-105">이 설명서는 Lync Server 2013 배포를 위한 세 가지 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cde-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="42cde-106">Lync Server 2013, Enterprise Edition의 새로운 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="42cde-107">Lync Server 2013, Standard Edition의 새로운 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="42cde-108">기존 Lync Server 2010 Standard edition 또는 Enterprise Edition 배포에 Lync Server 2013 Standard Edition 또는 Enterprise Edition의 새로운 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="42cde-109">기존 Microsoft Office Communications Server 2007 또는 Microsoft Office Communications Server 2007 R2 환경에서 Lync Server 2013을 배포 하는 방법에 대 한 자세한 내용은 [마이그레이션](migration.md) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="42cde-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42cde-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="42cde-110">In This Section</span></span>

  - [<span data-ttu-id="42cde-111">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="42cde-112">Lync Server 2013에서 외부 사용자 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="42cde-113">Lync Server 2013에서 엔터프라이즈 음성 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="42cde-114">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="42cde-115">Lync Server 2013에서 보관 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="42cde-116">Lync Server 2013에서 전화 접속 회의 구성</span><span class="sxs-lookup"><span data-stu-id="42cde-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="42cde-117">Lync Server 2013에서 비디오 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="42cde-118">Lync Server 2013에서 분기 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="42cde-119">Lync Server 2013에서 영구 채팅 서버 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="42cde-120">Lync Server 2013에서 클라이언트 및 장치 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="42cde-121">Lync Server 2013의 통합 된 연락처 저장소 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="42cde-122">Lync Server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="42cde-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="42cde-123">Lync Server 2013의 평가판 버전에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="42cde-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="42cde-124">Lync Server 2013에서 원격 통화 제어 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="42cde-125">Lync Server 2013에서 모바일 기능 배포</span><span class="sxs-lookup"><span data-stu-id="42cde-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="42cde-126">Office Online Server 및 Lync Server 2013과 통합 구성</span><span class="sxs-lookup"><span data-stu-id="42cde-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="42cde-127">Lync Server 2013의 상태 구성</span><span class="sxs-lookup"><span data-stu-id="42cde-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

