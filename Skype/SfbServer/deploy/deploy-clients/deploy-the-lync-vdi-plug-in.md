---
title: 비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용 하기 위한 배포 절차에 대해 설명 합니다.
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191142"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="26a87-103">비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포</span><span class="sxs-lookup"><span data-stu-id="26a87-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="26a87-104">이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용 하기 위한 배포 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="26a87-105">계획 고려 사항은 [VDI 환경의 비즈니스용 Skype 계획](../../plan-your-deployment/clients-and-devices/vdi-environments.md)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="26a87-106">VDI (가상 데스크톱 인프라) 환경은 보안 및 준수 문제가 특히 중요 한 일부 조직에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="26a87-107">해당 사용자는 로컬 Windows 컴퓨터에 있고 가상 데스크톱에서 클라이언트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="26a87-108">추가 VDI 플러그 인 소프트웨어가 필요한 것과 같은 연결에 비즈니스용 Skype를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="26a87-109">VDI 플러그 인 구성 요소에는 Microsoft에서 제공 하는 두 가지 솔루션과 Citrix에서 제공 하는 둘 중 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="26a87-110">Microsoft는 새 배포에서 새 HDX 실시간 최적화 팩 솔루션을 사용 하는 것이 좋지만 나머지 수명 주기 동안 원본 Lync VDI 플러그 인을 계속 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="26a87-111">이 항목에서는 Windows 7 및 Windows 8 또는 Windows Server 2008 에서만 지원 되며 Lync 2013 또는 비즈니스용 Skype 클라이언트만을 지 원하는 Microsoft Lync VDI 플러그 인을 배포 하는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="26a87-112">이 플러그 인을 업데이트할 계획이 없지만 비즈니스용 Skype에 대 한 [CITRIX HDX 실시간 최적화 팩](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) 이 필요에 따라 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="26a87-113">Lync VDI 플러그 인을 위한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="26a87-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="26a87-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="26a87-114"></span></span>

