---
title: 팀 업데이트
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft 팀 데스크톱 클라이언트를 업데이트 하는 프로세스에 대해 설명 합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8681f3f4cc7c25e9499e25e3978848084086a2a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031884"
---
# <a name="teams-update-process"></a><span data-ttu-id="c5d9f-103">팀 업데이트 프로세스</span><span class="sxs-lookup"><span data-stu-id="c5d9f-103">Teams update process</span></span>

<span data-ttu-id="c5d9f-104">팀 웹 앱이 매주 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="c5d9f-105">팀 데스크톱 클라이언트 업데이트는 기술 채택 프로그램을 통해 엄격 하 게 내부 테스트 및 유효성 검사 후 2 주 마다 릴리스됩니다 (탭).</span><span class="sxs-lookup"><span data-stu-id="c5d9f-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="c5d9f-106">이는 일반적으로 화요일에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="c5d9f-107">중요 업데이트가 필요한 경우 팀은이 일정을 무시 하 고 업데이트가 제공 되는 즉시이를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="c5d9f-108">데스크톱 클라이언트가 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="c5d9f-109">팀은 백그라운드에서 몇 시간 마다 업데이트를 확인 하 고 다운로드 한 다음 업데이트를 자동으로 설치 하기 전에 컴퓨터가 유휴 상태가 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="c5d9f-110">또한 사용자는 앱 오른쪽 상단의 **프로필** 드롭다운 메뉴에서 **업데이트 확인** 을 클릭 하 여 수동으로 업데이트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="c5d9f-111">업데이트를 사용할 수 있는 경우 컴퓨터가 유휴 상태일 때 다운로드 되 고 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="c5d9f-112">사용자에 게 업데이트를 다운로드 하려면 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="c5d9f-113">2019 년 7 월 31 일에 팀 클라이언트 업데이트는 업데이트 중 매우 낮은 네트워크 대역폭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-113">Starting July 31, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="c5d9f-114">이 기능은 기본적으로 설정 되어 있으며 관리자 또는 사용자의 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-114">This is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="c5d9f-115">엔터프라이즈 용 Microsoft 365 앱 업데이트에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c5d9f-115">What about updates to Microsoft 365 Apps for enterprise?</span></span>

<span data-ttu-id="c5d9f-116">Enterprise 용 microsoft [365 앱을 사용 하 여 Microsoft 팀 배포](https://docs.microsoft.com/DeployOffice/teams-install)에 설명 된 대로 Enterprise 용 Microsoft 365 앱을 새로 설치 하 여 팀이 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-116">Teams is installed by default with new installations of Microsoft 365 Apps for enterprise as described in [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="c5d9f-117">팀은 위에 설명 된 대로 자체 업데이트 프로세스를 수행 하 고 Word 및 Excel과 같은 다른 Office 앱에 대 한 업데이트 프로세스를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="c5d9f-118">자세한 내용은 [엔터프라이즈 용 Microsoft 365 앱 업데이트 채널에 대 한 개요](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) 를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-118">To learn more, read [Overview of update channels for Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="c5d9f-119">VDI에서 팀을 업데이트 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c5d9f-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="c5d9f-120">VDI (가상 데스크톱 인프라)의 팀 클라이언트는 비 VDI 팀 클라이언트의 방식으로 자동 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="c5d9f-121">[VDI에 팀을 설치](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)하는 지침에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="c5d9f-122">최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="c5d9f-123">관리자가 팀 자동 업데이트 대신 업데이트를 배포할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c5d9f-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="c5d9f-124">팀은 모든 배달 메커니즘을 통해 관리자에 게 업데이트를 배포 하는 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="c5d9f-125">서비스 계약</span><span class="sxs-lookup"><span data-stu-id="c5d9f-125">Servicing agreement</span></span>

<span data-ttu-id="c5d9f-126">최신 온라인 서비스인 팀 클라이언트는 2 주 마다 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-126">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="c5d9f-127">팀은 최신 수명 주기 정책에 따라 관리 되므로 사용자가 데스크톱 클라이언트의 최신 버전을 그대로 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-127">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="c5d9f-128">이렇게 하면 사용자에 게 최신 기능, 성능 향상, 보안 및 서비스 안정성이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-128">This ensures that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="c5d9f-129">데스크톱 클라이언트가 만료 되는 경우를 식별 하는 기능을 지원 하기 위해 사용자의 현재 버전이 1 개월 이상 이전이 고 사용할 수 있는 새 버전이 있으면 앱에서 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-129">To begin assisting in identifying when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="c5d9f-130">이 앱 내 메시지는 사용자가 최신 버전의 팀으로 업데이트 하거나 필요한 경우 IT 관리자에 게 연락 하 여이 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-130">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="c5d9f-131">3 개월 이상 지난 팀 데스크톱 클라이언트의 사용자에 게는 지금 업데이트 하는 옵션을 제공 하는 차단 페이지 (IT 관리자에 게 연락 하거나 웹의 팀으로 계속)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-131">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="c5d9f-132">팀의 첫 번째 설치 및/또는 최초 실행 시 3 개월 이상의 데스크톱 클라이언트 버전이 앞에서 언급 한 서비스 정보를 시작 하기 전에 28 일 유예 기간을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-132">Desktop client versions that are more than three months old upon first install and/or first run of Teams have a 28-day grace period before encountering the above-mentioned servicing information.</span></span> <span data-ttu-id="c5d9f-133">이 기간 동안에는 자동 업데이트 프로세스가 팀 클라이언트를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-133">During this period, the auto-update process will update the Teams client.</span></span> <span data-ttu-id="c5d9f-134">업데이트 하지 않은 경우 사용자는 앱에서 최신 버전을 수동으로 업데이트 하거나 필요한 경우 IT 관리자에 게 연락 하 여이에 대 한 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-134">If not updated, users will see an in-app alert encouraging them to manually update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="c5d9f-135">여기에는 enterprise 번들 용 Microsoft 365 앱의 일부로 팀 데스크톱 클라이언트를 사용 하는 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-135">This includes users using the Teams desktop client as part of the Microsoft 365 Apps for enterprise bundle.</span></span>

<span data-ttu-id="c5d9f-136">현재 정부 클라우드의 팀 데스크톱 클라이언트는 추가 공지에 도달할 때까지이 서비스 계약에 대 한 예외를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-136">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="c5d9f-137">새 버전 릴리스에 대 한 자세한 내용은 [메시지 센터](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) 를 확인 하거나 **Help**  >  클라이언트의 **새로운 기능** 에 대 한 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d9f-137">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
