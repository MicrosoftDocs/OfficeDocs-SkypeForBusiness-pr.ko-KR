---
title: 현재 도메인 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: '비즈니스용 Skype Server 또는 비즈니스용 Skype Server 사용자를 실행 하는 서버를 호스트 하기 위해 도메인을 준비 하려면 설치 프로그램을 사용 하 여 도메인 준비를 실행 하는 항목에 설명 된 대로 5 단계: 현재 도메인 준비를 완료 해야 합니다. 단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다. 도메인을 준비하려면 다음을 수행합니다.'
ms.openlocfilehash: 966f80fe799529ec4d208318fa417146db67ea13
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705443"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="f0aca-105">현재 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="f0aca-105">Prepare Current Domain</span></span>

<span data-ttu-id="f0aca-106">비즈니스용 Skype Server 또는 비즈니스용 Skype Server 사용자를 실행 하는 서버를 호스트 하기 위해 도메인을 준비 하려면 [설치 프로그램을 사용 하 여 도메인 준비를 실행 하](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)는 항목에 설명 된 대로 **5 단계: 현재 도메인 준비**를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="f0aca-107">단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="f0aca-108">도메인을 준비하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-108">To prepare the domain:</span></span>

1. <span data-ttu-id="f0aca-109">비즈니스용 Skype Server 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 비즈니스용 Skype 서버 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="f0aca-110">**Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="f0aca-111">**5단계: 현재 도메인 준비**에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="f0aca-112">**명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="f0aca-113">**작업** 열에서 **도메인 Prep**을 확장 하 고 각 작업의 끝에서 \*\* \<성공\> \*\* 실행 결과를 찾아 도메인 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="f0aca-114">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 해야 하는 경우에는 해당 단계를 실행 하는 Active Directory 도메인 서비스 사용자의 사용자 디렉터리에서 배포 마법사가 실행 된 컴퓨터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="f0aca-115">예를 들어 사용자가 도메인 Contoso.net의 도메인 관리자로 로그인 한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp.에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0aca-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


