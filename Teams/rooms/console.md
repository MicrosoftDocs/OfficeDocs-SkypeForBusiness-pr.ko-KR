---
title: Microsoft Teams 룸 콘솔 구성
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 이 문서에서는 Microsoft 팀 회의실 콘솔과 주변 장치를 설정 하 고 구성 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: d5c1b7f47769d925f6d67527429971970b555044
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905450"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="24b44-103">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="24b44-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="24b44-104">이 문서에서는 Microsoft 팀 회의실 콘솔과 주변 장치를 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="24b44-105">[Microsoft 팀 대화방 배포](rooms-deploy.md)에 설명 된 대로 필요한 microsoft 팀 또는 비즈니스용 Skype 및 Exchange 계정이 이미 만들어지고 테스트 된 경우에만이 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="24b44-106">[Microsoft 팀 회의실 요구 사항](requirements.md)에 설명 된 하드웨어 및 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="24b44-107">이 항목에서는 다음 섹션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="24b44-108">설치 미디어 준비</span><span class="sxs-lookup"><span data-stu-id="24b44-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="24b44-109">콘솔에 개인 CA 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="24b44-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="24b44-110">Windows 10 및 Microsoft 팀 대화방 콘솔 앱 설치</span><span class="sxs-lookup"><span data-stu-id="24b44-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="24b44-111">콘솔의 초기 설정</span><span class="sxs-lookup"><span data-stu-id="24b44-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="24b44-112">Microsoft 팀 대화방 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="24b44-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="24b44-113">Microsoft 팀 대화방은 [microsoft 팀 대화방 배포](rooms-deploy.md)에 설명 된 대로 디바이스 계정이 올바르게 설정 된 microsoft 팀 또는 비즈니스용 Skype 환경 에서만 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="24b44-114">설치 미디어 준비</span><span class="sxs-lookup"><span data-stu-id="24b44-114">Prepare the installation media</span></span>
<span data-ttu-id="24b44-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="24b44-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="24b44-116">Microsoft 팀 공간 콘솔 앱을 설치 하려면 최소한 32GB의 용량을 갖춘 USB 저장 장치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="24b44-117">장치에 다른 파일이 없어야 합니다. USB 저장소의 기존 파일이 모두 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24b44-118">이러한 지침에 따라 Microsoft 팀 회의실 설치 미디어를 만들지 못하면 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="24b44-119">아래 프로세스는 새 Microsoft 팀 공간 장치를 이미지 하기 위해 설치 미디어를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="24b44-120">기존 장치는 기본적으로 Windows Update 및 Windows 스토어에서 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24b44-121">Microsoft 팀 대화방 설치 미디어를 만드는 데 사용 되는 Windows 10 컴퓨터는 대상 설치 미디어로 Windows의 동일한 버전 또는 최신 버전 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="24b44-122">[CreateSrsMedia 스크립트](https://go.microsoft.com/fwlink/?linkid=867842)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="24b44-123">Windows 10 컴퓨터의 관리자 권한 프롬프트에서 CreateSrsMedia 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="24b44-124">스크립트의 지침에 따라 Microsoft 팀 대화방 USB 설치 디스크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="24b44-125">CreateSrsMedia 스크립트가 시작 될 때마다 화면 출력에는 세션에 대 한 로그 파일의 이름 또는 기록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="24b44-126">스크립트를 실행 하는 데 문제가 있는 경우 지원을 요청할 때 해당 기록의 복사본을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="24b44-127">CreateSrsMedia 스크립트는 다음 작업을 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="24b44-128">Microsoft 팀 대화방의 최신 MSI 설치 관리자를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="24b44-129">사용자가 제공 해야 하는 Windows의 빌드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="24b44-130">가장 최근에 릴리스된 버전이 Microsoft 팀 회의실 장치에서 사용 하도록 테스트 및 지원 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="24b44-131">필요한 지원 구성 요소를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="24b44-132">필요한 구성 요소를 설치 미디어에 어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="24b44-133">특정 버전의 Windows 10이 필요 하며,이 버전은 볼륨 라이선스 고객만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="24b44-134">[볼륨 라이선싱 서비스 센터](https://www.microsoft.com/Licensing/servicecenter/)에서 복사본을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="24b44-135">완료 되 면 컴퓨터에서 USB 디스크를 제거 하 고 [Windows 10 및 Microsoft 팀 대화방 콘솔 앱](console.md#Reimage)을 계속 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="24b44-136">Windows 10 및 Microsoft 팀 대화방 콘솔 앱 설치</span><span class="sxs-lookup"><span data-stu-id="24b44-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="24b44-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="24b44-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="24b44-138">지금 만든 설치 미디어를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="24b44-139">대상 장치가 기기로 실행 되 고 기본 사용자는 Microsoft 팀 대화방 콘솔 앱만 실행 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="24b44-140">대상 장치가 dock에 설치 되는 경우 (예: Surface Pro) dock에서 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="24b44-141">대상 장치가 네트워크에 연결 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="24b44-142">대상 장치가 AC 전원에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="24b44-143">USB 설치 디스크를 대상 장치에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="24b44-144">USB 설치 디스크로 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="24b44-145">제조업체 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24b44-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="24b44-146">대상 장치가 Surface Pro 인 경우 다음 단계를 사용 하 여 USB 설정 디스크로 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="24b44-147">a.</span><span class="sxs-lookup"><span data-stu-id="24b44-147">a.</span></span> <span data-ttu-id="24b44-148">볼륨 작게 (-) 단추를 길게 눌러 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="24b44-149">b.</span><span class="sxs-lookup"><span data-stu-id="24b44-149">b.</span></span> <span data-ttu-id="24b44-150">전원 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-150">Press and release the power button.</span></span>

    <span data-ttu-id="24b44-151">c.</span><span class="sxs-lookup"><span data-stu-id="24b44-151">c.</span></span> <span data-ttu-id="24b44-152">Windows 설치 프로그램이 부팅 되 면 볼륨 작게 (-) 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="24b44-153">설치가 완료 되 면 시스템이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="24b44-154">시스템이 종료 된 후에는 USB 설치 디스크를 제거 하는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="24b44-155">이 시점에서 대상 디바이스를 dock에 배치 (dock 기반 제품을 사용 하는 경우) 하 고 회의실에 필요한 주변 장치를 연결한 다음 네트워크에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="24b44-156">제조업체 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24b44-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="24b44-157">Microsoft 팀 대화방의 소프트웨어 업데이트는 비즈니스용 Microsoft Store에서 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="24b44-158">[Microsoft Store 비즈니스 에디션 및 학력에 대 한 필수 구성 요소](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 를 참조 하 여 채팅방 콘솔에서 스토어 및 자동 업데이트에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-158">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="24b44-159">언어 선택</span><span class="sxs-lookup"><span data-stu-id="24b44-159">Selecting a language</span></span> 

<span data-ttu-id="24b44-160">만든이의 업데이트에서 암시적 언어 선택이 사용자에 게 원하는 실제 응용 프로그램 언어를 제공 하지 않는 시나리오의 ps1 스크립트 (예: 콘솔 앱이 프랑스어로 표시 되는 경우에는 영어로 표시 됨)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="24b44-161">다음 지침은 Windows Creator의 업데이트를 사용 하 여 만든 콘솔에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="24b44-162">미디어를 새 프로비저닝 시스템으로 설정 하지 않은 레거시/시장 시스템에서는 이러한 지침을 사용할 수 없지만,이 수동 작업을 수행 해야 하는 초기 문제 (예를 들어, 설치의 일부로 앱 언어를 명시적으로 선택할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="24b44-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="24b44-163">원하는 언어를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="24b44-163">To apply your desired language</span></span>

1. <span data-ttu-id="24b44-164">관리 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="24b44-165">시작 메뉴를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="24b44-166">기어 아이콘을 선택 하 여 **설정** 앱을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="24b44-167">**시간 &amp; 언어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="24b44-168">**지역 &amp; 언어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="24b44-169">**언어 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="24b44-170">추가 하고자 하는 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="24b44-171">"언어" 목록에 방금 추가한 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="24b44-172">**기본값으로 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="24b44-173">제거할 언어에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="24b44-174">a.</span><span class="sxs-lookup"><span data-stu-id="24b44-174">a.</span></span> <span data-ttu-id="24b44-175">제거 하고자 하는 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-175">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="24b44-176">b.</span><span class="sxs-lookup"><span data-stu-id="24b44-176">b.</span></span> <span data-ttu-id="24b44-177">**제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-177">Select **Remove**.</span></span>
    
11. <span data-ttu-id="24b44-178">관리자 권한 명령 프롬프트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="24b44-179">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="24b44-180">시스템을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-180">Restart the system.</span></span>
    
<span data-ttu-id="24b44-181">이제 Microsoft 팀 대화방 콘솔에 해당 언어가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="24b44-182">콘솔의 초기 설정</span><span class="sxs-lookup"><span data-stu-id="24b44-182">Initial set up of the console</span></span>
<span data-ttu-id="24b44-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="24b44-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="24b44-184">Windows가 설치 된 후에는 Microsoft 팀 대화방 콘솔 앱이 다음에 시작 될 때 또는/reboot 옵션이 선택 된 경우 초기 설정 프로세스로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="24b44-185">사용자 계정 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-185">The User Account screen appears.</span></span> <span data-ttu-id="24b44-186">콘솔과 함께 사용할 룸 계정의 Skype 로그인 주소 (user@domain 형식으로)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="24b44-187">채팅방 계정에 대 한 암호를 입력 하 고 다시 입력 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="24b44-188">"도메인 구성"에서 비즈니스용 Skype 서버용 FQDN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="24b44-189">비즈니스용 Skype SIP 도메인이 사용자의 Exchange 도메인과 다른 경우이 필드에 Exchange 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="24b44-190">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="24b44-191">기능 화면에서 표시 된 장치를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="24b44-192">기본적으로 자동 화면 공유를 On으로 설정 하 고 모임 이름 숨기기를 해제로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="24b44-193">선택할 장치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="24b44-194">회의 마이크:이 회의실에 대 한 기본 마이크입니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="24b44-195">회의 스피커: 컨퍼런스 기본 스피커</span><span class="sxs-lookup"><span data-stu-id="24b44-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="24b44-196">기본 스피커: HDMI 수집에서 오디오에 사용 되는 스피커입니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="24b44-197">각 항목에는 선택할 수 있는 옵션의 드롭다운 메뉴가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-197">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="24b44-198">각 장치에 대 한 항목을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-198">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="24b44-199">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-199">Click **Finish**.</span></span>
    
<span data-ttu-id="24b44-200">Microsoft 팀 대화방 콘솔 앱은 바로 위의 자격 증명으로 비즈니스용 Skype Server에 로그인을 시작 하 고 동일한 자격 증명을 사용 하 여 Exchange와 일정을 동기화 하기 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="24b44-201">콘솔 앱을 사용 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 대화방 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24b44-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="24b44-202">Microsoft 팀 대화방은 인증 된 콘솔 하드웨어의 존재 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="24b44-203">Microsoft 팀 공간 콘솔 앱을 포함 하는 올바르게 만든 이미지도 콘솔 하드웨어가 검색 되지 않는 한 초기 설정 절차를 지 나 부팅 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="24b44-204">Surface Pro 기반 솔루션의 경우 Surface Pro는 함께 제공 된 dock 하드웨어에 연결 해야만이 검사를 통과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24b44-205">일부 영어가 아닌 사용자는 터치 키보드에서 기호가 지원 되지 않는 경우 초기 설정 시 콘솔에 연결 된 실제 키보드가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="24b44-206">콘솔에 개인 CA 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="24b44-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="24b44-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="24b44-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="24b44-208">Microsoft 팀 대화방 콘솔은 연결 하는 서버에서 사용 하는 인증서를 신뢰 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="24b44-209">O365의 경우이는 해당 서버가 공개 인증 기관을 사용 하 고 있으며 Windows 10에서 자동으로 신뢰 되기 때문에 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="24b44-210">Active Directory와 Windows 인증 기관과의 온-프레미스 배포와 같은 인증 기관이 비공개 인 경우 다음과 같은 두 가지 방법으로 인증서를 Microsoft 팀 공간 콘솔에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="24b44-211">Active Directory에 콘솔을 가입 하 고 인증 기관이 Active Directory에 게시 되 면 (일반 배포 옵션) 필요한 인증서가 자동으로 추가 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="24b44-212">이미징 프로세스가 완료 되 면 수동으로 인증서를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="24b44-213">이 작업을 수행 하기 전에 먼저 [콘솔 설정을](console.md#Initial)완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="24b44-214">수동으로 인증서를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="24b44-214">To manually install the certificate</span></span>

1. <span data-ttu-id="24b44-215">CA 인증서를 컴퓨터에 다운로드 하 고 "C:\Skype 채팅방 Systems\x64\Scripts\Provisioning\CAcertificate.cer"에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="24b44-216">콘솔을 관리 모드 ( [관리자 모드 및 장치 관리](rooms-operations.md#AdminMode)참조)로 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="24b44-217">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="24b44-218">Active Directory 도메인에 가입 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="24b44-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="24b44-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="24b44-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="24b44-220">Microsoft 팀 대화방 콘솔을 도메인에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="24b44-221">많은 워크스테이션 정책이 Microsoft 팀 대화방과 호환 되지 않으므로 microsoft 팀 공간 콘솔을 PC 워크스테이션과 별도의 OU에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="24b44-222">일반적인 예는 Microsoft 팀 대화방을 자동으로 시작 하는 것을 방지 하는 암호 적용 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="24b44-223">GPO 설정 관리에 대 한 자세한 내용은 [Microsoft 팀 대화방 관리](rooms-operations.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24b44-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="24b44-224">도메인에 Microsoft 팀 대화방에 참가 하려면</span><span class="sxs-lookup"><span data-stu-id="24b44-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="24b44-225">관리자 계정으로 콘솔에 로그인 합니다 ( [관리자 모드 및 장치 관리](rooms-operations.md#AdminMode)참조).</span><span class="sxs-lookup"><span data-stu-id="24b44-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="24b44-226">관리자 권한 Powershell 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="24b44-227">Powershell에 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="24b44-228">예를 들어 정규화 된 도메인이 redmond.corp.microsoft.com Microsoft 팀 대화방 콘솔이 "Resources" OU의 자식인 "Microsoft 팀 대화방" OU에 있어야 하는 경우 명령은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="24b44-229">도메인에 참가할 때 컴퓨터의 이름을 바꾸려면-NewName 플래그를 사용 하 고 컴퓨터의 새 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="24b44-230">Microsoft 팀 대화방 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="24b44-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="24b44-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="24b44-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="24b44-232">콘솔 및 모든 주변 기기가 완전히 구성 되었음을 최종 확인 하는 동안 다음 검사 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="24b44-233">**응용 프로그램 설정**</span><span class="sxs-lookup"><span data-stu-id="24b44-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24b44-234">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-234">☐</span></span>  <br/> |<span data-ttu-id="24b44-235">콘솔 화면의 오른쪽 위에 대화방 계정 이름 및 전화 번호 (PSTN 사용)가 올바르게 표시 됨</span><span class="sxs-lookup"><span data-stu-id="24b44-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="24b44-236">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-236">☐</span></span>  <br/> |<span data-ttu-id="24b44-237">Windows 컴퓨터 이름이 올바르게 설정 되어 있습니다 (원격 관리에 유용).</span><span class="sxs-lookup"><span data-stu-id="24b44-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="24b44-238">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-238">☐</span></span>  <br/> |<span data-ttu-id="24b44-239">Administrator 계정 비밀 번호 설정 및 확인 됨</span><span class="sxs-lookup"><span data-stu-id="24b44-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="24b44-240">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-240">☐</span></span>  <br/> |<span data-ttu-id="24b44-241">모든 펌웨어 업데이트가 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="24b44-242">**오디오/비디오 주변 장치**</span><span class="sxs-lookup"><span data-stu-id="24b44-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24b44-243">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-243">☐</span></span>  <br/> |<span data-ttu-id="24b44-244">카메라 주변 기기 펌웨어 버전이 올바릅니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="24b44-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="24b44-245">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-245">☐</span></span>  <br/> |<span data-ttu-id="24b44-246">카메라 작동 및 위치 최적화</span><span class="sxs-lookup"><span data-stu-id="24b44-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="24b44-247">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-247">☐</span></span>  <br/> |<span data-ttu-id="24b44-248">기본 장치 및 재생에 대 한 설정을 원하는 오디오 주변 장치에 설정 하는 기본 통신 디바이스</span><span class="sxs-lookup"><span data-stu-id="24b44-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="24b44-249">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-249">☐</span></span>  <br/> |<span data-ttu-id="24b44-250">원하는 오디오 주변 기기에 설정 된 기본 통신 디바이스의 기록 설정</span><span class="sxs-lookup"><span data-stu-id="24b44-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="24b44-251">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-251">☐</span></span>  <br/> |<span data-ttu-id="24b44-252">오디오 주변 기기 펌웨어 버전이 올바릅니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="24b44-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="24b44-253">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-253">☐</span></span>  <br/> |<span data-ttu-id="24b44-254">오디오 입력 디바이스 작동 및 최적 위치</span><span class="sxs-lookup"><span data-stu-id="24b44-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="24b44-255">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-255">☐</span></span>  <br/> |<span data-ttu-id="24b44-256">오디오 출력 디바이스 작동 및 최적 위치</span><span class="sxs-lookup"><span data-stu-id="24b44-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="24b44-257">**입력판**</span><span class="sxs-lookup"><span data-stu-id="24b44-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24b44-258">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-258">☐</span></span>  <br/> |<span data-ttu-id="24b44-259">케이블이 안전 하 고 pinched 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="24b44-260">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-260">☐</span></span>  <br/> |<span data-ttu-id="24b44-261">HDMI를 통한 오디오 수집 기능이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="24b44-262">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-262">☐</span></span>  <br/> |<span data-ttu-id="24b44-263">HDMI를 통해 비디오 수집 기능이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b44-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="24b44-264">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-264">☐</span></span>  <br/> |<span data-ttu-id="24b44-265">자유롭게 항구 회전 가능</span><span class="sxs-lookup"><span data-stu-id="24b44-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="24b44-266">☐</span><span class="sxs-lookup"><span data-stu-id="24b44-266">☐</span></span>  <br/> |<span data-ttu-id="24b44-267">환경에 대해 디스플레이 밝기가 허용 됨</span><span class="sxs-lookup"><span data-stu-id="24b44-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="24b44-268">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24b44-268">See also</span></span>
<span data-ttu-id="24b44-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="24b44-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="24b44-270">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="24b44-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="24b44-271">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="24b44-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="24b44-272">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="24b44-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="24b44-273">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="24b44-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
