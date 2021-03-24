---
title: 비즈니스용 Skype에서 SEFAUtil 도구 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 비즈니스용 Skype 서버에서 SEFAUtil 도구 배포
ms.openlocfilehash: 013890e3b65dfd3a8360da859a1c9179fa9b5a13
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105804"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="850cb-103">비즈니스용 Skype에서 SEFAUtil 도구 배포</span><span class="sxs-lookup"><span data-stu-id="850cb-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="850cb-104">비즈니스용 Skype 서버에서 SEFAUtil 도구 배포</span><span class="sxs-lookup"><span data-stu-id="850cb-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="850cb-105">그룹 통화 Pickup을 배포하고 관리하려면 SEFAUtil 도구의 비즈니스용 Skype 서버 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="850cb-106">SEFAUtil 도구를 실행하려면 모든 컴퓨터에 Microsoft UCMA(Unified Communications Managed API) 5 런타임이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="850cb-107">여기에서 다운로드하세요. [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="850cb-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="850cb-108">런타임이 포함된 UCMA 5 SDK는 [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345)에서 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="850cb-109">배포의 모든 프런트 엔드 풀에서 SEFAUtil 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="850cb-110">SEFAUtil 도구를 실행하려면 신뢰할 수 있는 응용 프로그램 컴퓨터의 비즈니스용 Skype 배포 마법사에서 1, 2, 3단계를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="850cb-111">SEFAUtil을 사용하려면 인증서뿐만 아니라 로컬 구성 저장소도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="850cb-112">SEFAUtil을 실행하는 방법에 대한 자세한 내용은 블로그 문서["SEFAutil을](/archive/blogs/jenstr/how-to-get-sefautil-running)실행하는 방법" "을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="850cb-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](/archive/blogs/jenstr/how-to-get-sefautil-running)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="850cb-113">SEFAUtil을 배포하기 위해</span><span class="sxs-lookup"><span data-stu-id="850cb-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="850cb-114">비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**</span><span class="sxs-lookup"><span data-stu-id="850cb-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="850cb-115">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="850cb-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="850cb-116">SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="850cb-117">필요한 경우 SEFAUtil을 실행할 프런트 엔드 풀에 대해 신뢰할 수 있는 응용 프로그램 풀을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="850cb-118">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="850cb-119">풀 FQDN: SEFAUtil 응용 프로그램(일반적으로 비즈니스용 Skype 프런트 엔드 서버 또는 풀)을 호스팅할 서버 또는 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="850cb-120">풀 등록자 FQDN: 이 응용 프로그램 풀과 연결된 비즈니스용 Skype 프런트 엔드 서버 또는 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="850cb-121">풀 사이트: 이 풀이 있는 사이트의 사이트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="850cb-122">SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="850cb-123">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="850cb-124">필요한 경우 다른 포트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="850cb-125">변경 내용과 함께 토폴로지 사용.</span><span class="sxs-lookup"><span data-stu-id="850cb-125">Enable the topology with your changes.</span></span> <span data-ttu-id="850cb-126">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="850cb-127">아직 설치하지 않은 경우 이 위치에서 SEFAUtil 도구의 비즈니스용 [](https://www.microsoft.com/download/details.aspx?id=52631)Skype 서버 버전을 다운로드하고 3단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="850cb-128">다음과 같이 SEFAUtil 도구가 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="850cb-129">a.</span><span class="sxs-lookup"><span data-stu-id="850cb-129">a.</span></span> <span data-ttu-id="850cb-130">관리자 권한으로 Windows 명령 프롬프트에서 도구를 실행하여 배포에 있는 사용자의 통화 전달 설정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="850cb-131">b.</span><span class="sxs-lookup"><span data-stu-id="850cb-131">b.</span></span> <span data-ttu-id="850cb-132">사용자의 통화 전달 설정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="850cb-133">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="850cb-134">사용자에 대한 전달 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="850cb-134">The call forwarding settings for the user will be displayed.</span></span>
