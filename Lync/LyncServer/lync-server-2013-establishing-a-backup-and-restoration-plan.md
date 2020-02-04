---
title: 'Lync Server 2013: 백업 및 복원 계획 수립'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cee1c4571dafa4e513f42613de13205ecec9de42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="f2d7b-102">Lync Server 2013의 백업 및 복원 계획 설정</span><span class="sxs-lookup"><span data-stu-id="f2d7b-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2d7b-103">_**마지막으로 수정한 주제:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f2d7b-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f2d7b-104">백업 및 복원 계획을 만들려면 다음과 같은 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="f2d7b-105">계획 개발.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-105">Developing the plan.</span></span>

  - <span data-ttu-id="f2d7b-106">계획 구현.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-106">Implementing the plan.</span></span>

  - <span data-ttu-id="f2d7b-107">계획을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="f2d7b-108">백업 및 복원 계획 개발</span><span class="sxs-lookup"><span data-stu-id="f2d7b-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="f2d7b-109">Lync Server에 대 한 백업 및 복원 전략을 개발한 후에는이를 사용 하 여 자세한 백업 및 복원 계획을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="f2d7b-110">데이터 및 설정 백업에 대 한 우선 순위와 요구 사항을 명확 하 게 전달 하는 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="f2d7b-111">[Lync server 2013의 백업 및 복원 전략 설정](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) 및 [lync Server 2013 용 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md) 의 워크시트에 대 한 정보를 사용 하 여 전략 설명서를 쉽게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="f2d7b-112">계획에는 서비스 복원 시기 및 방법을 결정 하는 조건도 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="f2d7b-113">계획을 개발할 때 다음을 고려 하 고 계정을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="f2d7b-114">새 하드웨어에서 서버를 복구 하는 방법</span><span class="sxs-lookup"><span data-stu-id="f2d7b-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="f2d7b-115">여러 비즈니스 영역이 나 부서의 작업을 수행 해야 하는 서비스를 복구 하는 방법</span><span class="sxs-lookup"><span data-stu-id="f2d7b-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="f2d7b-116">여분 서버를 신속 하 게 구입 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="f2d7b-117">전략을 사용 하 여 복구 하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="f2d7b-118">조직의 RTO (복구 시간 목적)에 대 한 요구 사항을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="f2d7b-119">배포의 서버와 구성 요소를 반영 하기 위해 적절 하 게 프로시저를 추가 하 고 삭제 하 여이 항목의 백업 및 복원 절차를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="f2d7b-120">또한 백업 일정과 같은 적절 한 세부 정보를 적절 한 절차에 추가 하 여 정보가 간과 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2d7b-121">프로시저의 품질과 reproducibility을 확인 하는 데 도움이 되도록 최대한 많은 단계를 위해 스크립트를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="f2d7b-122">계획에서 계획을 검토할 책임이 있는 사용자, 새 프로시저 또는 도구를 테스트 하 고 유효성을 검사 하는 사용자, 계획 및 관련 절차에 대 한 변경 내용을 승인 해야 하는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="f2d7b-123">백업 및 복원 계획이 설정 된 모든 목표 및 우선 순위를 완전히 충족 하는지 확인 하려면 계획을 구현 하기 전에 조직의 적절 한 비즈니스 의사 결정권자 및 기술 의사 결정권자에 대 한 승인을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="f2d7b-124">백업 및 복원 계획 구현</span><span class="sxs-lookup"><span data-stu-id="f2d7b-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="f2d7b-125">백업 및 복원 계획을 구현 하려면 다음 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="f2d7b-126">계획 테스트 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f2d7b-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="f2d7b-127">계획을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-127">Communicating the plan.</span></span>

  - <span data-ttu-id="f2d7b-128">백업 및 복원 작업의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="f2d7b-129">계획 테스트 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f2d7b-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="f2d7b-130">랩 환경에서 여기에 설명 된 절차를 테스트 하 고 유효성을 검사 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="f2d7b-131">이러한 절차 또는 다른 절차가 해당 환경에서 작동 하는지 확인 하려면 구현 하려는 각 프로시저를 테스트 하 고 유효성을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="f2d7b-132">최종 승인에 대 한 계획을 제출 하기 전에 테스트 및 유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="f2d7b-133">계획 통신</span><span class="sxs-lookup"><span data-stu-id="f2d7b-133">Communicating the Plan</span></span>

