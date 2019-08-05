---
title: 비즈니스용 Skype에서 SEFAUtil 도구 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 비즈니스용 Skype 서버에서 SEFAUtil 도구 배포
ms.openlocfilehash: 74b9ca6fa10237760e84f859baad5188436ac80e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197493"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="84ace-103">비즈니스용 Skype에서 SEFAUtil 도구 배포</span><span class="sxs-lookup"><span data-stu-id="84ace-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="84ace-104">비즈니스용 Skype 서버에서 SEFAUtil 도구 배포</span><span class="sxs-lookup"><span data-stu-id="84ace-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="84ace-105">그룹 통화 픽업을 배포 하 고 관리 하려면 비즈니스용 Skype 서버 버전의 SEFAUtil 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="84ace-106">Microsoft 통합 커뮤니케이션 관리 API (c) SEFAUtil 도구를 실행할 컴퓨터에는 5 개의 런타임을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="84ace-107">[통합 커뮤니케이션 관리 API 5.0 런타임을](https://www.microsoft.com/en-us/download/details.aspx?id=47344)여기에 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ace-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="84ace-108">또한 런타임, 그리고 여기에 포함 된 참조 ( [5.0 sdk](https://www.microsoft.com/en-us/download/details.aspx?id=47345))를 비롯 하 여 함께 다운로드 하는 sdk를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="84ace-109">배포의 모든 프런트 엔드 풀에서 SEFAUtil 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="84ace-110">SEFAUtil 도구를 실행 하려면 신뢰할 수 있는 응용 프로그램 컴퓨터의 비즈니스용 Skype 배포 마법사에서 1, 2, 3 단계를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="84ace-111">SEFAUtil에는 로컬 구성 저장소가 있어야 하 고 인증서도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84ace-112">SEFAUtil를 실행 하는 방법에 대 한 자세한 내용은 블로그 문서, "[실행 중인 SEFAUtil를 가져오는 방법](https://go.microsoft.com/fwlink/?LinkId=278940)"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ace-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="84ace-113">SEFAUtil 배포</span><span class="sxs-lookup"><span data-stu-id="84ace-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="84ace-114">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="84ace-115">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="84ace-116">SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="84ace-117">필요한 경우 SEFAUtil를 실행할 계획의 프런트 엔드 풀에 대해 신뢰할 수 있는 응용 프로그램 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="84ace-118">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="84ace-119">풀 FQDN: SEFAUtil 응용 프로그램을 호스트할 서버 또는 풀의 FQDN입니다 (일반적으로 비즈니스용 Skype 프런트 엔드 서버 또는 풀).</span><span class="sxs-lookup"><span data-stu-id="84ace-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="84ace-120">풀 등록자 FQDN:이 응용 프로그램 풀과 연결 된 비즈니스용 Skype 프런트 엔드 서버 또는 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="84ace-121">풀 사이트:이 풀이 속한 사이트의 사이트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="84ace-122">SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="84ace-123">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-123">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="84ace-124">필요한 경우 다른 포트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="84ace-125">변경 내용이 포함 된 토폴로지를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-125">Enable the topology with your changes.</span></span> <span data-ttu-id="84ace-126">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-126">At the command line, run:</span></span>
    
   ```
   Enable-CsTopology
   ```

6. <span data-ttu-id="84ace-127">아직 없는 경우 비즈니스용 Skype Server 버전을 [이 위치](https://www.microsoft.com/en-us/download/details.aspx?id=52631)에서 다운로드 하 여 3 단계에서 만든 신뢰 된 응용 프로그램 풀에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="84ace-128">다음과 같이 SEFAUtil 도구가 올바르게 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="84ace-129">에서.</span><span class="sxs-lookup"><span data-stu-id="84ace-129">a.</span></span> <span data-ttu-id="84ace-130">Windows 명령 프롬프트에서 관리자 권한으로 도구를 실행 하 여 배포에 있는 사용자의 착신 전환 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="84ace-131">b.</span><span class="sxs-lookup"><span data-stu-id="84ace-131">b.</span></span> <span data-ttu-id="84ace-132">사용자의 착신 전환 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="84ace-133">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-133">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="84ace-134">사용자의 착신 전환 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ace-134">The call forwarding settings for the user will be displayed.</span></span>
    

