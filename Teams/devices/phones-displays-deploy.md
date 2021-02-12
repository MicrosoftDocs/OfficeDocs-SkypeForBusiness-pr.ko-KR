---
title: Intune을 사용하여 Teams 휴대폰 및 Teams 디스플레이 배포
ms.author: v-cichur
author: cichur
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
description: 이 문서에서는 Microsoft Teams 디스플레이에서 지원하는 기능에 대한 개요를 제공합니다.
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825418"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="46f8b-103">Intune을 사용하여 Teams 휴대폰 및 Teams 디스플레이 배포</span><span class="sxs-lookup"><span data-stu-id="46f8b-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="46f8b-104">이 문서에서는 Intune을 사용하여 Teams 휴대폰 및 Teams 디스플레이를 배포하는 방법에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="46f8b-105">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="46f8b-105">Conditional Access</span></span>

<span data-ttu-id="46f8b-106">조건부 액세스는 Office 365 리소스에 액세스하는 디바이스가 제대로 관리되고 안전하도록 하는 데 도움이 되는 Azure AD(Azure Active Directory) 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="46f8b-107">Teams 서비스에 조건부 액세스 정책을 적용하는 경우 Teams에 액세스하는 Android 장치(Teams 휴대폰 및 Teams 디스플레이 포함)를 Intune에 등록해야 합니다. 해당 설정은 정책을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="46f8b-108">디바이스가 Intune에 등록되지 않은 경우 또는 등록되어 있지만 해당 설정이 정책을 준수하지 않는 경우 조건부 액세스는 사용자가 디바이스에서 Teams 앱에 로그인하거나 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="46f8b-109">일반적으로 Intune 내에 정의된 규정 준수 정책은 사용자 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="46f8b-110">즉, Android 규정 준수 정책을 user@contoso.com 해당 정책은 Android 스마트폰 및 로그인하는 Android 기반 Teams user@contoso.com 동일하게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="46f8b-111">Intune 등록을 적용해야 하는 조건부 액세스를 사용하는 경우 조직에서 성공적인 Intune 등록을 허용하도록 설정해야 하는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="46f8b-112">**Intune 라이선스** Teams 장치에 로그인하는 사용자는 Intune에 대한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="46f8b-113">Teams 디바이스가 유효한 Intune 라이선스가 있는 사용자 계정에 로그인하는 한 디바이스는 로그인 프로세스의 일부로 Microsoft Intune에 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="46f8b-114">**Intune 구성** Android 디바이스 관리자 등록에 대해 올바르게 구성된 Intune 테넌트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="46f8b-115">Teams Android 기반 디바이스를 등록하도록 Intune 구성</span><span class="sxs-lookup"><span data-stu-id="46f8b-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="46f8b-116">Teams Android 기반 디바이스는 Android DA(장치 관리자) 관리를 통해 Intune에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="46f8b-117">디바이스를 Intune에 등록하기 전에 수행할 몇 가지 기본 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="46f8b-118">현재 Intune을 통해 디바이스를 이미 관리하고 있는 경우 이러한 모든 것을 이미 수행한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="46f8b-119">그렇지 않은 경우 다음 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="46f8b-120">Intune MDM(모바일 디바이스 관리) 기관을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="46f8b-121">Intune을 사용한 적이 없는 경우 디바이스를 등록하기 전에 MDM 기관을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="46f8b-122">자세한 내용은 모바일 디바이스 관리 [기관 설정 을 참조하세요.](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="46f8b-122">For more information, see [Set the mobile device management authority](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="46f8b-123">이 단계는 새 Intune 테넌트 만들기 시 수행해야 하는 일회성 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="46f8b-124">Android 디바이스 관리자 등록을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="46f8b-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="46f8b-125">Android 기반 Teams 디바이스는 Intune을 사용하여 디바이스 관리자 디바이스로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="46f8b-126">새로 만든 테넌트의 경우 디바이스 관리자 등록이 기본적으로 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="46f8b-127">자세한 내용은 Android 디바이스 관리자 [등록을 참조하세요.](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)</span><span class="sxs-lookup"><span data-stu-id="46f8b-127">For more information, see [Android device administrator enrollment](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="46f8b-128">사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-128">Assign licenses to users.</span></span> <span data-ttu-id="46f8b-129">Intune에 등록하는 Teams 디바이스 사용자에게 유효한 Intune 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="46f8b-130">자세한 내용은 Intune에서 디바이스를 등록할 수 있도록 사용자에게 라이선스 [할당을 참조하세요.](https://docs.microsoft.com/intune/fundamentals/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="46f8b-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="46f8b-131">디바이스 관리자 규정 준수 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="46f8b-132">Android 디바이스 관리자 규정 준수 정책을 만들고 Teams 디바이스에 로그인할 사용자를 포함하는 Azure Active Directory 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="46f8b-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="46f8b-133">자세한 내용은 규정 준수 정책을 사용하여 [Intune을](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)사용하여 관리하는 디바이스에 대한 규칙을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="46f8b-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="46f8b-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46f8b-134">See also</span></span>

[<span data-ttu-id="46f8b-135">Teams용 전화</span><span class="sxs-lookup"><span data-stu-id="46f8b-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="46f8b-136">Microsoft Teams에 대해 인증된 IP 전화기</span><span class="sxs-lookup"><span data-stu-id="46f8b-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="46f8b-137">Teams 표시</span><span class="sxs-lookup"><span data-stu-id="46f8b-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="46f8b-138">Teams에서 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="46f8b-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="46f8b-139">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="46f8b-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)
