---
title: Intune을 Teams 휴대폰 및 Teams 디스플레이 배포
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
description: 이 문서에서는 디스플레이에서 지원되는 기능과 Microsoft Teams 제공합니다.
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420823"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="04755-103">Intune을 Teams 휴대폰 및 Teams 디스플레이 배포</span><span class="sxs-lookup"><span data-stu-id="04755-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="04755-104">이 문서에서는 배포 방법에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="04755-105">Teams Intune을 사용하여 휴대폰 및 Teams 디스플레이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="04755-106">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="04755-106">Conditional Access</span></span>

<span data-ttu-id="04755-107">조건부 액세스는 azure AD(Azure Active Directory) 기능으로, 리소스에 액세스하는 디바이스가 Office 365 안전하게 관리되도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04755-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="04755-108">조건부 액세스 정책을 Teams 서비스에 적용하는 경우 액세스하는 Android 디바이스(Teams 휴대폰 및 Teams 디스플레이 포함)는 Intune에 등록해야 Teams 설정이 정책을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="04755-109">디바이스가 Intune에 등록되지 않은 경우 또는 등록되어 있지만 해당 설정이 정책을 준수하지 않는 경우 조건부 액세스는 사용자가 디바이스에서 앱에 로그인하거나 Teams 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="04755-110">일반적으로 Intune 내에 정의된 규정 준수 정책은 사용자 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="04755-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="04755-111">즉, Android 규정 준수 정책을 할당하는 user@contoso.com 해당 정책은 로그인하는 Android 스마트폰 및 Android 기반 Teams 디바이스에 user@contoso.com 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04755-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="04755-112">Intune 등록을 적용해야 하는 조건부 액세스를 사용하는 경우 조직에서 성공적인 Intune 등록을 허용하기 위해 설정해야 할 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04755-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="04755-113">**Intune 라이선스** 디바이스에 로그인하는 Teams Intune에 대한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="04755-114">디바이스가 Teams Intune 라이선스가 있는 사용자 계정에 로그인하는 한, 디바이스는 로그인 프로세스의 일부로 Microsoft Intune 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="04755-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="04755-115">**Intune 구성** Android 디바이스 관리자 등록을 위해 제대로 구성된 Intune 테넌트가 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="04755-116">Android 기반 디바이스에 Teams Intune 구성</span><span class="sxs-lookup"><span data-stu-id="04755-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="04755-117">Teams Android 기반 디바이스는 Android 디바이스 관리자(DA) 관리를 통해 Intune에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="04755-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="04755-118">디바이스를 Intune에 등록하기 전에 수행할 몇 가지 기본 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04755-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="04755-119">현재 Intune을 통해 디바이스를 관리하고 있는 경우 이러한 모든 일을 이미 수행한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04755-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="04755-120">그렇지 않은 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04755-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="04755-121">테넌트 관리자가 공용 영역 휴대폰을 Intune에 등록하려면 계정에 Intune 라이선스를 추가하고 Intune 등록 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="04755-122">디바이스에 로그인하는 데 Teams Intune에 대한 라이선스가 없는 경우 계정에 대해 Intune 준수 정책 및 등록 제한을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="04755-123">Intune MDM(모바일 장치 관리) 기관을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="04755-124">Intune을 사용한 적이 없는 경우 디바이스를 등록하기 전에 MDM 기관을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="04755-125">자세한 내용은 모바일 장치 관리 [권한 설정 을 참조하세요.](/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="04755-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="04755-126">이 단계는 새 Intune 테넌트 만들기 시 수행해야 하는 일회성 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="04755-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="04755-127">Android 디바이스 관리자 등록을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="04755-128">Android 기반 Teams 디바이스는 Intune을 사용하여 디바이스 관리자 장치로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="04755-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="04755-129">새로 만든 테넌트의 경우 디바이스 관리자 등록이 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="04755-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="04755-130">Android [디바이스 관리자 등록 을 참조하세요.](/intune/enrollment/android-enroll-device-administrator)</span><span class="sxs-lookup"><span data-stu-id="04755-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="04755-131">사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="04755-132">Intune에 Teams 디바이스의 사용자에게 유효한 Intune 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="04755-133">자세한 내용은 Intune에 디바이스를 등록할 수 있도록 사용자에게 라이선스 [할당을 참조하세요.](/intune/fundamentals/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="04755-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="04755-134">디바이스 관리자 규정 준수 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="04755-135">a.</span><span class="sxs-lookup"><span data-stu-id="04755-135">a.</span></span> <span data-ttu-id="04755-136">Android 디바이스 관리자 준수 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="04755-137">b.</span><span class="sxs-lookup"><span data-stu-id="04755-137">b.</span></span> <span data-ttu-id="04755-138">디바이스에 Azure Active Directory 사용자를 포함하는 Teams 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="04755-139">준수 [정책 사용을 참조하여 Intune을](/mem/intune/protect/device-compliance-get-started)사용하여 관리하는 디바이스에 대한 규칙을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04755-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="04755-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04755-140">See also</span></span>

[<span data-ttu-id="04755-141">Teams용 전화</span><span class="sxs-lookup"><span data-stu-id="04755-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="04755-142">IP Phone이 인증된 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04755-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="04755-143">Teams 표시</span><span class="sxs-lookup"><span data-stu-id="04755-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="04755-144">Teams에서 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="04755-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="04755-145">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="04755-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)