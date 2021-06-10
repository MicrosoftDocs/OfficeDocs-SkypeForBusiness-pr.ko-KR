---
title: 복구 Microsoft Teams 룸 사용
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
description: 이 문서에서는 최신 시스템을 지원되는 상태로 Microsoft Teams 룸 복구 도구를 사용하는 방법을 설명합니다.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117496"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="23ed5-103">복구 Microsoft Teams 룸 사용</span><span class="sxs-lookup"><span data-stu-id="23ed5-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="23ed5-104">이 문서에서는 최신 시스템을 지원되는 상태로 Microsoft Teams 룸 복구 도구를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="23ed5-105">이 도구는 Microsoft Teams 룸 "시스템 구성" 오류가 표시되거나 푸시 단추 재설정 팩터리 복원을 수행하기 전에 를 표시하는 경우 [적용해야 합니다.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="23ed5-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23ed5-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="23ed5-106">Prerequisites</span></span>

<span data-ttu-id="23ed5-107">최신 설치 [Microsoft Teams 룸](https://go.microsoft.com/fwlink/?linkid=851168) 패키지를 다운로드하고 USB 메모리 스틱 또는 네트워크 공유에 Microsoft Teams 룸 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="23ed5-108">MSI에서 파일을 추출하는 것은 여러 가지 수단으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="23ed5-109">모든 파일을 추출하고 디렉터리 구조를 보존하는 모든 메커니즘은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="23ed5-110">이러한 한 가지 방법은 룸 설치 패키지에 대한 전체 경로를 Microsoft Teams 파일을 추출할 폴더의 전체 경로를 나타내는 명령을 사용하는 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="23ed5-111">도구 실행</span><span class="sxs-lookup"><span data-stu-id="23ed5-111">Running the tool</span></span>

1) <span data-ttu-id="23ed5-112">디바이스의 관리자 계정에 Microsoft Teams 룸 상승된 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="23ed5-113">설치 패키지에서 Microsoft Teams 룸 파일에 포함된 에 액세스할 수 있는지 Microsoft Teams 룸 `RecoveryTool.ps1 file` 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="23ed5-114">키트는 전제 구성을 준비할 때 사용되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="23ed5-115">`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="23ed5-116">팩터리 복원을 수행하기 위해:</span><span class="sxs-lookup"><span data-stu-id="23ed5-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="23ed5-117">스크립트가 묻는 메시지가 표시되면 옵션 2: **재설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23ed5-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="23ed5-118">BitLocker 설정되어 있는 경우 스크립트 출력의 끝에 제공된 지침을 따라 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="23ed5-119">팩터리 복원을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="23ed5-120">설정 **앱을** 열고 보안 업데이트 **& 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23ed5-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="23ed5-121">복구 **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="23ed5-122">이 **PC 재설정 아래에서** **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23ed5-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="23ed5-123">모든 **제거**, 다음 및 **재설정을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23ed5-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="23ed5-124">내 Microsoft Teams 룸 유지 **-** 앱 및 설정을 제거하지만 개인 파일 옵션이 다시 설정 프로세스 중에 선택되어 있는 경우 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="23ed5-125">이 옵션을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-125">Do not select this option.</span></span>
      5. <span data-ttu-id="23ed5-126">시스템이 여러 번 다시 부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-126">The system will reboot multiple times.</span></span> <span data-ttu-id="23ed5-127">재설정이 완료되면 시스템은 "OOBE(Windows 경험 부족) 화면이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23ed5-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="23ed5-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23ed5-128">See also</span></span>

[<span data-ttu-id="23ed5-129">Microsoft Teams 룸 도움말</span><span class="sxs-lookup"><span data-stu-id="23ed5-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="23ed5-130">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="23ed5-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)