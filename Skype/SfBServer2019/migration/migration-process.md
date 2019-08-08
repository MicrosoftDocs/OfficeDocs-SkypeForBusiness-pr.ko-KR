---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019에 대해 권장 되거나 지원 되는 마이그레이션 절차는 나란히 마이그레이션입니다. 이 항목에서는 나란히 마이그레이션을 사용 해야 하는 이유와 공존 테스트에 대 한 정보를 포함 합니다.
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238085"
---
# <a name="migration-process"></a><span data-ttu-id="3a5a9-104">마이그레이션 프로세스</span><span class="sxs-lookup"><span data-stu-id="3a5a9-104">Migration process</span></span>

<span data-ttu-id="3a5a9-105">비즈니스용 Skype 서버 2019에 대해 권장 되거나 지원 되는 마이그레이션 절차는 나란히 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="3a5a9-106">이 항목에서는 나란히 마이그레이션을 사용 해야 하는 이유와 공존 테스트에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="3a5a9-107">나란히 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3a5a9-107">Side-By-Side Migration</span></span>

<span data-ttu-id="3a5a9-108">거의 모든 마이그레이션에는 side-by-side 마이그레이션 경로를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="3a5a9-109">나란히 마이그레이션하는 경우 이전 버전을 실행 하는 해당 서버와 함께 비즈니스용 Skype 서버 2019와 새 서버를 배포한 다음 새 서버로 작업을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="3a5a9-110">이전 버전으로 롤백하는 데 필요한 경우 원래 서버로만 작업을 다시 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="3a5a9-111">이 상황에서는 업그레이드 된 클라이언트를 사용 하 여 예약 된 새 모임이 작동 하지 않으며 클라이언트도 다운 그레이드 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="3a5a9-112">공존 테스트</span><span class="sxs-lookup"><span data-stu-id="3a5a9-112">Coexistence Testing</span></span>

<span data-ttu-id="3a5a9-113">이전 버전과 병행 하 여 비즈니스용 Skype 서버 2019을 배포한 후에는 배포는 비즈니스용 Skype Server 2019 및 이전 버전의 공존 테스트 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="3a5a9-114">이 상태에서는 서비스를 시작 하 고 각 사이트를 관리할 수 있으며 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지를 테스트 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="3a5a9-115">모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해 하 고 각 배포가 제대로 작동 하 고 작동 하는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="3a5a9-116">일반적으로 공존 테스트 단계는 비즈니스용 Skype 서버 2019의 파일럿 테스트 전반에 걸쳐 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="3a5a9-117">레거시 사용자는 일정 기간 동안 비즈니스용 Skype 서버 2019으로 이동 하 여 응용 프로그램 호환성과 기능 및 기능이 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="3a5a9-118">파일럿 테스트 후에는 사용자 및 응용 프로그램이 비즈니스용 Skype Server 2019의 프로덕션 버전으로 이동 하 고 이전 버전의 레거시 풀 및 응용 프로그램은 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a5a9-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
