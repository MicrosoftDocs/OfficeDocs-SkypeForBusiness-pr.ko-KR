---
title: 비즈니스용 Skype 서버를 통해 Lync VDI 플러그 인 배포
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype를 사용하는 배포 절차에 대해 설명합니다.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805938"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="84dad-103">비즈니스용 Skype 서버를 통해 Lync VDI 플러그 인 배포</span><span class="sxs-lookup"><span data-stu-id="84dad-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="84dad-104">이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype를 사용하는 배포 절차에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="84dad-105">계획 고려 사항은 VDI 환경의 [비즈니스용 Skype 계획에 있습니다.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)</span><span class="sxs-lookup"><span data-stu-id="84dad-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="84dad-106">보안 및 규정 준수 문제가 특히 중요한 일부 조직에서는 VDI(가상 데스크톱 인프라) 환경이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="84dad-107">사용자가 로컬 Windows 컴퓨터에 있으며 가상 데스크톱의 클라이언트를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="84dad-108">추가 VDI 플러그 인 소프트웨어가 필요한 경우와 같은 연결에서 비즈니스용 Skype를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="84dad-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="84dad-109">VDI 플러그 인 구성 요소에는 Microsoft에서 제공하는 솔루션과 Citrix에서 제공하는 두 가지 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="84dad-110">Microsoft는 새 배포에서 새로운 HDX 실시간 최적화 팩 솔루션을 사용하는 것이 권장되지만 나머지 수명 주기 동안 원래 Lync VDI 플러그 인을 계속 지원할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="84dad-111">이 항목에서는 Windows 7 및 Windows 8 또는 Windows Server 2008에서만 지원되는 Microsoft Lync VDI 플러그 인 배포에 대해 자세히 설명하며 Lync 2013 또는 비즈니스용 Skype 클라이언트만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="84dad-112">이 플러그 인을 업데이트할 계획은 없지만 비즈니스용 [Skype용 Citrix HDX RealTime 최적화](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) 팩은 필요한 경우 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="84dad-113">Lync VDI 플러그 인을 위한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="84dad-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="84dad-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="84dad-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="84dad-115">비즈니스용 Skype 서버에서 모든 Lync VDI 플러그 인 사용자에 대해 EnableMediaRedirection이 TRUE로 설정되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="84dad-116">자세한 내용은 [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet 및 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="84dad-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="84dad-117">데이터 센터 서버에서 모든 가상 데스크톱에 비즈니스용 Skype 클라이언트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="84dad-118">로컬 컴퓨터에서 Lync VDI 플러그 인을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="84dad-119">이제 사용자가 헤드셋 또는 웹캠과 같은 장치를 로컬 컴퓨터에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="84dad-120">원격 데스크톱 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="84dad-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="84dad-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="84dad-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="84dad-122">Lync VDI 플러그 인에 대해 원격 데스크톱 연결을 준비하려면 로컬 컴퓨터에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="84dad-123">로컬 컴퓨터에서 Windows 8을 실행하는 경우 이 단계를 건너뜁니 다.</span><span class="sxs-lookup"><span data-stu-id="84dad-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="84dad-124">로컬 컴퓨터에서 Windows 7 SP1을 실행하는 경우 최신 버전의 원격 데스크톱 서비스 클라이언트를 [설치합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268032)</span><span class="sxs-lookup"><span data-stu-id="84dad-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="84dad-125">**시작** 을 클릭하고 **원격 데스크톱 연결** 을 클릭하여 원격 데스크톱 서비스 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="84dad-126">**옵션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="84dad-127">**로컬 자원** 탭을 클릭합니다. **원격 오디오** 에서 **설정** 을 클릭하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="84dad-128">**원격 오디오 재생** 에서 **이 컴퓨터에서 재생** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="84dad-129">**원격 오디오 녹음** 에서 **녹음 안 함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="84dad-130">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="84dad-131">**작업 환경** 탭을 클릭합니다. **성능** 아래에서 **지속적인 비트맵 캐싱** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="84dad-132">일반 **탭을** 클릭합니다. 컴퓨터에서 가상 데스크톱의 이름을 입력하고 연결 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84dad-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="84dad-133">가상 데스크톱에서 로그인 및 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="84dad-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="84dad-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="84dad-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="84dad-135">Lync VDI 플러그 인을 사용하도록 설정한 후 사용자는 가상 데스크톱에서 비즈니스용 Skype에 로그인할 때 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="84dad-136">사용자는 가상 데스크톱에서 실행되는 비즈니스용 Skype 클라이언트에 자신의 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="84dad-137">비즈니스용 Skype에서 Lync VDI 플러그 인을 검색하면 비즈니스용 Skype에서 사용자에게 자격 증명을 다시 입력하라는 메시지를 사용자에게 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="84dad-138">이 대화 상자에서는 사용자가 이후 로그인할 때 자격 증명을 입력할 필요가 없도록 **암호 저장** 확인란을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="84dad-139">비즈니스용 Skype가 Lync VDI 플러그 인과의 페어링을 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="84dad-140">이 경우 클라이언트는 비즈니스용 Skype 상태 표시줄에 두 개의 아이콘을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="84dad-141">왼쪽 아래 아이콘은 사용할 수 있는 오디오 장치가 없음을 나타내고, 오른쪽 아래에서 깜박이는 아이콘은 VDI 페어링이 진행 중임: a를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="84dad-142">VDI 페어링이 성공하면 아이콘이 변경하여 통화에 사용할 오디오 장치와 VDI 페어링 성공을 나타냅니다. b.</span><span class="sxs-lookup"><span data-stu-id="84dad-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="84dad-143">이제 사용자는 로컬 컴퓨터에 연결된 비즈니스용 Skype 호환 장치에서 자신의 현재 정보를 보고 평소처럼 통화를 걸고 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="84dad-144">Lync VDI 플러그 인 문제 해결</span><span class="sxs-lookup"><span data-stu-id="84dad-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="84dad-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="84dad-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="84dad-146">Lync VDI 플러그 인을 설치한 후 문제가 발생하는 경우 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84dad-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="84dad-147">Lync VDI 플러그 인 설치 문제</span><span class="sxs-lookup"><span data-stu-id="84dad-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="84dad-148">Lync VDI 플러그 인 설치에 문제가 있는 경우 다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="84dad-149">TEMP 및 TMP 시스템 변수에 지정한 폴더에 충분한 공간이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="84dad-150">쓰기 금지가 해제되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="84dad-151">지침은 장치 제조업체 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84dad-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="84dad-152">페어링 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="84dad-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="84dad-153">Lync VDI 플러그 인 페어링이 실패하면 오른쪽 아래에서 페어링 아이콘이 다음과 같이 빨간색 "X"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="84dad-154">다음은 오류의 가능한 이유와 문제를 해결하기 위해 수행할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="84dad-155">**사용자가 로그인 중에 잘못된 자격 증명을 입력함**</span><span class="sxs-lookup"><span data-stu-id="84dad-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="84dad-156">사용자는 비즈니스용 Skype에서 로그아웃하고 올바른 자격 증명으로 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="84dad-157">그러면 페어링 대화 상자가 다시 나타나고 페어링 성공 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="84dad-158">**다른 원격 데스크톱 클라이언트 인스턴스가 실행되고 있음**</span><span class="sxs-lookup"><span data-stu-id="84dad-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="84dad-159">Windows에서 원격 데스크톱 연결을 사용하는 경우 사용자는 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="84dad-160">**Alt+Ctrl+Delete** 를 누르고 **작업 관리자 시작** 을 클릭하여 작업 관리자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="84dad-161">**프로세스** 탭을 클릭하고 목록에서 이름이 **mstsc.exe** 인 모든 프로세스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="84dad-162">각 **mstsc.exe** 프로세스를 강조 표시하고 **프로세스 끝내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="84dad-163">새 원격 데스크톱 세션을 시작하고 다시 연결해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="84dad-164">**필요한 파일이 올바르게 설치되지 않음**</span><span class="sxs-lookup"><span data-stu-id="84dad-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="84dad-165">플러그 인이 로컬 컴퓨터에 설치된 후 이러한 파일이 C:\Program Files\Microsoft Office\Office15(또는 적절한 드라이브 문자) 아래에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="84dad-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="84dad-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="84dad-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="84dad-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="84dad-168">**비즈니스용 Skype 클라이언트가 로컬 컴퓨터에서 실행되고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="84dad-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="84dad-169">Lync VDI 플러그 인을 사용하려면 비즈니스용 Skype 클라이언트가 로컬 컴퓨터에서 실행되고 있지 않으면 페어링이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="84dad-170">로컬 컴퓨터에 비즈니스용 Skype 클라이언트를 설치하지 않는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84dad-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="84dad-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84dad-171">See also</span></span>
<span data-ttu-id="84dad-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="84dad-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="84dad-173">VDI 환경의 비즈니스용 Skype 계획</span><span class="sxs-lookup"><span data-stu-id="84dad-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
