---
title: 팀 업데이트
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 팀 데스크톱 클라이언트가 업데이트 되는 방법에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fe542c6df89946ad73f14cf9104f973e292aa3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243845"
---
# <a name="teams-update-process"></a><span data-ttu-id="a9568-103">팀 업데이트 프로세스</span><span class="sxs-lookup"><span data-stu-id="a9568-103">Teams update process</span></span>

<span data-ttu-id="a9568-104">팀 웹 앱이 매주 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="a9568-105">팀 데스크톱 클라이언트 업데이트는 기술 채택 프로그램을 통해 엄격 하 게 내부 테스트 및 유효성 검사 후 2 주 마다 릴리스됩니다 (탭).</span><span class="sxs-lookup"><span data-stu-id="a9568-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="a9568-106">이는 일반적으로 화요일에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="a9568-107">중요 업데이트가 필요한 경우 팀은이 일정을 무시 하 고 업데이트가 제공 되는 즉시이를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="a9568-108">데스크톱 클라이언트가 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="a9568-109">팀은 백그라운드에서 몇 시간 마다 업데이트를 확인 하 고 다운로드 한 다음 업데이트를 자동으로 설치 하기 전에 컴퓨터가 유휴 상태가 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="a9568-110">또한 사용자는 앱 오른쪽 상단의 **프로필** 드롭다운 메뉴에서 **업데이트 확인** 을 클릭 하 여 수동으로 업데이트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="a9568-111">업데이트를 사용할 수 있는 경우 컴퓨터가 유휴 상태일 때 다운로드 되 고 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="a9568-112">사용자에 게 업데이트를 다운로드 하려면 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="a9568-113">7 월 9 일부터 2019, 팀 클라이언트 업데이트는 업데이트 중에 훨씬 낮은 네트워크 대역폭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="a9568-114">이 기능은 기본적으로 설정 되어 있으며 관리자 또는 사용자의 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="a9568-115">Office 365 ProPlus 업데이트에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a9568-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="a9568-116">팀은 [office 365 proplus를 사용 하 여 Microsoft 팀 배포](https://docs.microsoft.com/DeployOffice/teams-install)에 설명 된 대로 Office 365 ProPlus의 새 설치와 함께 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="a9568-117">팀은 위에 설명 된 대로 자체 업데이트 프로세스를 수행 하 고 Word 및 Excel과 같은 다른 Office 앱에 대 한 업데이트 프로세스를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="a9568-118">자세한 내용은 [Office 365 ProPlus의 업데이트 채널에 대 한 개요](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) 를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="a9568-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="a9568-119">VDI에서 팀을 업데이트 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="a9568-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="a9568-120">VDI (가상 데스크톱 인프라)의 팀 클라이언트는 비 VDI 팀 클라이언트의 방식으로 자동 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="a9568-121">[VDI에 팀을 설치](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)하는 지침에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="a9568-122">최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="a9568-123">관리자가 팀 자동 업데이트 대신 업데이트를 배포할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a9568-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="a9568-124">팀은 모든 배달 메커니즘을 통해 관리자에 게 업데이트를 배포 하는 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9568-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
