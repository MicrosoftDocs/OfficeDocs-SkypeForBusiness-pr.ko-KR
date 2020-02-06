---
title: 현재 포리스트 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory 도메인 서비스 포리스트를 준비 하려면 스키마 준비 실행 항목에 설명 된 대로 스키마를 성공적으로 확장 하 고 스키마가 복제 되었는지 확인 해야 합니다.
ms.openlocfilehash: 0458fee54814f7f48382709a0509494e770d3e2b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798315"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="9eef2-103">현재 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="9eef2-103">Prepare Current Forest</span></span>

<span data-ttu-id="9eef2-104">Active Directory 도메인 서비스 포리스트를 준비 하려면 스키마 [준비 실행](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)항목에 설명 된 대로 스키마를 성공적으로 확장 하 고 스키마가 복제 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="9eef2-p101">이러한 선행 조건을 완료한 후 **3단계: 현재 포리스트 준비**를 시작할 수 있습니다. 포리스트를 준비하려면 포리스트 루트에서 Domain Admins의 구성원으로 또는 준비할 포리스트에 대한 Enterprise Admins의 구성원으로 포리스트 루트에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="9eef2-107">배포 마법사의 **3단계: 현재 포리스트 준비**에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="9eef2-108">**포리스트 준비** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eef2-109">포리스트 준비를 사용 하 여 비즈니스용 Skype 서버용 유니버설 그룹을 배치할 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="9eef2-110">조직의 요구 사항에 맞는 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="9eef2-p103">**명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다. 오류가 없는지 확인합니다. 경고를 검토하여 해당 경고가 인프라에 대해 예상된 것이며 일반적인 것인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="9eef2-114">로그의 **작업** 열에서 **포리스트**준비를 확장 하 고 각 작업의 끝 \*\* \<에서\> 성공\*\* 실행 결과를 찾아 포리스트 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="9eef2-115">도메인 준비를 실행 하기 전에 Active Directory 도메인 서비스 복제가 완료 되거나 포리스트 루트 도메인 컨트롤러에 대 한 **Active Directory 사이트 및 서비스** 스냅인에 나열 된 모든 도메인 컨트롤러로 복제를 강제로 수행할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="9eef2-116">모든 Active Directory 사이트의 도메인 컨트롤러 간 복제를 강제로 사이트 내에서 몇 분 내에 복제를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="9eef2-117">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 해야 하는 경우 배포 마법사가 실행 된 컴퓨터에서 해당 단계를 실행 하는 Active Directory 도메인 서비스 사용자의 사용자 디렉터리에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="9eef2-118">예를 들어 사용자가 도메인 Contoso.net의 도메인 관리자로 로그인 한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eef2-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