<span data-ttu-id="f2d7b-134">백업 및 복원 계획에서는 프로시저를 수행 하기 위한 절차와 단계별 지침을 구현 하는 사용자를 명확 하 게 설명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="f2d7b-135">백업 및 복원의 모든 측면을 담당 하는 모든 사용자가 계획, 구현 방법, 역할에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="f2d7b-136">여기에는 다음에 대 한 구현 요구 사항이 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="f2d7b-137">풀 및 서버 백업</span><span class="sxs-lookup"><span data-stu-id="f2d7b-137">Pool and server backup.</span></span>

  - <span data-ttu-id="f2d7b-138">서비스 복원.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-138">Restoration of service.</span></span>

<span data-ttu-id="f2d7b-139">**풀 및 서버 백업**</span><span class="sxs-lookup"><span data-stu-id="f2d7b-139">**Pool and server backup**</span></span>

<span data-ttu-id="f2d7b-140">백업 및 복원 계획에는 지속적으로 백업 절차를 완료 하는 데 필요한 모든 정보가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="f2d7b-141">책임자 팀 구성원에 게 전달 되는 주요 정보에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="f2d7b-142">각 서버 백업을 담당 하는 팀 또는 사용자 (개인 또는 역할로 지정 됨)</span><span class="sxs-lookup"><span data-stu-id="f2d7b-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="f2d7b-143">각 서버를 백업 하기 위한 특정 일정</span><span class="sxs-lookup"><span data-stu-id="f2d7b-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="f2d7b-144">각 데이터 형식 (설정, 데이터베이스, 파일 공유)에 대 한 백업 위치</span><span class="sxs-lookup"><span data-stu-id="f2d7b-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="f2d7b-145">각 절차를 완료 하는 데 필요한 도구를 포함 하 여 사용할 백업 절차</span><span class="sxs-lookup"><span data-stu-id="f2d7b-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="f2d7b-146">[Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 명시 된 대로 백업을 완료 하는 데 필요한 정보</span><span class="sxs-lookup"><span data-stu-id="f2d7b-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="f2d7b-147">정기적 감사 및 테스트 복원을 포함할 수 있는 데이터 및 설정이 적절 하 게 백업 되 고 복원 가능한 지 확인 하는 데 사용 되는 유효성 검사 메서드.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="f2d7b-148">**서비스 복원**</span><span class="sxs-lookup"><span data-stu-id="f2d7b-148">**Restoration of service**</span></span>

<span data-ttu-id="f2d7b-149">하나 이상의 서버에서 서비스를 사용할 수 없게 되는 손실이 발생 하는 경우 백업 및 복원 계획에 서비스를 복원 하는 데 필요한 모든 정보가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="f2d7b-150">책임자 팀 구성원에 게 전달 되는 주요 정보에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="f2d7b-151">서비스 복원이 필요한 시기와 서비스를 복원 하는 데 사용 되는 절차 및 각 사용자에 대 한 절차를 구현 해야 하는 팀 또는 사용자를 결정 하는 팀 또는 개인 (개인 또는 역할로 지정 됨) 복원 시나리오.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="f2d7b-152">특정 상황에 가장 적합 한 복원 절차를 결정 하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="f2d7b-153">각 복원 시나리오에서 서비스 및 RTO (복구 시간 목표) 복원에 대 한 시간을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="f2d7b-154">각 절차를 완료 하는 데 필요한 도구를 포함 하 여 복원 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="f2d7b-155">데이터 및 설정을 복원 하는 데 필요한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-155">Information required to restore data and settings.</span></span> <span data-ttu-id="f2d7b-156">워크시트는 [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="f2d7b-157">백업 및 복원 작업의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f2d7b-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="f2d7b-158">실제 환경에서 초기 백업 노력을 완료 한 후 지정 된 간격 (백업 및 복원 계획에 명시 된 대로)에서 다음 사항을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="f2d7b-159">필요에 따라 백업이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="f2d7b-160">백업 된 데이터 및 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="f2d7b-161">복원 절차는 백업 및 복원 계획에 지정 된 RTO (복구 시간 목표) 시간 내에 수행할 수 있으며, 결과는 모든 비즈니스 요구 사항에 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="f2d7b-162">백업 워크시트를 완료 하 고 확인 한 후 안전한 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="f2d7b-163">이러한 워크시트는 [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="f2d7b-164">백업 및 복원 계획에 지정 된 대로 복원 절차가 테스트 되 고 예상 대로 작동 하는지 확인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="f2d7b-165">백업 및 복원 계획 유지 관리</span><span class="sxs-lookup"><span data-stu-id="f2d7b-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="f2d7b-166">Lync 서버 토폴로지는 조직과 달라 지는 동적 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="f2d7b-167">조직의 변화에 따라 백업 및 복원 계획을 Reassess 하 고 정기적으로 검토 하 여 비즈니스 요구에 맞게 지속적으로 진행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d7b-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

