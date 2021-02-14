---
title: Microsoft Teams 회의실 복구 도구 사용
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 최신 시스템을 지원되는 상태로 가져오는 데 사용하는 Microsoft Teams 회의실에 대한 복구 도구를 사용하는 방법을 논의합니다.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021726"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="70584-103">Microsoft Teams 회의실 복구 도구 사용</span><span class="sxs-lookup"><span data-stu-id="70584-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="70584-104">이 문서에서는 최신 시스템을 지원되는 상태로 가져오는 데 사용하는 Microsoft Teams 회의실에 대한 복구 도구를 사용하는 방법을 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="70584-105">이 도구는 Microsoft Teams 회의실 콘솔에 "시스템 구성이 최신이 아닙니다." 오류가 표시되거나 푸시 단추 초기화 팩터리 복원을 수행하기 전에 [적용해야 합니다.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="70584-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70584-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="70584-106">Prerequisites</span></span>

<span data-ttu-id="70584-107">최신 [Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) 설치 패키지를 다운로드하여 Microsoft Teams 회의실 장치에 액세스할 수 있는 USB 메모리 스틱 또는 네트워크 공유에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="70584-108">MSI에서 파일을 추출하는 것은 여러 가지 수단으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70584-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="70584-109">모든 파일을 추출하고 해당 디렉터리 구조를 보존하는 모든 메커니즘은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70584-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="70584-110">이러한 한 가지 방법은 Microsoft Teams Room 설치 패키지의 전체 경로를 나타내고 추출할 파일을 원하는 폴더의 전체 경로를 나타내는 명령을 사용하는 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70584-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="70584-111">도구 실행</span><span class="sxs-lookup"><span data-stu-id="70584-111">Running the tool</span></span>

1) <span data-ttu-id="70584-112">Microsoft Teams Rooms 장치에서 관리자 계정에 로그인하고 관리자 권한 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="70584-113">Microsoft Teams Rooms 설치 패키지에서 추출한 파일에 포함된 파일에 액세스할 수 있는지 Microsoft Teams 회의실 장치에서 `RecoveryTool.ps1 file` 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="70584-114">키트는 전제 구성을 준비할 때 사용되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70584-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="70584-115">`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="70584-116">팩터리 복원을 수행하기 위해:</span><span class="sxs-lookup"><span data-stu-id="70584-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="70584-117">스크립트에서 메시지가 표시되면 옵션 2: **재설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70584-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="70584-118">BitLocker가 설정되어 있는 경우 스크립트 출력의 끝에 제공된 지침에 따라 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="70584-119">팩터리 복원을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="70584-120">설정 **앱을 열고** 보안 업데이트 **& 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70584-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="70584-121">복구 **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="70584-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="70584-122">이 **PC 재설정 아래에서** **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70584-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="70584-123">모두 **제거,** **다음** 및 다시 설정 **선택**</span><span class="sxs-lookup"><span data-stu-id="70584-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="70584-124">내 파일 유지 **-** 앱 및 설정을 제거하지만 Windows 재설정 프로세스 중에 개인 파일 옵션이 선택된 경우 Microsoft Teams 회의실 장치를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70584-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="70584-125">이 옵션을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70584-125">Do not select this option.</span></span>
      5. <span data-ttu-id="70584-126">시스템이 여러 번 다시부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="70584-126">The system will reboot multiple times.</span></span> <span data-ttu-id="70584-127">다시 설정이 완료되면 시스템이 Windows "기본 환경"(OOBE) 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70584-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="70584-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70584-128">See also</span></span>

[<span data-ttu-id="70584-129">Microsoft Teams 회의실 도움말</span><span class="sxs-lookup"><span data-stu-id="70584-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="70584-130">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="70584-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
