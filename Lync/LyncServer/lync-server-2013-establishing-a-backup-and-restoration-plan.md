---
title: 'Lync Server 2013: 백업 및 복원 계획 설정'
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
ms.openlocfilehash: 64d9842ccb9d83fb7ce81c326008e36722e45764
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514225"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="02b6e-102">Lync Server 2013에 대 한 백업 및 복원 계획 설정</span><span class="sxs-lookup"><span data-stu-id="02b6e-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02b6e-103">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="02b6e-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="02b6e-104">백업 및 복원 계획을 만들 때는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="02b6e-105">계획 개발</span><span class="sxs-lookup"><span data-stu-id="02b6e-105">Developing the plan.</span></span>

  - <span data-ttu-id="02b6e-106">계획 구현</span><span class="sxs-lookup"><span data-stu-id="02b6e-106">Implementing the plan.</span></span>

  - <span data-ttu-id="02b6e-107">계획 유지 관리</span><span class="sxs-lookup"><span data-stu-id="02b6e-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="02b6e-108">백업 및 복원 계획 개발</span><span class="sxs-lookup"><span data-stu-id="02b6e-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="02b6e-109">Lync Server에 대 한 백업 및 복원 전략을 개발한 후에는이를 사용 하 여 자세한 백업 및 복원 계획을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="02b6e-110">계획에는 데이터 및 설정 백업을 위한 우선 순위 및 요구 사항이 명확하게 표시되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="02b6e-111">[Lync server 2013에 대 한 백업 및 복원 전략을 설정](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) 하는 방법과 [lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md) 에 있는 워크시트에 대 한 정보를 사용 하 여 전략 설명서를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="02b6e-112">계획에는 또한 서비스 복원 시기 및 방법을 결정하는 기준이 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="02b6e-113">계획을 개발할 때는 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="02b6e-114">새 하드웨어로 서버를 복구하는 방법</span><span class="sxs-lookup"><span data-stu-id="02b6e-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="02b6e-115">여러 비즈니스 영역 또는 부서 부분에 대한 작업이 필요한 서비스 복구 방법</span><span class="sxs-lookup"><span data-stu-id="02b6e-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="02b6e-116">예비 서버를 신속하게 얻을 수 있는 방법</span><span class="sxs-lookup"><span data-stu-id="02b6e-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="02b6e-117">전략을 사용하여 복구하는 데 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="02b6e-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="02b6e-118">조직의 RTO (복구 시간 목표)에 대 한 요구 사항을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="02b6e-119">이 항목의 백업 및 복원 절차를 적절 하 게 추가 및 삭제 하 여 배포의 서버와 구성 요소를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="02b6e-120">또한 백업 일정과 같은 적절 한 세부 정보를 적절 한 절차에 추가 하 여 정보를 간과 하지 않도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02b6e-121">절차의 품질과 재현 가능성을 보장 하기 위해 가능한 한 여러 단계로 스크립트를 작성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="02b6e-122">계획에서 계획 검토 책임자, 새로운 절차 또는 도구 테스트 및 유효성 검사 책임자, 계획 및 관련 절차에 대 한 변경 내용을 승인 해야 하는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="02b6e-123">백업 및 복원 계획이 모든 설정 된 목표 및 우선 순위를 완전히 충족 하는지 확인 하려면 계획을 구현 하기 전에 조직에서 적절 한 비즈니스 의사 결정권자 및 기술 의사 결정자의 승인을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="02b6e-124">백업 및 복원 계획 구현</span><span class="sxs-lookup"><span data-stu-id="02b6e-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="02b6e-125">백업 및 복원 계획을 구현 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="02b6e-126">계획 테스트 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="02b6e-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="02b6e-127">요금제를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-127">Communicating the plan.</span></span>

  - <span data-ttu-id="02b6e-128">백업 및 복원 작업의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="02b6e-129">계획 테스트 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="02b6e-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="02b6e-130">여기서 설명 하는 절차는 랩 환경에서 테스트 하 고 유효성을 검사 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="02b6e-131">사용자 환경에서 이러한 절차가 작동 하는지 확인 하려면 구현 하려는 각 절차를 테스트 하 고 유효성을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="02b6e-132">최종 승인을 위해 요금제를 제출 하기 전에 테스트 및 유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="02b6e-133">계획 커뮤니케이션</span><span class="sxs-lookup"><span data-stu-id="02b6e-133">Communicating the Plan</span></span>

