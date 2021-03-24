---
title: 비즈니스용 Skype 서버 제어판의 첫 번째 실행 검사 목록
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: 비즈니스용 Skype 서버 제어판은 비즈니스용 Skype 서버 관리 및 관리를 위한 웹 기반 사용자 인터페이스입니다. 제어판을 사용하여 이전 릴리스의 Microsoft Management Console을 사용하여 수행된 관리 작업 유형을 수행할 수 있습니다.
ms.openlocfilehash: 262d2d16ad4922909ba08d9628c768e1d1443d12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099774"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="95081-104">비즈니스용 Skype 서버 제어판의 첫 번째 실행 검사 목록</span><span class="sxs-lookup"><span data-stu-id="95081-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="95081-105">비즈니스용 Skype 서버 제어판은 비즈니스용 Skype 서버 관리 및 관리를 위한 웹 기반 사용자 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="95081-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="95081-106">제어판을 사용하여 이전 릴리스의 Microsoft Management Console을 사용하여 수행된 관리 작업 유형을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95081-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="95081-107">비즈니스용 Skype 서버를 배포한 후 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95081-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="95081-108">이러한 작업 중 일부는 배포 중에 이미 수행한 초기 구성 단계인 반면 다른 작업은 배포 또는 기본 설정 중에 구성한 설정의 구체화 또는 수정입니다.</span><span class="sxs-lookup"><span data-stu-id="95081-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="95081-109">이 항목에서 설명하는 다른 작업은 배포 프로세스 중에 수행한 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95081-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="95081-110">다음 표의 작업을 수행하기 전에 역할 기반 액세스 제어 항목의 "역할 및 범위" 섹션에 설명된 올바른 사용자 권한, 사용 권한 및 역할을 사용하여 [로그온해야](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) 합니다.</span><span class="sxs-lookup"><span data-stu-id="95081-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="95081-111">첫 실행 검사 목록</span><span class="sxs-lookup"><span data-stu-id="95081-111">First Run Checklist</span></span>

<span data-ttu-id="95081-112">이 항목에서 설명하는 작업을 검토한 다음 조직에서 Lync Server 배포에 적합한 절차를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95081-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for the Lync Server deployment in your organization.</span></span>

|<span data-ttu-id="95081-113">**작업**</span><span class="sxs-lookup"><span data-stu-id="95081-113">**Task**</span></span>|<span data-ttu-id="95081-114">**제어판 그룹**</span><span class="sxs-lookup"><span data-stu-id="95081-114">**Control Panel group**</span></span>|<span data-ttu-id="95081-115">**설명서**</span><span class="sxs-lookup"><span data-stu-id="95081-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95081-116">토폴로지에서 설치한 서비스가 예상대로 실행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95081-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="95081-117">**토폴로지**</span><span class="sxs-lookup"><span data-stu-id="95081-117">**Topology**</span></span> <br/> |[<span data-ttu-id="95081-118">서비스에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="95081-118">View Details About a Service</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|<span data-ttu-id="95081-119">사용자가 비즈니스용 Skype 서버에 대해 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="95081-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="95081-120">선택적으로 이전 릴리스에서 마이그레이션하는 경우 사용자를 비즈니스용 Skype 서버로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="95081-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="95081-121">**사용자**</span><span class="sxs-lookup"><span data-stu-id="95081-121">**Users**</span></span> <br/> |[<span data-ttu-id="95081-122">사용자 관리</span><span class="sxs-lookup"><span data-stu-id="95081-122">Managing Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|<span data-ttu-id="95081-123">배포하거나 배포하려는 Enterprise Voice PSTN(전화망)에 대한 연결을 사용하도록 SIP 트렁크 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="95081-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="95081-124">**음성 라우팅**</span><span class="sxs-lookup"><span data-stu-id="95081-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="95081-125">트렁크 및 변환 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="95081-125">Configuring Trunks and Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|<span data-ttu-id="95081-126">배포한 Enterprise Voice 라우팅 Enterprise Voice 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95081-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="95081-127">**음성 라우팅**</span><span class="sxs-lookup"><span data-stu-id="95081-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="95081-128">음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="95081-128">Test Voice Routing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|<span data-ttu-id="95081-129">보관 서버를 배포한 경우 보관 정책 및 설정이 조직의 규정 준수 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95081-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="95081-130">**모니터링 및 보관**</span><span class="sxs-lookup"><span data-stu-id="95081-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="95081-131">보관 관리</span><span class="sxs-lookup"><span data-stu-id="95081-131">Managing Archiving</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|<span data-ttu-id="95081-132">모니터링 서버를 배포한 경우 모니터링 서버 보고서를 보고 사용 현황 및 진단 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95081-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="95081-133">**홈**</span><span class="sxs-lookup"><span data-stu-id="95081-133">**Home**</span></span> <br/> |[<span data-ttu-id="95081-134">비즈니스용 Skype 서버 2015에서 상태 및 모니터링 관리</span><span class="sxs-lookup"><span data-stu-id="95081-134">Manage health and monitoring in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |