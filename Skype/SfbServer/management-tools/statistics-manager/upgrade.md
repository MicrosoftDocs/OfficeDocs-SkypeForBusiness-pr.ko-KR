---
title: 비즈니스용 Skype 서버 통계 관리자 업그레이드
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자를 업그레이드하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821768"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="2b866-103">비즈니스용 Skype 서버 통계 관리자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2b866-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="2b866-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자를 업그레이드하는 방법을 배워 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="2b866-105">이 항목에서는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구인 비즈니스용 Skype 서버 통계 관리자의 기존 설치를 업그레이드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="2b866-106">몇 초마다 수백 대의 서버로 성능 데이터를 폴링하고 통계 관리자 웹 사이트에서 결과를 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="2b866-107">통계 관리자 및 릴리스 2.0의 새로운 기능에 대한 자세한 내용은 비즈니스용 [Skype](plan.md) 서버의 통계 관리자 계획 및 비즈니스용 Skype 서버용 통계 관리자 배포를 [참조하세요.](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="2b866-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="2b866-108">업그레이드 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="2b866-109">**자동화된 업그레이드.**</span><span class="sxs-lookup"><span data-stu-id="2b866-109">**Automated upgrade.**</span></span> <span data-ttu-id="2b866-110">이 메서드는 자동화된 스크립트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-110">This method uses an automated script.</span></span> <span data-ttu-id="2b866-111">가장 쉬운 방법일 수 있으며 모든 업그레이드 시나리오에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="2b866-112">**수동 업그레이드.**</span><span class="sxs-lookup"><span data-stu-id="2b866-112">**Manual upgrade.**</span></span> <span data-ttu-id="2b866-113">이 방법은 자동화된 업그레이드가 실패하는 비정상적인 경우 백업 계획으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="2b866-114">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2b866-114">Prerequisites</span></span>

<span data-ttu-id="2b866-115">업그레이드하기 전에 다음 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="2b866-116">활성 수신기 인증서 지문</span><span class="sxs-lookup"><span data-stu-id="2b866-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="2b866-117">수신기 서비스 암호(수신기 및 모든 에이전트를 설치할 때 입력)</span><span class="sxs-lookup"><span data-stu-id="2b866-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="2b866-118">웹 사이트에 대한 SSL 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="2b866-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="2b866-119">자동화된 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2b866-119">Automated upgrade</span></span>

<span data-ttu-id="2b866-120">스크립트는 현재 인증서 정보 및 수신기 암호를 수집하고 이전 버전의 제품을 제거한 다음 제품의 새 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="2b866-121">서버에 설치된 Redis 인스턴스는 터치되지 않습니다. 따라서 캐시에 저장된 데이터는 업그레이드 프로세스를 통해 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="2b866-122">새 버전의 에이전트, 수신기 및 웹 사이트의 MSI 파일과 Update-StatsMan.ps1 스크립트를 수신기 컴퓨터의 단일 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="2b866-123">관리 PowerShell 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="2b866-124">수신기 구성 요소를 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="2b866-125">통계 관리자 서비스 암호는 설치 관리자에 전달될 때 명령줄에 명확한 텍스트로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="2b866-126">필요한 경우 모니터를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="2b866-127">스크립트를 실행하는 경우 이전 버전의 제품을 제거하라는 메시지가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="2b866-128">예로 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="2b866-129">수신기 서비스가 실행 중인 경우 계속하기 전에 응용 프로그램을 닫을지 묻는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="2b866-130">응용 프로그램을 닫을 수 있도록 허용합니다(Statistics Manager Listener Service가 중지됨).</span><span class="sxs-lookup"><span data-stu-id="2b866-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="2b866-131">설치 프로세스를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-131">Continue the install process.</span></span> <span data-ttu-id="2b866-132">서비스 암호 및 인증서 지문이 미리 채워진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="2b866-133">그렇지 않은 경우 저장한 값을 계속하기 전에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="2b866-134">관리 PowerShell 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="2b866-135">웹 사이트 구성 요소를 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="2b866-136">스크립트를 실행하는 경우 이전 버전의 제품을 제거하라는 메시지가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="2b866-137">예로 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="2b866-138">에이전트 서비스가 실행 중인 경우 계속하기 전에 응용 프로그램을 닫을지 묻는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="2b866-139">응용 프로그램을 닫을 수 있도록 허용합니다(StatsMan 에이전트 서비스가 중지됨).</span><span class="sxs-lookup"><span data-stu-id="2b866-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="2b866-140">설치 프로세스를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-140">Continue the install process.</span></span> <span data-ttu-id="2b866-141">서비스 암호 및 인증서 지문이 미리 채워진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="2b866-142">그렇지 않은 경우 저장한 값을 계속하기 전에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="2b866-143">관리 PowerShell 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="2b866-144">에이전트 구성 요소를 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="2b866-145">스크립트를 실행하는 경우 이전 버전의 제품을 제거하라는 메시지가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="2b866-146">예로 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="2b866-147">설치 프로세스를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-147">Continue the install process.</span></span> <span data-ttu-id="2b866-148">웹 사이트 포트가 미리 채워진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="2b866-149">그렇지 않은 경우 저장한 값을 추가한 후 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="2b866-150">브라우저를 사용하여 웹 사이트가 예상대로 작동하고 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2b866-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b866-151">에이전트 업그레이드는 -NoPrompt 스위치와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="2b866-152">이렇게 하면 제거/설치 프로세스가 자동으로 실행되므로 PSExec 같은 도구가 많은 서버에서 원격으로 업그레이드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="2b866-153">수동 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2b866-153">Manual upgrade</span></span>

<span data-ttu-id="2b866-154">어떤 이유로 인해 자동화된 업그레이드가 실패하면 항상 다음과 같이 수동 업그레이드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="2b866-155">수신기 컴퓨터에서 프로그램 및 기능 제어판을 통해 수신기, 웹 사이트 및 에이전트(이 서버에 설치된 경우)를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="2b866-156">그런 다음 업그레이드 프로세스를 통해 캐시의 데이터가 유지 관리될 수 있도록 Redis를 설치한 후 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="2b866-157">메시지가 표시될 때 위에 저장한 값을 포함하여 새 버전의 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b866-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="2b866-158">구성 요소 설치에 대한 자세한 내용은 통계 관리자 [배포를 참조하십시오.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="2b866-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="2b866-159">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="2b866-159">For more information</span></span>
<span data-ttu-id="2b866-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="2b866-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="2b866-161">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b866-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="2b866-162">비즈니스용 Skype 서버 통계 관리자에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="2b866-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="2b866-163">비즈니스용 Skype 서버 통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="2b866-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="2b866-164">비즈니스용 Skype 서버 통계 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2b866-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
