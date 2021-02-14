---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019에 대한 권장 및 지원되는 마이그레이션 절차는 나란히 마이그레이션입니다. 이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유에 대해 설명하며, 동시 사용 테스트에 대한 정보도 제공합니다.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752640"
---
# <a name="migration-process"></a><span data-ttu-id="9a29e-104">마이그레이션 프로세스</span><span class="sxs-lookup"><span data-stu-id="9a29e-104">Migration process</span></span>

<span data-ttu-id="9a29e-105">비즈니스용 Skype 서버 2019에 대한 권장 및 지원되는 마이그레이션 절차는 나란히 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="9a29e-106">이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유에 대해 설명하며, 동시 사용 테스트에 대한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="9a29e-107">병렬 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9a29e-107">Side-By-Side Migration</span></span>

<span data-ttu-id="9a29e-108">거의 모든 마이그레이션에서는 병렬 마이그레이션 경로를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="9a29e-109">단계적 마이그레이션에서는 비즈니스용 Skype 서버 2019가 있는 새 서버를 이전 버전을 실행하는 해당 서버와 함께 배포한 다음 작업을 새 서버로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="9a29e-110">이전 버전으로 롤백해야 하는 경우 작업을 원래 서버로 다시 이동하기만하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="9a29e-111">이 경우 업그레이드된 클라이언트로 예약된 모든 새 모임이 작동하지 않으며 클라이언트도 다운그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="9a29e-112">동시 사용 테스트</span><span class="sxs-lookup"><span data-stu-id="9a29e-112">Coexistence Testing</span></span>

<span data-ttu-id="9a29e-113">이전 버전과 함께 비즈니스용 Skype 서버 2019를 배포한 후 배포는 비즈니스용 Skype 서버 2019 및 이전 버전의 동시 사용 테스트 상태를 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="9a29e-114">이 상태에서는 테스트를 통해 서비스가 시작되었고, 각 사이트를 관리할 수 있으며, 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="9a29e-115">모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해하고 각 배포가 올바르게 기능 및 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="9a29e-116">일반적으로 공존 테스트 단계는 비즈니스용 Skype 서버 2019의 파일럿 테스트 전체에 걸쳐 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="9a29e-117">레거시 사용자는 응용 프로그램 호환성 및 기능이 제대로 작동하도록 하기 위해 기간 동안 비즈니스용 Skype 서버 2019로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="9a29e-118">파일럿 테스트 후 사용자 및 응용 프로그램은 프로덕션 버전의 비즈니스용 Skype 서버 2019로 이동되고 이전 버전의 레거시 풀 및 응용 프로그램은 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29e-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
