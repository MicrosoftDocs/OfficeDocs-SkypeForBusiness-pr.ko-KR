---
title: Microsoft Teams 회의실 장치를 수동으로 업데이트
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Microsoft Teams 회의실 장치를 특정 버전으로 수동으로 업데이트하는 방법을 배워야 합니다.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731400"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="d3477-103">Microsoft Teams 회의실 장치를 수동으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="d3477-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="d3477-104">Microsoft Teams 회의실 앱은 Microsoft Store를 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="d3477-105">앱에 대한 업데이트는 야간 유지 관리 중에 Microsoft Store에서 자동으로 설치됩니다. 이 방법은 업데이트를 다운로드하는 데 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="d3477-106">그러나 Teams 회의실 장치에서 Microsoft Store에서 업데이트를 받을 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="d3477-107">예를 들어 보안 정책은 디바이스가 인터넷에 연결하도록 허용하지 않을 수 있습니다. 또는 Microsoft Store에서 앱을 다운로드하도록 허용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="d3477-108">또는 Microsoft Store를 사용할 수 없는 설정을 수행하기 전에 디바이스를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="d3477-109">Microsoft Store에서 업데이트를 받을 수 없는 경우 오프라인 앱 업데이트 PowerShell 스크립트를 사용하여 Teams 회의실 장치를 최신 버전의 Teams 회의실 앱으로 수동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="d3477-110">이 문서의 단계에 따라 Teams 회의실 장치를 수동으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="d3477-111">이 프로세스는 Teams 회의실 앱이 이미 설치되어 있는 Teams 회의실 디바이스만 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="d3477-112">새 설치를 수행하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="d3477-113">또한 앱을 이전 버전으로 다운그레이드하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="d3477-114">Teams Rooms 앱의 새 설치를 수행하려면 장치 제조업체에 해당 미디어에 문의하거나 설치 미디어 [준비를 참조하세요.](console.md#prepare-the-installation-media)</span><span class="sxs-lookup"><span data-stu-id="d3477-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="d3477-115">1단계: 오프라인 앱 업데이트 스크립트 다운로드</span><span class="sxs-lookup"><span data-stu-id="d3477-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="d3477-116">먼저 최신 버전의 오프라인 앱 업데이트 스크립트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="d3477-117">스크립트를 다운로드하려면 <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="d3477-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="d3477-118">스크립트는 디바이스의 기본 다운로드 폴더에 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="d3477-119">다운로드한 파일은 Windows에서 차단된 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="d3477-120">상호 작용 없이 스크립트를 실행해야 하는 경우 스크립트 차단을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="d3477-121">스크립트 차단을 해제하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="d3477-122">파일 탐색기에서 파일을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="d3477-123">속성 **클릭**</span><span class="sxs-lookup"><span data-stu-id="d3477-123">Click **Properties**</span></span>
3. <span data-ttu-id="d3477-124">차단 **해제 선택**</span><span class="sxs-lookup"><span data-stu-id="d3477-124">Select **Unblock**</span></span>
4. <span data-ttu-id="d3477-125">확인 **클릭**</span><span class="sxs-lookup"><span data-stu-id="d3477-125">Click **OK**</span></span>

<span data-ttu-id="d3477-126">PowerShell을 사용하여 스크립트 차단을 해제하는 경우 차단 [해제 파일을 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)</span><span class="sxs-lookup"><span data-stu-id="d3477-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="d3477-127">오프라인 앱 업데이트 스크립트를 다운로드한 후 파일을 Teams 회의실 장치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="d3477-128">USB 드라이브를 사용하여 또는 디바이스의 관리 모드에 있는 동안 네트워크 파일 공유에서 파일에 액세스하여 디바이스로 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="d3477-129">디바이스에 파일을 저장하는 위치를 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="d3477-130">2단계: 스크립트를 실행하여 Teams 회의실 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="d3477-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="d3477-131">Skype 사용자(앱이 실행되는 사용자)가 여전히 로그인하는 동안 상승된 명령 프롬프트에서 오프라인 앱 업데이트 스크립트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="d3477-132">Skype 사용자가 여전히 로그인하는 동안 관리자 계정에 로그인하여 관리자 권한 명령 프롬프트를 사용하는 방법에 대한 자세한 내용은 [Microsoft Teams](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)회의실 앱이 실행 중일 때 관리자 모드로 전환을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3477-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="d3477-133">다음을 실행하여 상승된 명령 프롬프트에서 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="d3477-134">관리 모드로 전환</span><span class="sxs-lookup"><span data-stu-id="d3477-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="d3477-135">시작 아이콘을 클릭하고 명령 **프롬프트를** 입력한 다음 관리자 **권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3477-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="d3477-136">스크립트의 전체 경로와 스크립트 파일의 이름을 포함하는 다음 `<path to script>` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="d3477-137">예를 들어 스크립트 파일이 있는 경우 스크립트 파일 이름이 있는 경우 `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="d3477-138">스크립트를 실행할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-138">Allow the script to run.</span></span> <span data-ttu-id="d3477-139">완료되면 스크립트가 Teams 회의실 디바이스를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="d3477-140">원격 PowerShell을 사용하여 스크립트를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="d3477-141">Teams 회의실 장치에서 원격 PowerShell을 사용하는 자세한 내용은 [PowerShell을](rooms-operations.md#remote-management-using-powershell)사용하여 원격 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3477-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="d3477-142">3단계: 앱이 성공적으로 업데이트되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d3477-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="d3477-143">스크립트가 성공적으로 실행되는 경우 디바이스가 Teams 회의실 앱으로 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="d3477-144">스크립트에 문제가 발생하면 명령줄에 문제가 있는 것을 나타내고 해당 출력을 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="d3477-145">스크립트에서 제공하는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="d3477-146">Microsoft 지원에 문의해야 하는 경우 지원 요청과 함께 로그 파일을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="d3477-147">스크립트는 로그 파일에 대한 경로를 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3477-147">The script will provide you with the path to the log file.</span></span>
