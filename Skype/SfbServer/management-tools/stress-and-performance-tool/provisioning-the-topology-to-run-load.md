---
title: 스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로비전
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 사용자가 스트레스 및 성능 도구를 성공적으로 실행할 수 있도록 비즈니스용 Skype 서버 2015 토폴로지 변경 또는 프로비전
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814938"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="ce6e8-103">스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로비전</span><span class="sxs-lookup"><span data-stu-id="ce6e8-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="ce6e8-104">사용자가 스트레스 및 성능 도구를 성공적으로 실행할 수 있도록 비즈니스용 Skype 서버 2015 토폴로지 변경 또는 프로비전</span><span class="sxs-lookup"><span data-stu-id="ce6e8-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="ce6e8-105">비즈니스용 Skype 서버 2015 배포에 대한 기존 설정 및 구성에 따라 환경을 일부 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="ce6e8-106">다음은 이러한 변경 내용의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="ce6e8-107">실행 Windows PowerShell 제한되지 않은 정책으로 설정</span><span class="sxs-lookup"><span data-stu-id="ce6e8-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="ce6e8-108">현재 설정되어 있는 것이 확실하지 않은 경우 비즈니스용 Skype 서버 관리 셸을 열고 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="ce6e8-109">무제한 값이 반환되지 않는 경우 다음에 이 값을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="ce6e8-110">비즈니스용 Skype 서버를 효과적으로 구성하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="ce6e8-111">비즈니스용 Skype 서버 2015 토폴로지(예: 컴퓨터 이름, 서비스 인스턴스, 사이트 이름 및 정책)에 대해 잘 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="ce6e8-112">응답 그룹 헌트 그룹(예: SIP UR)처럼 그룹에 만들어진 일부 사용자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="ce6e8-113">명령줄에서 스크립트를 실행하기 위해 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="ce6e8-114">일반적으로 이 패키지에서 스크립트를 실행한 후 결과 추적은 스크립트가 실행된 동일한 경로의 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="ce6e8-115">$m$ $h 이름 형식도 \<scriptname\>s.txt.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="ce6e8-116">따라서 오후 12시 15분에 ArchivingPolicy.ps1 로그 파일을 ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="ce6e8-117">서버 구성에 대한 이러한 예제를 제공한 경우 부하 테스트를 완료한 후 구성을 수정하고 복원하거나 롤백하는 것이 모두 사용자에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce6e8-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

