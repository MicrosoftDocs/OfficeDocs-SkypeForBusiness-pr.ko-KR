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
description: 비즈니스용 Skype 서버 2019에 대해 권장 되 고 지원 되는 마이그레이션 절차는 side-by-side 마이그레이션입니다. 이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유에 대해 설명하며, 동시 사용 테스트에 대한 정보도 제공합니다.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752640"
---
# <a name="migration-process"></a><span data-ttu-id="e4f0f-104">마이그레이션 프로세스</span><span class="sxs-lookup"><span data-stu-id="e4f0f-104">Migration process</span></span>

<span data-ttu-id="e4f0f-105">비즈니스용 Skype 서버 2019에 대해 권장 되 고 지원 되는 마이그레이션 절차는 side-by-side 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="e4f0f-106">이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유에 대해 설명하며, 동시 사용 테스트에 대한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="e4f0f-107">병렬 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e4f0f-107">Side-By-Side Migration</span></span>

<span data-ttu-id="e4f0f-108">거의 모든 마이그레이션에서는 병렬 마이그레이션 경로를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="e4f0f-109">병렬 마이그레이션에서는 이전 버전을 실행 하는 해당 서버와 함께 새로운 비즈니스용 Skype 서버 2019을 사용 하 여 새 서버를 배포한 다음 작업을 새 서버로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="e4f0f-110">이전 버전으로 롤백하는 데 필요한 경우 작업을 원래 서버로 다시 이동 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="e4f0f-111">이 경우 업그레이드된 클라이언트로 예약된 모든 새 모임이 작동하지 않으며 클라이언트도 다운그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="e4f0f-112">동시 사용 테스트</span><span class="sxs-lookup"><span data-stu-id="e4f0f-112">Coexistence Testing</span></span>

<span data-ttu-id="e4f0f-113">이전 버전과 동시에 비즈니스용 Skype 서버 2019을 배포한 후에는 배포에서 비즈니스용 Skype 서버 2019 및 이전 버전의 공존 성 테스트 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="e4f0f-114">이 상태에서는 테스트를 통해 서비스가 시작되었고, 각 사이트를 관리할 수 있으며, 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="e4f0f-115">모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해하고 각 배포가 올바르게 기능 및 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="e4f0f-116">일반적으로 비즈니스용 Skype 서버 2019의 파일럿 테스트 전반에 걸쳐 동시 테스트 단계가 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="e4f0f-117">레거시 사용자는 일정 기간 동안 비즈니스용 Skype 서버 2019로 이동 하 여 응용 프로그램 호환성과 기능 및 기능이 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="e4f0f-118">파일럿 테스트를 수행한 후에는 사용자와 응용 프로그램이 비즈니스용 Skype 서버 2019 프로덕션 버전으로 이동 하 고 이전 버전의 레거시 풀과 응용 프로그램은 폐기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4f0f-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
