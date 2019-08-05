---
title: 스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로 비전
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 사용자가 스트레스 및 성능 도구를 성공적으로 실행할 수 있도록 비즈니스용 Skype 서버 2015 토폴로지를 변경 하거나 프로 비전 합니다.
ms.openlocfilehash: c7cdc10b3667ac99376904c81309df739e49844a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197025"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="4c1f7-103">스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로 비전</span><span class="sxs-lookup"><span data-stu-id="4c1f7-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="4c1f7-104">사용자가 스트레스 및 성능 도구를 성공적으로 실행할 수 있도록 비즈니스용 Skype 서버 2015 토폴로지를 변경 하거나 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="4c1f7-105">비즈니스용 Skype Server 2015 배포에 대 한 기존 설정 및 구성에 따라 환경에서 몇 가지 변경 작업을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="4c1f7-106">다음은 이러한 변경의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="4c1f7-107">Windows PowerShell 실행 정책을 무제한으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="4c1f7-108">현재 설정 되어 있는지 확실 하지 않은 경우 비즈니스용 Skype Server Management Shell을 열고 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="4c1f7-109">무제한 값이 반환 되지 않는 경우 다음을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="4c1f7-110">비즈니스용 Skype 서버를 효과적으로 구성 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="4c1f7-111">비즈니스용 Skype 서버 2015 토폴로지 (컴퓨터 이름, 서비스 인스턴스, 사이트 이름, 정책 등)에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="4c1f7-112">응답 그룹 헌트 그룹과 같은 그룹에 만든 일부 사용자 (예: SIP Uri)를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="4c1f7-113">명령줄에서 스크립트를 실행 하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="4c1f7-114">일반적으로이 패키지에서 스크립트를 실행 하면 결과 추적은 스크립트가 실행 된 위치와 같은 경로에 있는 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="4c1f7-115">\<Scriptname\>$h $ m $ s .txt와 같은 이름 지정 형식으로도 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="4c1f7-116">따라서 12:15 PM에서 ArchivingPolicy를 실행 하면 ArchivingPolicy121500 라는 로그 파일이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="4c1f7-117">서버 구성에 대해 이러한 예제를 제공 했지만 부하 테스트 실행을 완료 한 후에는 구성을 수정 하 고 복원 하거나 롤백해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1f7-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

