---
title: Android 디바이스에 대한 원격 프로비전 및 Teams 로그인
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Android 디바이스에 대한 원격 프로비전 및 로그인 Teams 방법 자세히 알아보기
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059192"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="b3fd0-103">Android 디바이스에 대한 원격 프로비전 및 Teams 로그인</span><span class="sxs-lookup"><span data-stu-id="b3fd0-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="b3fd0-104">IT 관리자는 원격으로 Android 디바이스에 프로비전하고 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="b3fd0-105">디바이스를 원격으로 프로비전하려면 관리자는 프로비전되는 디바이스의 MAC 아이디를 업로드하고 확인 코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="b3fd0-106">전체 프로세스는 관리자 센터에서 원격으로 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="b3fd0-107">지원되는 디바이스 검토</span><span class="sxs-lookup"><span data-stu-id="b3fd0-107">Review the supported devices</span></span>

<span data-ttu-id="b3fd0-108">다음 목록에는 Android 디바이스 펌웨어 요구 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="b3fd0-109">디바이스 범주</span><span class="sxs-lookup"><span data-stu-id="b3fd0-109">Device category</span></span>|<span data-ttu-id="b3fd0-110">디바이스 모델</span><span class="sxs-lookup"><span data-stu-id="b3fd0-110">Device model</span></span>|<span data-ttu-id="b3fd0-111">펌웨어 버전</span><span class="sxs-lookup"><span data-stu-id="b3fd0-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="b3fd0-112">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-112">Teams phones</span></span>|<span data-ttu-id="b3fd0-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="b3fd0-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="b3fd0-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="b3fd0-114">58.15.0.124</span></span>|
|<span data-ttu-id="b3fd0-115">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-115">Teams phones</span></span>|<span data-ttu-id="b3fd0-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="b3fd0-116">Yealink VP59</span></span>|<span data-ttu-id="b3fd0-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="b3fd0-117">91.15.0.58</span></span>|
|<span data-ttu-id="b3fd0-118">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-118">Teams phones</span></span>|<span data-ttu-id="b3fd0-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="b3fd0-119">Yealink CP960</span></span>|<span data-ttu-id="b3fd0-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="b3fd0-120">73.15.0.117</span></span>|
|<span data-ttu-id="b3fd0-121">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-121">Teams phones</span></span>|<span data-ttu-id="b3fd0-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="b3fd0-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="b3fd0-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="b3fd0-123">122.15.0.36</span></span>|
|<span data-ttu-id="b3fd0-124">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-124">Teams phones</span></span>|<span data-ttu-id="b3fd0-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="b3fd0-125">Crestron UC-2</span></span>|<span data-ttu-id="b3fd0-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="b3fd0-126">1.0.3.52</span></span>|
|<span data-ttu-id="b3fd0-127">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-127">Teams phones</span></span>|  <span data-ttu-id="b3fd0-128">Poly Trio C60</span><span class="sxs-lookup"><span data-stu-id="b3fd0-128">Poly Trio C60</span></span>|  <span data-ttu-id="b3fd0-129">7.0.2.1071</span><span class="sxs-lookup"><span data-stu-id="b3fd0-129">7.0.2.1071</span></span>|
|<span data-ttu-id="b3fd0-130">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-130">Teams phones</span></span>|  <span data-ttu-id="b3fd0-131">CCX400/CCX500/CCX600</span><span class="sxs-lookup"><span data-stu-id="b3fd0-131">CCX400/CCX500/CCX600</span></span>    |<span data-ttu-id="b3fd0-132">7.0.2.1072</span><span class="sxs-lookup"><span data-stu-id="b3fd0-132">7.0.2.1072</span></span>|
|<span data-ttu-id="b3fd0-133">Teams 휴대폰</span><span class="sxs-lookup"><span data-stu-id="b3fd0-133">Teams phones</span></span>|  <span data-ttu-id="b3fd0-134">오디오 코드 C448HD/C450HD/C470HD</span><span class="sxs-lookup"><span data-stu-id="b3fd0-134">Audio Codes C448HD/C450HD/C470HD</span></span>|   <span data-ttu-id="b3fd0-135">1.10.120</span><span class="sxs-lookup"><span data-stu-id="b3fd0-135">1.10.120</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="b3fd0-136">디바이스 MAC 주소 추가</span><span class="sxs-lookup"><span data-stu-id="b3fd0-136">Add a device MAC address</span></span>