<span data-ttu-id="02b6e-134">백업 및 복원 계획은 절차 및 절차 수행을 위한 단계별 지침을 구현하는 사용자에게 명확하게 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="02b6e-135">백업 및 복원을 담당 하는 모든 사용자가 계획, 구현 방법 및 역할을 이해 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="02b6e-136">여기에는 다음에 대한 모든 구현 요구 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="02b6e-137">풀 및 서버 백업</span><span class="sxs-lookup"><span data-stu-id="02b6e-137">Pool and server backup.</span></span>

  - <span data-ttu-id="02b6e-138">서비스 복원</span><span class="sxs-lookup"><span data-stu-id="02b6e-138">Restoration of service.</span></span>

<span data-ttu-id="02b6e-139">**풀 및 서버 백업**</span><span class="sxs-lookup"><span data-stu-id="02b6e-139">**Pool and server backup**</span></span>

<span data-ttu-id="02b6e-p106">백업 및 복원 계획에는 지속적으로 백업 절차를 완료하는 데 필요한 모든 정보가 포함되어야 합니다. 각각의 책임이 있는 팀 구성원에게 전달해야 하는 기본 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="02b6e-142">각 서버를 백업할 책임이 있는 팀 또는 사용자 (개인 또는 역할로 지정)</span><span class="sxs-lookup"><span data-stu-id="02b6e-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="02b6e-143">각 서버 백업에 대 한 특정 일정</span><span class="sxs-lookup"><span data-stu-id="02b6e-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="02b6e-144">각 데이터 형식에 대 한 백업 위치 (설정, 데이터베이스 및 파일 공유)</span><span class="sxs-lookup"><span data-stu-id="02b6e-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="02b6e-145">각 절차를 완료 하는 데 필요한 도구를 포함 하 여 사용할 백업 절차</span><span class="sxs-lookup"><span data-stu-id="02b6e-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="02b6e-146">[Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 설명 된 대로 백업을 완료 하는 데 필요한 정보</span><span class="sxs-lookup"><span data-stu-id="02b6e-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="02b6e-147">데이터 및 설정을 적절 하 게 백업 하 고 복원에 사용할 수 있도록 하는 데 사용 되는 유효성 검사 방법 (주기적인 감사 및 테스트 복원을 포함할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="02b6e-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="02b6e-148">**서비스 복원**</span><span class="sxs-lookup"><span data-stu-id="02b6e-148">**Restoration of service**</span></span>

<span data-ttu-id="02b6e-149">백업 및 복원 계획에는 서비스를 사용 하지 않도록 설정 하는 서버가 하나 이상 손실 될 경우이를 복원 하는 데 필요한 모든 정보가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="02b6e-150">각각의 책임이 있는 팀 구성원에게 전달해야 하는 기본 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="02b6e-151">서비스 복원이 필요한 시간 및 서비스 복원에 사용할 절차 그리고 각 복원 시나리오의 절차를 구현할 책임이 있는 팀 또는 사용자를 확인할 책임이 있는 팀 또는 사용자(개인 또는 역할로 지정됨)</span><span class="sxs-lookup"><span data-stu-id="02b6e-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="02b6e-152">특정 상황에 가장 적합한 복원 절차를 확인하기 위한 기준</span><span class="sxs-lookup"><span data-stu-id="02b6e-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="02b6e-153">각 복원 시나리오에서 서비스 및 RTO (복구 시간 목표) 복원에 대 한 예상 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="02b6e-154">각 절차를 완료하는 데 필요한 도구를 포함하는 사용할 복원 절차</span><span class="sxs-lookup"><span data-stu-id="02b6e-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="02b6e-155">데이터 및 설정 복원에 필요한 정보.</span><span class="sxs-lookup"><span data-stu-id="02b6e-155">Information required to restore data and settings.</span></span> <span data-ttu-id="02b6e-156">워크시트는 [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="02b6e-157">백업 및 복원 작업 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="02b6e-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="02b6e-158">프로덕션 환경에서 초기 백업 작업을 완료한 후 백업 및 복원 계획에 표시된 것처럼 지정된 간격에 따라 다음을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="02b6e-159">필요에 따라 백업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="02b6e-160">백업한 데이터 및 설정을 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="02b6e-161">복원 절차는 백업 및 복원 계획에 지정 된 RTO (복구 시간 목표) 시간 내에 수행할 수 있으며, 결과는 모든 비즈니스 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="02b6e-162">백업 워크시트가 완료 및 확인되었으며 안전한 위치에 저장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="02b6e-163">이러한 워크시트는 [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="02b6e-164">백업 및 복원 계획에 지정된 대로 필요에 따라 복원 절차가 테스트 및 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="02b6e-165">백업 및 복원 계획 유지 관리</span><span class="sxs-lookup"><span data-stu-id="02b6e-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="02b6e-166">Lync Server 토폴로지는 조직에서 변경 되는 동적 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="02b6e-167">조직이 변경 됨에 따라 백업 및 복원 계획을 다시 평가 합니다이를 주기적으로 검토 하 여 비즈니스 요구에 맞게 계속 진행 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6e-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

