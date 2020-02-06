---
title: 비즈니스용 Skype 서버 제어판에 대한 첫 번째 실행 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버의 관리 및 관리를 위한 웹 기반 사용자 인터페이스인 비즈니스용 Skype 서버 제어판에 오신 것을 환영 합니다. 제어판을 사용하면 이전 릴리스의 Microsoft Management Console을 사용하여 수행했던 다양한 유형의 관리 작업을 수행할 수 있습니다.
ms.openlocfilehash: 0efd6b5730154e0f1847de6f4caf87867f977817
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797639"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="1bc48-104">비즈니스용 Skype 서버 제어판에 대한 첫 번째 실행 검사 목록</span><span class="sxs-lookup"><span data-stu-id="1bc48-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="1bc48-105">비즈니스용 Skype 서버의 관리 및 관리를 위한 웹 기반 사용자 인터페이스인 비즈니스용 Skype 서버 제어판에 오신 것을 환영 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="1bc48-106">제어판을 사용하면 이전 릴리스의 Microsoft Management Console을 사용하여 수행했던 다양한 유형의 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="1bc48-107">비즈니스용 Skype 서버를 구축한 후에는 몇 가지 중요 한 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="1bc48-108">이러한 작업 중 일부는 배포하는 동안 이미 수행했을 수 있는 초기 구성 단계이고, 나머지 다른 작업은 배포 또는 기본 설정에서 구성한 설정을 구체화하거나 수정하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="1bc48-109">이 항목에 설명되어 있는 다른 작업에서는 배포 프로세스에서 수행한 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="1bc48-110">다음 표에 나와 있는 작업을 수행하기 전에 [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) 항목의 "역할 및 범위" 섹션에 설명된 대로 올바른 사용자 권한 및 역할을 사용하여 로그온했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="1bc48-111">첫 번째 실행 검사 목록</span><span class="sxs-lookup"><span data-stu-id="1bc48-111">First Run Checklist</span></span>

<span data-ttu-id="1bc48-112">이 항목에서 참조 하는 작업을 검토 한 다음 조직의 배포에 적합 한 절차를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for deployment in your organization.</span></span>

|<span data-ttu-id="1bc48-113">**작업**</span><span class="sxs-lookup"><span data-stu-id="1bc48-113">**Task**</span></span>|<span data-ttu-id="1bc48-114">**제어판 그룹**</span><span class="sxs-lookup"><span data-stu-id="1bc48-114">**Control Panel group**</span></span>|<span data-ttu-id="1bc48-115">**설명서**</span><span class="sxs-lookup"><span data-stu-id="1bc48-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1bc48-116">토폴로지에 설치된 서비스가 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="1bc48-117">**토폴로지**</span><span class="sxs-lookup"><span data-stu-id="1bc48-117">**Topology**</span></span> <br/> |[<span data-ttu-id="1bc48-118">View Details About a Service</span><span class="sxs-lookup"><span data-stu-id="1bc48-118">View Details About a Service</span></span>](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|<span data-ttu-id="1bc48-119">비즈니스용 Skype 서버에서 사용자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="1bc48-120">필요에 따라 이전 릴리스에서 마이그레이션하는 경우 비즈니스용 Skype 서버로 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="1bc48-121">**사용자**</span><span class="sxs-lookup"><span data-stu-id="1bc48-121">**Users**</span></span> <br/> |[<span data-ttu-id="1bc48-122">Managing Users</span><span class="sxs-lookup"><span data-stu-id="1bc48-122">Managing Users</span></span>](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|<span data-ttu-id="1bc48-123">Enterprise Voice를 배포했거나 배포하려는 경우 SIP 트렁크 연결을 구성하여 공중 전화망(PSTN)에 대한 연결을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="1bc48-124">**음성 라우팅**</span><span class="sxs-lookup"><span data-stu-id="1bc48-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="1bc48-125">Configuring Trunks and Translation Rules</span><span class="sxs-lookup"><span data-stu-id="1bc48-125">Configuring Trunks and Translation Rules</span></span>](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|<span data-ttu-id="1bc48-126">Enterprise Voice를 배포한 경우 Enterprise Voice 라우팅 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="1bc48-127">**음성 라우팅**</span><span class="sxs-lookup"><span data-stu-id="1bc48-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="1bc48-128">Test Voice Routing</span><span class="sxs-lookup"><span data-stu-id="1bc48-128">Test Voice Routing</span></span>](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|<span data-ttu-id="1bc48-129">보관 서버를 배포한 경우 보관 정책 및 설정이 조직의 준수 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="1bc48-130">**모니터링 및 보관**</span><span class="sxs-lookup"><span data-stu-id="1bc48-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="1bc48-131">Managing Archiving</span><span class="sxs-lookup"><span data-stu-id="1bc48-131">Managing Archiving</span></span>](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|<span data-ttu-id="1bc48-132">모니터링 서버를 배포한 경우 모니터링 서버 보고서에서 사용 및 진단 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc48-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="1bc48-133">**홈**</span><span class="sxs-lookup"><span data-stu-id="1bc48-133">**Home**</span></span> <br/> |[<span data-ttu-id="1bc48-134">비즈니스용 Skype 서버에서 상태 및 모니터링 관리</span><span class="sxs-lookup"><span data-stu-id="1bc48-134">Manage health and monitoring in Skype for Business Server</span></span>](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


