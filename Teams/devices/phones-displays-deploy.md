---
title: Intune을 사용 하 여 팀 전화 및 팀의 배포 표시
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 이 문서에서는 Microsoft 팀이 표시 하는 기능에 대 한 개요를 제공 합니다.
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787639"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="b203f-103">Intune을 사용 하 여 팀 전화 및 팀의 배포 표시</span><span class="sxs-lookup"><span data-stu-id="b203f-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="b203f-104">이 문서에서는 Intune을 사용 하 여 팀 전화 및 팀 표시를 배포 하는 방법에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="b203f-105">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="b203f-105">Conditional Access</span></span>

<span data-ttu-id="b203f-106">조건부 액세스는 Office 365 리소스에 액세스 하는 디바이스가 제대로 관리 되 고 안전한 지 확인 하는 데 도움이 되는 azure Active Directory (Azure AD) 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="b203f-107">팀 서비스에 조건부 액세스 정책을 적용 하는 경우, Android 장치 (팀 전화, 팀 표시 포함)가 Intune에 등록 되어야 하 고 해당 설정이 정책을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="b203f-108">장치가 Intune에 등록 되지 않은 경우 또는 해당 설정이 정책에 맞지 않는 경우에는 조건부 액세스를 통해 사용자가 디바이스에서 팀 앱에 로그인 하거나 해당 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="b203f-109">일반적으로 Intune 내에서 정의 된 규정 준수 정책은 사용자 그룹에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="b203f-110">즉, Android 준수 정책을 user@contoso.com에 할당 하면 해당 정책은 Android smartphone 및 user@contoso.com 로그인 하는 모든 Android 기반 팀 장치에 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="b203f-111">사용자의 조직에 Intune 등록이 적용 되어야 하는 조건부 액세스를 사용 하는 경우에는 성공적으로 Intune을 등록할 수 있도록 설정 해야 하는 몇 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="b203f-112">**Intune 라이선스** 팀 장치에 로그인 하는 사용자에 게 Intune 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="b203f-113">팀 장치가 유효한 Intune 라이선스가 있는 사용자 계정에 로그인 한 경우 로그인 프로세스의 일부로 장치가 Microsoft Intune에 자동으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="b203f-114">**Intune 구성** Android 장치 관리자 등록에 대해 올바르게 구성 된 Intune 테 넌 트가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="b203f-115">Intune에서 팀으로 등록 Android 기반 장치 구성</span><span class="sxs-lookup"><span data-stu-id="b203f-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="b203f-116">팀 Android 기반 장치는 DA (Android 장치 관리자) 관리를 통해 Intune에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="b203f-117">Intune에 장치를 등록할 수 있으려면 먼저 몇 가지 기본 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="b203f-118">현재 Intune을 사용 하 여 이미 장치를 관리 하 고 있는 경우 이러한 모든 작업을 이미 수행 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="b203f-119">그렇지 않은 경우 수행할 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="b203f-120">Intune MDM (모바일 디바이스 관리) 인증 기관 설정.</span><span class="sxs-lookup"><span data-stu-id="b203f-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="b203f-121">아직 Intune을 사용 하지 않은 경우 디바이스를 등록 하기 전에 MDM 기관을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="b203f-122">자세한 내용은 [모바일 장치 관리 기관 설정을](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b203f-122">For more information, see [Set the mobile device management authority](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="b203f-123">이것은 새 Intune 테 넌 트를 만들 때 수행 해야 하는 일회성 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="b203f-124">Android 장치 관리자 등록을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="b203f-125">Android 기반 팀 디바이스는 Intune을 사용 하 여 디바이스 관리자 장치로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="b203f-126">새로 만든 테 넌 트에 대 한 장치 관리자 등록은 기본적으로 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="b203f-127">자세한 내용은 [Android 장치 관리자 등록](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b203f-127">For more information, see [Android device administrator enrollment](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="b203f-128">사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-128">Assign licenses to users.</span></span> <span data-ttu-id="b203f-129">Intune을 등록 하는 팀 디바이스의 사용자에 게 유효한 Intune 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="b203f-130">자세한 내용은 [Intune에서 장치를 등록할 수 있도록 사용자에 게 라이선스 할당](https://docs.microsoft.com/intune/fundamentals/licenses-assign)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b203f-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="b203f-131">장치 관리자 준수 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="b203f-132">Android 장치 관리자 준수 정책을 만들고 팀 디바이스에 로그인 할 사용자가 포함 된 Azure Active Directory 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203f-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="b203f-133">자세한 내용은 [준수 정책을 사용 하 여 Intune을 사용 하 여 관리 하는 장치에 대 한 규칙 설정](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b203f-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="b203f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b203f-134">See also</span></span>

[<span data-ttu-id="b203f-135">Teams용 전화</span><span class="sxs-lookup"><span data-stu-id="b203f-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="b203f-136">Microsoft 팀에 대해 인증 된 IP 전화</span><span class="sxs-lookup"><span data-stu-id="b203f-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="b203f-137">팀 표시</span><span class="sxs-lookup"><span data-stu-id="b203f-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="b203f-138">Teams에서 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="b203f-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="b203f-139">팀 마켓플레이스</span><span class="sxs-lookup"><span data-stu-id="b203f-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)