1. <span data-ttu-id="26a87-115">비즈니스용 Skype 서버에서 모든 Lync VDI 플러그 인 사용자에 대해 EnableMediaRedirection이 TRUE로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="26a87-116">자세한 내용은 [새 csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) Cmdlet 및 [Set csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26a87-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="26a87-117">데이터 센터 서버에서 모든 가상 데스크톱에 비즈니스용 Skype 클라이언트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="26a87-118">로컬 컴퓨터에서 Lync VDI 플러그 인을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="26a87-119">이제 사용자는 헤드셋 또는 웹캠 같은 장치를 로컬 컴퓨터에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="26a87-120">원격 데스크톱 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="26a87-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="26a87-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="26a87-121"></span></span>

<span data-ttu-id="26a87-122">Lync VDI 플러그 인에 대 한 원격 데스크톱 연결을 준비 하려면 로컬 컴퓨터에서 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="26a87-123">로컬 컴퓨터에서 Windows 8을 실행 하는 경우에는이 단계를 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="26a87-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="26a87-124">로컬 컴퓨터에서 SP1을 사용 하 여 Windows 7을 실행 하는 경우 최신 Windows 8 버전의 [원격 데스크톱 서비스 클라이언트](https://go.microsoft.com/fwlink/p/?LinkId=268032)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="26a87-125">**시작**을 클릭 한 다음 **원격 데스크톱 연결**을 클릭 하 여 원격 데스크톱 서비스 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="26a87-126">**옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="26a87-127">**로컬 리소스** 탭을 클릭 합니다. **원격 오디오**에서 **설정을**클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="26a87-128">**원격 오디오 재생**에서 **이 컴퓨터에서 재생**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="26a87-129">**원격 오디오 기록**에서 **녹화 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="26a87-130">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="26a87-131">**환경** 탭을 클릭 합니다. **성능**에서 **영구적 비트맵 캐싱** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="26a87-132">**일반** 탭을 클릭 합니다. **컴퓨터**에서 가상 데스크톱의 이름을 입력 한 다음 **연결**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="26a87-133">가상 데스크톱에서 비즈니스용 Skype에 로그인 및 사용</span><span class="sxs-lookup"><span data-stu-id="26a87-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="26a87-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="26a87-134"></span></span>

<span data-ttu-id="26a87-135">Lync VDI 플러그 인을 사용 하도록 설정한 후 사용자는 가상 데스크톱에서 비즈니스용 Skype에 로그인 할 때 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="26a87-136">사용자는 가상 데스크톱에서 실행 되는 비즈니스용 Skype 클라이언트에 자신의 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="26a87-137">비즈니스용 Skype에서 Lync VDI 플러그 인을 감지 하면 비즈니스용 Skype에서 사용자에 게 자격 증명을 다시 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="26a87-138">이 대화 상자에서 사용자가 다음에 로그인 할 때 자격 증명을 입력할 필요가 없도록 **암호 저장** 확인란을 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="26a87-139">비즈니스용 Skype는 Lync VDI 플러그 인과 페어링 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="26a87-140">이 문제가 발생 하는 동안에는 클라이언트가 비즈니스용 Skype 상태 표시줄에 두 개의 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="26a87-141">왼쪽 아래에 있는 아이콘은 사용할 수 있는 오디오 장치가 없음을 나타내고 오른쪽 아래에 깜박이는 아이콘은 VDI 페어링이 진행 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="26a87-142">VDI 페어링에 성공한 후에는이 아이콘이 변경 되어 통화에 사용 되는 오디오 장치 및 성공한 VDI 페어링에는 b가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="26a87-143">이제 사용자는 로컬 컴퓨터에 연결 된 비즈니스용 Skype 호환 장치에서 현재 상태를 볼 수 있으며 평소와 같이 전화를 걸고 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="26a87-144">Lync VDI 플러그 인 문제 해결</span><span class="sxs-lookup"><span data-stu-id="26a87-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="26a87-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="26a87-145"></span></span>

<span data-ttu-id="26a87-146">Lync VDI 플러그 인을 설치한 후 문제가 발생 하는 경우 다음 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26a87-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="26a87-147">Lync VDI 플러그 인 설치 문제</span><span class="sxs-lookup"><span data-stu-id="26a87-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="26a87-148">Lync VDI 플러그 인을 설치 하는 데 문제가 있는 경우 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="26a87-149">TEMP 및 TMP 시스템 변수에 지정한 폴더에 충분 한 공간이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="26a87-150">쓰기 방지가 꺼져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="26a87-151">자세한 내용은 장치 제조업체의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26a87-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="26a87-152">페어링 문제 해결</span><span class="sxs-lookup"><span data-stu-id="26a87-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="26a87-153">Lync VDI 플러그 인 페어링에 실패 하면 오른쪽 아래에 있는 페어링 아이콘은 표시 된 대로 빨간색 "X"로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="26a87-154">오류 및 문제를 해결 하기 위해 수행할 수 있는 작업에 대 한 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="26a87-155">**로그인 하는 동안 사용자가 잘못 된 자격 증명을 입력 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="26a87-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="26a87-156">사용자는 비즈니스용 Skype에서 로그 아웃 하 고 올바른 자격 증명으로 다시 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="26a87-157">페어링 대화 상자가 다시 표시 되 고 페어링이 성공할 수 있는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="26a87-158">**원격 데스크톱 클라이언트의 다른 인스턴스가 실행 중입니다.**</span><span class="sxs-lookup"><span data-stu-id="26a87-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="26a87-159">Windows에서 원격 데스크톱 연결을 사용 하는 경우 사용자는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="26a87-160">작업 관리자 시작: **Alt + Ctrl + Delete**를 누른 다음 **작업 관리자 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="26a87-161">**프로세스** 탭을 클릭 하 고 목록에서 **mstsc** 라는 모든 프로세스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="26a87-162">각 **mstsc** 프로세스를 강조 표시 한 다음 **프로세스 끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="26a87-163">새 원격 데스크톱 세션을 시작 하 고 다시 연결 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="26a87-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="26a87-164">**필요한 파일이 올바르게 설치 되지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="26a87-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="26a87-165">로컬 컴퓨터에 플러그 인을 설치한 후 이러한 파일이 C:\Program Files\Microsoft Office\Office15 (또는 적절 한 드라이브 문자) 아래에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="26a87-166">LyncVdiPlugin</span><span class="sxs-lookup"><span data-stu-id="26a87-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="26a87-167">(Vdi) dll</span><span class="sxs-lookup"><span data-stu-id="26a87-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="26a87-168">**비즈니스용 Skype 클라이언트가 로컬 컴퓨터에서 실행 되 고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="26a87-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="26a87-169">Lync VDI 플러그 인을 사용 하려면 비즈니스용 Skype 클라이언트가 로컬 컴퓨터에서 실행 되 고 있지 않아야 하 고, 그렇지 않으면 페어링이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="26a87-170">가장 좋은 방법은 사용자가 로컬 컴퓨터에 비즈니스용 Skype 클라이언트를 설치 하지 않아야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26a87-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="26a87-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26a87-171">See also</span></span>
<span data-ttu-id="26a87-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="26a87-172"></span></span>

[<span data-ttu-id="26a87-173">VDI 환경에서 비즈니스용 Skype에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="26a87-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
