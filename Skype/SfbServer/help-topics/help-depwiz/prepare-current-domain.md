---
title: 현재 도메인 준비
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: '비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버 사용자를 실행하는 서버를 호스트할 도메인을 준비하려면 Using Setup to Run Domain Preparation 항목에 설명된 5단계: 현재 도메인 준비를 완료해야 합니다. 단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다. 도메인을 준비하려면 다음을 수행합니다.'
ms.openlocfilehash: c9c33e466b7b0fcc7c2711603c284e5f419960a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096874"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="c5280-105">현재 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="c5280-105">Prepare Current Domain</span></span>

<span data-ttu-id="c5280-106">비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버 사용자를 실행하는 서버를 호스트할 도메인을 준비하려면 Using Setup [to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)항목에 설명된 **5단계:** 현재 도메인 준비를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="c5280-107">단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="c5280-108">도메인을 준비하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-108">To prepare the domain:</span></span>

1. <span data-ttu-id="c5280-109">비즈니스용 Skype 서버 2015 설치 폴더 또는 미디어에서 비즈니스용 Skype Setup.exe 실행하여 비즈니스용 Skype 서버 배포 마법사를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="c5280-110">**Active Directory 준비** 를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="c5280-111">**5단계: 현재 도메인 준비** 에서 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="c5280-112">**명령 실행** 페이지에서 **작업 상태: 완료됨** 을 찾은 다음 **로그 보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="c5280-113">작업 **열 아래에서** **도메인** 준비를 확장하고 각 작업 끝에 있는 실행 결과를 찾아 도메인 준비가 성공적으로 완료된지 확인하고 로그를 닫고 마친 을 **\<Success\>** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5280-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="c5280-114">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토해야 하는 경우 배포 마법사를 실행한 컴퓨터에서 해당 단계를 실행한 Active Directory 도메인 서비스 사용자의 Users 디렉터리에서 로그 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="c5280-115">예를 들어 사용자가 도메인 관리자로 로그인한 경우 Contoso.net 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5280-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>