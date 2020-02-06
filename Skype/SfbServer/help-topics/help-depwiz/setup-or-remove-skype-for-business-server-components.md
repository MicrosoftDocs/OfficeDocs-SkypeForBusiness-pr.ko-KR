---
title: 비즈니스용 Skype 서버 구성 요소 설치 또는 제거
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: '비즈니스용 Skype 서버 2015 구성 요소를 설치 및 활성화 또는 비활성화 하거나 제거 하려면 2 단계: Skype Server 구성 요소 설치 또는 제거를 사용 합니다. 설치 하거나 수정 하는 컴퓨터에 로컬 관리자로 로그인 해야 하며 현재 도메인의 Active Directory 도메인 서비스 사용자 및 그룹을 읽을 수 있어야 합니다. 시작하려면 실행을 클릭합니다. 그러면 중앙 관리 저장소 기반 토폴로지 정의를 읽습니다. 필요한 소프트웨어 구성 요소가 중앙 관리 저장소에 정의된 대로 역할에 따라 설치 및 구성됩니다. 설치가 완료되면 요약을 검토하고 마침을 클릭합니다.'
ms.openlocfilehash: b9fbdf7960c9d3fc8e11e9064ef6ca1b7f23b308
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823382"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="5bedf-108">비즈니스용 Skype 서버 구성 요소 설치 또는 제거</span><span class="sxs-lookup"><span data-stu-id="5bedf-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="5bedf-109">비즈니스용 Skype 서버 2015 구성 요소를 설치 및 활성화 또는 비활성화 하거나 제거 하려면 **2 단계: Skype Server 구성 요소 설치 또는 제거**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-109">To install and activate, or deactivate or uninstall Skype for Business Server 2015 components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="5bedf-110">설치 하거나 수정 하는 컴퓨터에 로컬 관리자로 로그인 해야 하며 현재 도메인의 Active Directory 도메인 서비스 사용자 및 그룹을 읽을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="5bedf-111">시작하려면 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-111">To begin, click **Run**.</span></span> <span data-ttu-id="5bedf-112">그러면 중앙 관리 저장소 기반 토폴로지 정의를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="5bedf-113">필요한 소프트웨어 구성 요소가 중앙 관리 저장소에 정의된 대로 역할에 따라 설치 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="5bedf-114">설치가 완료되면 요약을 검토하고 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="5bedf-115">배포 마법사에서 만든 로그 파일을 검토 해야 하는 경우 배포 마법사가 실행 된 컴퓨터에서 해당 단계를 실행 한 Active Directory 사용자의 사용자 디렉터리에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="5bedf-116">예를 들어 사용자가 도메인 Contoso.net의 도메인 관리자로 로그인 한 경우 로그 파일의 위치는 다음과 같습니다. > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="5bedf-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5bedf-117">이전에이 컴퓨터에 비즈니스용 Skype 서버 2015 구성 요소를 설치한 경우 배포 마법사에서이를 인식 하 고 2 단계의 단추가 **다시 실행**으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-117">If you have previously installed Skype for Business Server 2015 components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="5bedf-118">이 단추를 통해 서버를 올바르게 구성하거나 수정하는 데 필요한 횟수만큼 단계를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bedf-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

