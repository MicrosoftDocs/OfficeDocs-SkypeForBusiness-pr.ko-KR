---
title: 비즈니스용 Skype 서버 구성 요소 설치 또는 제거
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: '비즈니스용 Skype 서버 구성 요소를 설치 및 활성화 또는 비활성화하거나 제거하려면 2단계: Skype 서버 구성 요소 설치 또는 제거를 사용하세요. 설치 또는 수정 중인 컴퓨터에서 로컬 관리자로 로그인하고 현재 도메인의 Active Directory 도메인 서비스 사용자 및 그룹을 읽을 수 있어야 합니다. 시작하려면 실행을 클릭합니다. 그러면 중앙 관리 저장소 기반 토폴로지 정의를 읽습니다. 필요한 소프트웨어 구성 요소가 중앙 관리 저장소에 정의된 대로 역할에 따라 설치 및 구성됩니다. 설치가 완료되면 요약을 검토하고 마침을 클릭합니다.'
ms.openlocfilehash: 8a004e17984a927d08b7c814f8a4ba435c98971e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825058"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="030fc-108">비즈니스용 Skype 서버 구성 요소 설치 또는 제거</span><span class="sxs-lookup"><span data-stu-id="030fc-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="030fc-109">비즈니스용 Skype 서버 구성 요소를 설치 및 활성화 또는 비활성화하거나 제거하려면 **2단계: Skype 서버** 구성 요소 설치 또는 제거를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="030fc-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="030fc-110">설치 또는 수정 중인 컴퓨터에서 로컬 관리자로 로그인하고 현재 도메인의 Active Directory 도메인 서비스 사용자 및 그룹을 읽을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="030fc-111">시작하려면 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-111">To begin, click **Run**.</span></span> <span data-ttu-id="030fc-112">그러면 중앙 관리 저장소 기반 토폴로지 정의를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="030fc-113">필요한 소프트웨어 구성 요소가 중앙 관리 저장소에 정의된 대로 역할에 따라 설치 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="030fc-114">설치가 완료되면 요약을 검토하고 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="030fc-115">배포 마법사에서 만든 로그 파일을 검토해야 하는 경우 배포 마법사를 실행한 컴퓨터의 단계를 실행한 Active Directory 사용자의 Users 디렉터리에서 로그 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="030fc-116">예를 들어 사용자가 도메인 Contoso.net 도메인 관리자로 로그인한 경우 로그 파일은 > C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="030fc-117">이 컴퓨터에 이전에 비즈니스용 Skype 서버 구성 요소를 설치한 경우 배포 마법사에서 이를 인식하고 2단계의 단추가 다시 실행으로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="030fc-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="030fc-118">이 단추를 통해 서버를 올바르게 구성하거나 수정하는 데 필요한 횟수만큼 단계를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="030fc-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

