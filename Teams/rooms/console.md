---
title: Microsoft Teams 룸 콘솔 구성
ms.author: dstrome
author: dstrome
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
description: 이 문서에서는 콘솔 및 주변 장치를 설정하고 Microsoft Teams 룸 방법을 설명합니다.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117576"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="8cdeb-103">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="8cdeb-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="8cdeb-104">이 문서에서는 콘솔 및 주변 장치를 Microsoft Teams 룸 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="8cdeb-105">필요한 계정 또는 Microsoft Teams 비즈니스용 Skype Exchange 배포 에서 설명한 [Microsoft Teams 룸.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="8cdeb-106">요구 사항에 설명된 하드웨어 [및 Microsoft Teams 룸 필요합니다.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="8cdeb-107">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="8cdeb-108">설치 미디어 준비</span><span class="sxs-lookup"><span data-stu-id="8cdeb-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="8cdeb-109">본체에 개인 CA 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="8cdeb-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="8cdeb-110">Windows 10 및 Microsoft Teams 룸 앱 설치</span><span class="sxs-lookup"><span data-stu-id="8cdeb-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="8cdeb-111">콘솔의 초기 설정</span><span class="sxs-lookup"><span data-stu-id="8cdeb-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="8cdeb-112">Microsoft Teams 룸 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="8cdeb-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="8cdeb-113">Microsoft Teams 룸 디바이스 계정이 배포 에서 설명한 Microsoft Teams 비즈니스용 Skype 올바르게 설정되는 환경에서만 제대로 구성된 [Microsoft Teams 룸.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="8cdeb-114">설치 미디어 준비</span><span class="sxs-lookup"><span data-stu-id="8cdeb-114">Prepare the installation media</span></span>
<span data-ttu-id="8cdeb-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="8cdeb-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="8cdeb-116">콘솔 Microsoft Teams 룸 설치하려면 용량이 32GB 이상인 USB 저장소 디바이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="8cdeb-117">디바이스에 다른 파일이 없습니다. USB 저장소의 기존 파일이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cdeb-118">이러한 지침에 Microsoft Teams 룸 설치 미디어를 만들지 못하면 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="8cdeb-119">아래 프로세스는 새 디바이스를 이미지하는 설치 미디어를 Microsoft Teams 룸 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="8cdeb-120">기존 디바이스는 기본적으로 업데이트 및 Windows 저장소에서 Windows 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cdeb-121">Windows 10 설치 미디어를 만드는 데 Microsoft Teams 룸 컴퓨터는 대상 설치 미디어와 동일한 Windows 버전에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="8cdeb-122">스크립트를 [CreateSrsMedia.ps1 다운로드합니다.](https://go.microsoft.com/fwlink/?linkid=867842)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="8cdeb-123">CreateSrsMedia.ps1 컴퓨터의 상승된 프롬프트에서 Windows 10 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="8cdeb-124">스크립트의 지침에 따라 USB Microsoft Teams 룸 디스크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="8cdeb-125">스크립트가 CreateSrsMedia.ps1 시작할 때마다 화면 출력에는 세션에 대한 로그 파일 또는 전사 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="8cdeb-126">스크립트를 실행하는 데 문제가 있는 경우 지원을 요청할 때 해당 녹취록의 복사본을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="8cdeb-127">CreateSrsMedia.ps1 스크립트는 다음 작업을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="8cdeb-128">최신 MSI 설치 관리자를 다운로드하여 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="8cdeb-129">사용자가 제공해야 하는 Windows 빌드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="8cdeb-130">가장 최근에 릴리스된 버전은 디바이스와 함께 사용하기 위해 테스트되거나 지원되지 않을 Microsoft Teams 룸 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="8cdeb-131">필요한 지원 구성 요소를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="8cdeb-132">설치 미디어에서 필요한 구성 요소를 조립합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="8cdeb-133">특정 버전의 Windows 10 필요하며, 이 버전은 볼륨 라이선스 고객에게만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="8cdeb-134">볼륨 라이선스 서비스 센터에서 [복사본을 얻을 수 있습니다.](https://www.microsoft.com/Licensing/servicecenter/)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="8cdeb-135">완료되면 컴퓨터에서 USB 디스크를 제거하고 Windows 10 콘솔 앱 Microsoft Teams 룸 [진행합니다.](console.md#Reimage)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="8cdeb-136">Windows 10 및 Microsoft Teams 룸 앱 설치</span><span class="sxs-lookup"><span data-stu-id="8cdeb-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="8cdeb-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="8cdeb-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="8cdeb-138">이제 만든 설정 미디어를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="8cdeb-139">대상 디바이스는 어플라이언스로 실행됩니다. 기본 사용자는 콘솔 앱만 Microsoft Teams 룸 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="8cdeb-140">대상 디바이스가 dock에 설치되는 경우(예: Surface Pro) dock에서 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="8cdeb-141">대상 디바이스가 네트워크에 연결되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="8cdeb-142">대상 디바이스가 AC 전원에 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="8cdeb-143">USB 설정 디스크를 대상 디바이스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="8cdeb-144">USB 설정 디스크로 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="8cdeb-145">제조업체 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="8cdeb-146">대상 디바이스가 Surface Pro 경우 다음 단계를 사용하여 USB 설정 디스크로 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="8cdeb-147">a.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-147">a.</span></span> <span data-ttu-id="8cdeb-148">누를 때 볼륨을 계속 누르고(-) 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="8cdeb-149">b.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-149">b.</span></span> <span data-ttu-id="8cdeb-150">전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-150">Press and release the power button.</span></span>

    <span data-ttu-id="8cdeb-151">c.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-151">c.</span></span> <span data-ttu-id="8cdeb-152">설치 Windows 부팅하면 볼륨 다운(-) 단추를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="8cdeb-153">설치가 완료되면 시스템이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="8cdeb-154">시스템이 종료된 후 USB 설정 디스크를 제거하는 것이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="8cdeb-155">이 시점에서 대상 디바이스를 해당 dock에 두고(dock 기반 제품을 사용하는 경우), 회의실에 필요한 주변 장치를 연결하고 네트워크에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="8cdeb-156">제조업체 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="8cdeb-157">소프트웨어 업데이트는 Microsoft Teams 룸 자동으로 다운로드 비즈니스용 Microsoft Store됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="8cdeb-158">룸 [콘솔이](/microsoft-store/prerequisites-microsoft-store-for-business) 저장소 및 자체 업데이트에 액세스할 수 비즈니스용 Microsoft Store 확인을 위해 교육 및 교육에 대한 전제 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-158">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="8cdeb-159">언어 선택</span><span class="sxs-lookup"><span data-stu-id="8cdeb-159">Selecting a language</span></span> 

<span data-ttu-id="8cdeb-160">크리에이터의 업데이트에서는 암시적 언어 선택이 사용자에게 원하는 실제 애플리케이션 언어를 제공하지 않는 시나리오에서 ApplyCurrentRegionAndLanguage.ps1 스크립트를 사용해야 합니다(예: 콘솔 앱이 프랑스어로 제공되지만 영어로 제공됩니다).</span><span class="sxs-lookup"><span data-stu-id="8cdeb-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cdeb-161">다음 지침은 크리에이터의 업데이트를 사용하여 만든 콘솔에만 Windows 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="8cdeb-162">새 프로비전 시스템과 함께 미디어를 사용하여 설정되지 않은 레거시/인-마켓 시스템은 이러한 지침을 사용할 수 없지만 이 수동 개입이 필요한 초기 문제로 고통을 겪지 않습니다(주년 버전에서는 설정의 일부로 앱 언어를 명시적으로 선택할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="8cdeb-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="8cdeb-163">원하는 언어를 적용하기 위해</span><span class="sxs-lookup"><span data-stu-id="8cdeb-163">To apply your desired language</span></span>

1. <span data-ttu-id="8cdeb-164">관리자 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="8cdeb-165">시작 메뉴를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="8cdeb-166">기어 아이콘을 선택하여  설정 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="8cdeb-167">시간 **언어를 &amp; 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="8cdeb-168">지역 **언어를 &amp; 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="8cdeb-169">언어 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="8cdeb-170">추가할 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="8cdeb-171">방금 "언어" 목록에 추가한 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="8cdeb-172">기본값으로 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="8cdeb-173">제거하고자 하는 언어의 경우:</span><span class="sxs-lookup"><span data-stu-id="8cdeb-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="8cdeb-174">a.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-174">a.</span></span> <span data-ttu-id="8cdeb-175">제거할 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-175">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="8cdeb-176">b.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-176">b.</span></span> <span data-ttu-id="8cdeb-177">제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-177">Select **Remove**.</span></span>
    
11. <span data-ttu-id="8cdeb-178">상승된 명령 프롬프트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="8cdeb-179">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="8cdeb-180">시스템을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-180">Restart the system.</span></span>
    
<span data-ttu-id="8cdeb-181">이제 원하는 언어가 콘솔에 Microsoft Teams 룸 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="8cdeb-182">콘솔의 초기 설정</span><span class="sxs-lookup"><span data-stu-id="8cdeb-182">Initial set up of the console</span></span>
<span data-ttu-id="8cdeb-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="8cdeb-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="8cdeb-184">Windows 설치한 후 Microsoft Teams 룸 콘솔 앱이 다음에 시작되거나 /reboot 옵션을 선택한 경우 초기 설치 프로세스로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="8cdeb-185">사용자 계정 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-185">The User Account screen appears.</span></span> <span data-ttu-id="8cdeb-186">본체와 Skype 사용할 user@domain 로그인 주소(user@domain 형식)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="8cdeb-187">룸 계정에 대한 암호를 입력하고 다시 입력하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="8cdeb-188">"도메인 구성"에서 도메인에 대한 FQDN을 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="8cdeb-189">SIP 비즈니스용 Skype 사용자의 Exchange 도메인과 다른 경우 이 Exchange 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="8cdeb-190">다음 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="8cdeb-191">기능 화면에서 표시된 디바이스를 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="8cdeb-192">기본값은 자동 화면 공유를 설정하고 모임 이름을 끄기 및 숨기기로 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="8cdeb-193">선택할 디바이스는 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="8cdeb-194">회의용 마이크: 이 회의실의 기본 마이크입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="8cdeb-195">회의용 발표자: 회의의 기본 스피커입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="8cdeb-196">기본 스피커: HDMI 인제스트의 오디오에 사용되는 스피커입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="8cdeb-197">각 항목에는 선택할 옵션의 드롭다운 메뉴가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-197">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="8cdeb-198">각 디바이스에 대해 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-198">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="8cdeb-199">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-199">Click **Finish**.</span></span>
    
<span data-ttu-id="8cdeb-200">Microsoft Teams 룸 콘솔 앱은 위에서 입력한 자격 증명으로 비즈니스용 Skype 서버 즉시 로그인을 시작해야 합니다. 또한 동일한 자격 증명을 사용하여 일정을 Exchange 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="8cdeb-201">콘솔 앱 사용에 대한 자세한 내용은 Microsoft Teams 룸 [참조하세요.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8cdeb-202">Microsoft Teams 룸 콘솔 하드웨어의 존재에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="8cdeb-203">콘솔 앱이 Microsoft Teams 룸 올바르게 만든 이미지라도 콘솔 하드웨어가 검색되지 않는 한 초기 설정 절차를 따라 부팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="8cdeb-204">Surface Pro 솔루션의 경우 이 Surface Pro 확인을 전달하려면 해당 Surface Pro Dock 하드웨어에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cdeb-205">영어가 아닌 일부 사용자는 터치 키보드에서 기호가 지원되지 않는 경우 초기 설정 중에 본체에 연결된 물리적 키보드가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="8cdeb-206">본체에 개인 CA 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="8cdeb-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="8cdeb-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="8cdeb-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="8cdeb-208">Microsoft Teams 룸 콘솔은 연결되는 서버에서 사용하는 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="8cdeb-209">O365의 경우 이러한 서버가 공용 인증서 기관을 사용하고 있으며 이러한 서버는 자동으로 신뢰할 수 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="8cdeb-210">인증서 기관이 비공개인 경우(예: Active Directory 및 Windows 인증 기관을 사용하여 프레미스 배포) 몇 가지 방법으로 인증서를 Microsoft Teams 룸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="8cdeb-211">콘솔을 Active Directory에 조인할 수 있으며 인증서 기관이 Active Directory에 게시된 경우 필요한 인증서를 자동으로 추가합니다(일반 배포 옵션).</span><span class="sxs-lookup"><span data-stu-id="8cdeb-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="8cdeb-212">이미징 프로세스 후에 인증서를 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="8cdeb-213">이렇게 하기 전에 콘솔의 초기 설정 [을 완료해야 합니다.](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="8cdeb-214">인증서를 수동으로 설치하려면</span><span class="sxs-lookup"><span data-stu-id="8cdeb-214">To manually install the certificate</span></span>

1. <span data-ttu-id="8cdeb-215">컴퓨터에 CA 인증서를 다운로드하고 "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="8cdeb-216">콘솔을 관리 모드로 [전환합니다(관리자 모드 및 디바이스 관리 참조).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="8cdeb-217">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="8cdeb-218">Active Directory 도메인 가입(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="8cdeb-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="8cdeb-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="8cdeb-220">도메인에 Microsoft Teams 룸 콘솔에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="8cdeb-221">Microsoft Teams 룸 많은 workstation 정책이 사용자와 호환되지 않는 경우 PC 작업대와 별도의 OU에 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="8cdeb-222">일반적인 예로 암호 적용 정책이 Microsoft Teams 룸 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="8cdeb-223">GPO 설정 관리에 대한 자세한 내용은 관리 를 [Microsoft Teams 룸.](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="8cdeb-224">도메인에 Microsoft Teams 룸 참가하려면</span><span class="sxs-lookup"><span data-stu-id="8cdeb-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="8cdeb-225">관리자 계정에서 본체에 로그인합니다(관리자 [모드 및 디바이스 관리 참조).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="8cdeb-226">Powershell 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="8cdeb-227">Powershell에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="8cdeb-228">예를 들어 자격이 redmond.corp.microsoft.com 도메인이 Microsoft Teams 룸 "리소스" OU의 자식인 "Microsoft Teams 룸" OU에 있는 경우 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="8cdeb-229">도메인에 조인할 때 컴퓨터의 이름을 변경하려면 -NewName 플래그와 컴퓨터의 새 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="8cdeb-230">Microsoft Teams 룸 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="8cdeb-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="8cdeb-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="8cdeb-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="8cdeb-232">본체와 모든 주변 장치를 완전히 구성하는지 최종 확인하는 동안 다음 검사 목록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="8cdeb-233">**애플리케이션 설정**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8cdeb-234">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-234">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-235">룸 계정 이름 및 휴대폰 #(PSTN을 사용하도록 설정한 경우) 콘솔 화면 오른쪽 위에 올바르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="8cdeb-236">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-236">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-237">Windows 이름이 올바르게 설정되어 있습니다(원격 관리에 유용)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="8cdeb-238">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-238">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-239">관리자 계정 암호 설정 및 확인</span><span class="sxs-lookup"><span data-stu-id="8cdeb-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="8cdeb-240">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-240">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-241">모든 펌웨어 업데이트가 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="8cdeb-242">**오디오/비디오 주변 장치**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8cdeb-243">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-243">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-244">카메라 주변 펌웨어 버전이 올바른 경우(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="8cdeb-245">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-245">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-246">카메라 기능 및 최적 위치</span><span class="sxs-lookup"><span data-stu-id="8cdeb-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="8cdeb-247">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-247">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-248">설정 기본 디바이스 및 재생 기본 통신 디바이스에 대해 의도된 오디오 주변 장치로 설정</span><span class="sxs-lookup"><span data-stu-id="8cdeb-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="8cdeb-249">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-249">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-250">설정 기본 통신 디바이스를 의도된 오디오 주변 장치로 설정하기 위한 기본 설정</span><span class="sxs-lookup"><span data-stu-id="8cdeb-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="8cdeb-251">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-251">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-252">오디오 주변 펌웨어 버전이 올바른 경우(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="8cdeb-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="8cdeb-253">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-253">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-254">오디오 입력 디바이스 기능 및 최적 위치</span><span class="sxs-lookup"><span data-stu-id="8cdeb-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="8cdeb-255">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-255">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-256">오디오 출력 디바이스 기능 및 최적 위치</span><span class="sxs-lookup"><span data-stu-id="8cdeb-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="8cdeb-257">**Dock**</span><span class="sxs-lookup"><span data-stu-id="8cdeb-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8cdeb-258">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-258">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-259">케이블이 안전하며 고정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="8cdeb-260">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-260">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-261">HDMI를 통해 오디오 인제스트가 작동</span><span class="sxs-lookup"><span data-stu-id="8cdeb-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="8cdeb-262">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-262">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-263">HDMI를 통해 비디오 인제스트가 작동</span><span class="sxs-lookup"><span data-stu-id="8cdeb-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="8cdeb-264">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-264">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-265">Dock은 자유롭게 스위브할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="8cdeb-266">☐</span><span class="sxs-lookup"><span data-stu-id="8cdeb-266">☐</span></span>  <br/> |<span data-ttu-id="8cdeb-267">디스플레이 밝기는 환경에 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdeb-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8cdeb-268">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cdeb-268">See also</span></span>
<span data-ttu-id="8cdeb-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="8cdeb-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="8cdeb-270">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="8cdeb-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="8cdeb-271">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="8cdeb-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="8cdeb-272">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="8cdeb-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="8cdeb-273">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="8cdeb-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)