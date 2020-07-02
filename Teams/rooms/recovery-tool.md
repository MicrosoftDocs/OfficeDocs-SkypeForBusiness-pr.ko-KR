---
title: Microsoft 팀 대화방 복구 도구 사용
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
description: 이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021726"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="0473a-103">Microsoft 팀 대화방 복구 도구 사용</span><span class="sxs-lookup"><span data-stu-id="0473a-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="0473a-104">이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="0473a-105">Microsoft 팀 대화방 콘솔에 "시스템 구성 날짜가 만료 됨" 오류가 표시 되거나 푸시 단추 다시 설정 [공장 복원을](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)수행 하기 전에이 도구를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0473a-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0473a-106">Prerequisites</span></span>

<span data-ttu-id="0473a-107">최신 [Microsoft 팀 대화방 설치 패키지](https://go.microsoft.com/fwlink/?linkid=851168) 를 다운로드 하 고 Microsoft 팀 회의실 장치에서 액세스할 수 있는 USB 메모리 스틱 또는 네트워크 공유에 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="0473a-108">MSI에서 파일의 압축을 푸는 것은 여러 방법에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="0473a-109">모든 파일을 추출 하 고 해당 디렉터리 구조를 유지 하는 메커니즘은 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="0473a-110">그 이유 중 하나는 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` Microsoft 팀 대화방 설치 패키지에 대 한 전체 경로를 나타내는 명령을 사용 하는 것이 고, `PathToTarget` 압축을 푼 파일을 원하는 폴더의 전체 경로를 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="0473a-111">도구 실행</span><span class="sxs-lookup"><span data-stu-id="0473a-111">Running the tool</span></span>

1) <span data-ttu-id="0473a-112">Microsoft 팀 대화방 장치에서 관리자 계정에 로그인 하 고 관리자 권한 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="0473a-113">Microsoft 팀 대화방 `RecoveryTool.ps1 file` 설치 패키지에서 추출 된 파일에 포함 된에 액세스할 수 있는 Microsoft 팀원 장치에서 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="0473a-114">이 키트는 필수 구성 요소를 준비할 때 사용 되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="0473a-115">실행 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="0473a-116">공장 복원을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="0473a-117">스크립트에 메시지가 표시 되 면 옵션 2: **Reset**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="0473a-118">BitLocker가 켜져 있는 경우 스크립트 출력 끝부분에 나와 있는 지침에 따라 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="0473a-119">공장 복원을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="0473a-120">**설정** 앱을 열고 **& 보안 업데이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="0473a-121">**복구** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="0473a-122">**이 PC 초기화**아래에서 **시작 하기** 선택</span><span class="sxs-lookup"><span data-stu-id="0473a-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="0473a-123">**모두 제거**를 선택한 다음 **다음** 을 선택 하 고 **다시 설정** 합니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="0473a-124">Microsoft 팀 공간 장치를 사용할 수 없게 되는 경우 **내 파일 유지-앱과 설정을 제거 하지만** Windows 재설정 프로세스 중에 개인 파일 옵션이 선택 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="0473a-125">이 옵션을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0473a-125">Do not select this option.</span></span>
      5. <span data-ttu-id="0473a-126">시스템이 여러 번 재부팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-126">The system will reboot multiple times.</span></span> <span data-ttu-id="0473a-127">재설정이 완료 되 면 시스템은 Windows "OOBE (of box)" 화면에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0473a-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="0473a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0473a-128">See also</span></span>

[<span data-ttu-id="0473a-129">Microsoft 팀 대화방 도움말</span><span class="sxs-lookup"><span data-stu-id="0473a-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="0473a-130">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="0473a-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