<span data-ttu-id="b3fd0-137">다음 단계를 완료하여 새 디바이스를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-137">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="b3fd0-138">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-138">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="b3fd0-139">디바이스를 **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3fd0-139">Expand **Devices**.</span></span>
3. <span data-ttu-id="b3fd0-140">작업 **탭에서** 새 디바이스 **프로비전을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-140">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="b3fd0-141">새 디바이스 **프로비전** 창에서 MAC 주소를 수동으로 추가하거나 파일을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-141">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="b3fd0-142">디바이스 MAC 주소를 수동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-142">Manually add a device MAC address</span></span>

1. <span data-ttu-id="b3fd0-143">대기 중 **활성화 탭에서** **MAC ID 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3fd0-143">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![디바이스 mac 주소를 수동으로 추가합니다.](../media/remote-provision-6.png)

1. <span data-ttu-id="b3fd0-145">MAC ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-145">Enter the MAC ID.</span></span>
1. <span data-ttu-id="b3fd0-146">위치를 입력하여 기술자가 디바이스를 설치할 위치를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-146">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="b3fd0-147">완료 **시 적용을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-147">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="b3fd0-148">업로드 MAC 주소를 추가하기 위해 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-148">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="b3fd0-149">대기 **중** 활성화 탭에서 MAC **업로드 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3fd0-149">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="b3fd0-150">파일 템플릿을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-150">Download the file template.</span></span>
3. <span data-ttu-id="b3fd0-151">MAC ID 및 위치를 입력한 다음 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-151">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="b3fd0-152">**파일 을** 선택한 다음 을 **업로드.**</span><span class="sxs-lookup"><span data-stu-id="b3fd0-152">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="b3fd0-153">확인 코드 생성</span><span class="sxs-lookup"><span data-stu-id="b3fd0-153">Generate a verification code</span></span>

<span data-ttu-id="b3fd0-154">디바이스에 대한 확인 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-154">You need a verification code for the devices.</span></span> <span data-ttu-id="b3fd0-155">확인 코드는 일괄적으로 또는 디바이스 수준에서 생성되어 24시간 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-155">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="b3fd0-156">대기 **중 활성화 탭에서** 기존 MAC ID를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-156">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="b3fd0-157">MAC 주소에 대한 암호가 만들어지며 확인 **코드 열에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b3fd0-157">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="b3fd0-158">현장 기술자에게 MAC 신분증 및 확인 코드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-158">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="b3fd0-159">파일에서 직접 세부 정보를 내보낼 수 있으며 실제 설치 작업을 수행하고 있는 기술자에게 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-159">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="b3fd0-160">디바이스 프로비전</span><span class="sxs-lookup"><span data-stu-id="b3fd0-160">Provision the device</span></span>

<span data-ttu-id="b3fd0-161">디바이스에 전원이 공급되고 네트워크에 연결되면 기술자가 디바이스를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-161">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="b3fd0-162">이러한 단계는 디바이스에서 Teams 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-162">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="b3fd0-163">기술자는 **에서** 디바이스 **프로비전을 설정.**</span><span class="sxs-lookup"><span data-stu-id="b3fd0-163">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![작업 탭에서 새 디바이스 옵션 프로비전](../media/provision-device1.png)
  
2. <span data-ttu-id="b3fd0-165">기술자는 제공된 입력 필드에 디바이스별 확인 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-165">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![새 디바이스 확인 프로비전](../media/provision-device-verification1.png)

   <span data-ttu-id="b3fd0-167">디바이스가 성공적으로 프로비전된 후 테넌트 이름이 로그인 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-167">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![로그인 페이지의 테넌트 이름](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="b3fd0-169">원격으로 로그인</span><span class="sxs-lookup"><span data-stu-id="b3fd0-169">Sign in remotely</span></span>

<span data-ttu-id="b3fd0-170">프로비전된 디바이스가 대기 로그인 **탭에 나타납니다.** 개별 디바이스를 선택하여 원격 로그인 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-170">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="b3fd0-171">대기 로그인 탭에서 **디바이스를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd0-171">Select a device from the **Awaiting sign in** tab.</span></span>

   ![로그인할 준비가 된 디바이스 목록이 있는 창입니다.](../media/remote-device1.png)

2. <span data-ttu-id="b3fd0-173">사용자 로그인의 지침을 **따르고** 닫기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3fd0-173">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![개별 디바이스에 대한 사용자 로그인 창](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="b3fd0-175">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b3fd0-175">Related article</span></span>

- [<span data-ttu-id="b3fd0-176">Teams에서 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="b3fd0-176">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="b3fd0-177">원격 Teams 디바이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="b3fd0-177">Update Teams devices remotely</span></span>](remote-update.md)
