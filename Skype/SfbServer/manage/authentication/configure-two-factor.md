---
title: 비즈니스용 Skype 서버에서 2 단계 인증 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '요약: 비즈니스용 Skype 서버에서 2 단계 인증을 구성 합니다.'
ms.openlocfilehash: 91a8929b89a584b116f1c7ec9313daa2fe679fd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189690"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="ebab0-103">비즈니스용 Skype 서버에서 2 단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="ebab0-104">**요약:** 비즈니스용 Skype 서버에서 2 단계 인증을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="ebab0-105">다음 섹션에서는 배포에 대해 2 단계 인증을 구성 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="ebab0-106">2 단계 인증에 대 한 자세한 내용은 [온라인 관리자-그리드 사용자 게시에 대해 Office 365 다단계 인증 사용](https://go.microsoft.com/fwlink/p/?LinkId=313332)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebab0-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="ebab0-107">스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 인증 기관 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="ebab0-108">다음 단계에서는 스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 CA를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="ebab0-109">엔터프라이즈 루트 CA를 설치 하는 방법에 대 한 자세한 내용은 [엔터프라이즈 루트 인증 기관 설치](https://go.microsoft.com/fwlink/p/?LinkID=313364)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebab0-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="ebab0-110">도메인 관리자 계정을 사용 하 여 엔터프라이즈 CA 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="ebab0-111">시스템 관리자를 시작 하 고 인증 기관 웹 등록 역할이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="ebab0-112">**관리 도구** 메뉴에서 **인증 기관** 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="ebab0-113">탐색 창에서 **인증 기관을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="ebab0-114">**인증서 템플릿을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 선택한 다음 **발급할 인증서 템플릿을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="ebab0-115">**등록 에이전트**, **스마트 카드 사용자**, **스마트 카드 로그온**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="ebab0-116">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-116">Click **OK**.</span></span>

8. <span data-ttu-id="ebab0-117">**인증서 템플릿을**마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="ebab0-118">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-118">Select **Manage**.</span></span>

10. <span data-ttu-id="ebab0-119">스마트 카드 사용자 서식 파일의 속성을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="ebab0-120">**보안** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="ebab0-121">아래와 같이 사용 권한을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="ebab0-122">읽기/등록 (허용) 권한을 사용 하 여 개별 사용자 광고 계정을 추가 하거나</span><span class="sxs-lookup"><span data-stu-id="ebab0-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="ebab0-123">읽기/등록 (허용) 권한이 있는 스마트 카드 사용자를 포함 하는 보안 그룹을 추가 하거나</span><span class="sxs-lookup"><span data-stu-id="ebab0-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="ebab0-124">읽기/등록 (허용) 권한을 사용 하 여 도메인 사용자 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="ebab0-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="ebab0-125">가상 스마트 카드에 맞게 Windows 8 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="ebab0-126">2 단계 인증 및 스마트 카드 기술을 구축할 때 고려해 야 하는 한 가지 요인은 구현 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="ebab0-127">Windows 8은 다양 한 새로운 보안 기능을 제공 하 고 가장 흥미로운 새 기능 중 하나는 가상 스마트 카드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="ebab0-128">규정 버전 1.2을 충족 하는 TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 장착 된 컴퓨터의 경우, 이제 조직에서는 하드웨어에 대 한 추가 투자 없이 스마트 카드 로그온의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="ebab0-129">자세한 내용은 [Windows 8과 함께 가상 스마트 카드 사용](https://go.microsoft.com/fwlink/p/?LinkId=313365)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebab0-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="ebab0-130">가상 스마트 카드에 대해 Windows 8을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="ebab0-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="ebab0-131">비즈니스용 Skype 사용이 가능한 사용자의 자격 증명을 사용 하 여 Windows 8 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="ebab0-132">Windows 8 시작 화면에서 화면 오른쪽 아래 모서리로 커서를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="ebab0-133">**검색** 옵션을 선택한 다음 Forcommand 프롬프트를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="ebab0-134">**명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="ebab0-135">다음 명령을 실행 하 여 TPM (신뢰할 수 있는 플랫폼 모듈) 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="ebab0-136">TPM 관리 콘솔에서 TPM 사양 버전이 최소 1.2 인지 확인</span><span class="sxs-lookup"><span data-stu-id="ebab0-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebab0-137">호환 되는 TPM (신뢰할 수 있는 플랫폼 모듈)을 찾을 수 없다는 대화 상자가 표시 되는 경우 컴퓨터에 호환 되는 TPM 모듈이 있고 시스템 BIOS에서 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="ebab0-138">TPM 관리 콘솔을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-138">Close the TPM management console</span></span>

8. <span data-ttu-id="ebab0-139">명령 프롬프트에서 다음 명령을 사용 하 여 새 가상 스마트 카드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="ebab0-140">가상 스마트 카드를 만들 때 사용자 지정 PIN 값을 제공 하려면/cpin prompt를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="ebab0-141">명령 프롬프트에서 다음 명령을 실행 하 여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="ebab0-142">컴퓨터 관리 콘솔에서 **장치 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="ebab0-143">**스마트 카드 판독기**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="ebab0-144">새 가상 스마트 카드 판독기가 성공적으로 생성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="ebab0-145">스마트 카드 인증을 위해 사용자 등록</span><span class="sxs-lookup"><span data-stu-id="ebab0-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="ebab0-146">스마트 카드 인증을 위해 사용자를 등록 하는 방법에는 일반적으로 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="ebab0-147">더 간단한 방법은 사용자가 웹 등록을 사용 하 여 스마트 카드 인증을 직접 등록 하도록 하는 반면 복잡 한 방법은 등록 에이전트를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="ebab0-148">이 항목에서는 스마트 카드 인증서의 자체 등록에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="ebab0-149">등록 에이전트로 사용자를 등록 하는 방법에 대 한 자세한 내용은 [다른 사용자를 대신 하 여 인증서 등록](https://go.microsoft.com/fwlink/p/?LinkID=313367)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebab0-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="ebab0-150">스마트 카드 인증을 위해 사용자를 등록 하려면</span><span class="sxs-lookup"><span data-stu-id="ebab0-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="ebab0-151">비즈니스용 Skype 사용이 가능한 사용자의 자격 증명을 사용 하 여 Windows 8 workstation에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="ebab0-152">Internet Explorer를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="ebab0-153">**인증 기관 웹 등록** 페이지 (예:)로 이동 https://MyCA.contoso.com/certsrv)합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebab0-154">Internet Explorer 10을 사용 하는 경우 호환 모드에서이 웹 사이트를 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="ebab0-155">**시작** 페이지에서 **인증서 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="ebab0-156">그런 다음 **고급 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="ebab0-157">**이 CA에 대 한 요청 만들기 및 제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="ebab0-158">**인증서 템플릿** 섹션에서 **스마트 카드 사용자** 를 선택 하 고 다음 값을 사용 하 여 고급 인증서 요청을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="ebab0-159">**키 옵션** 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="ebab0-160">**새 키 집합 만들기** 라디오 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="ebab0-161">**CSP**의 경우 **Microsoft 기본 스마트 카드 암호화 공급자** 선택</span><span class="sxs-lookup"><span data-stu-id="ebab0-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="ebab0-162">**키 사용**에 대해 **Exchange** 를 선택 합니다 (사용 가능한 유일한 옵션).</span><span class="sxs-lookup"><span data-stu-id="ebab0-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="ebab0-163">**키 크기**에는 2048을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="ebab0-164">**자동 키 컨테이너 이름이** 선택 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="ebab0-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="ebab0-165">다른 확인란은 선택 하지 않은 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="ebab0-166">**추가 옵션** 에서 다음 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="ebab0-167">**요청 형식의** 경우 **CMC**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="ebab0-168">**해시 알고리즘** 의 경우 **sha1**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="ebab0-169">**친근 한 이름** enterSmardcard 인증서.</span><span class="sxs-lookup"><span data-stu-id="ebab0-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="ebab0-170">실제 스마트 카드 판독기를 사용 하는 경우 장치에 스마트 카드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="ebab0-171">**제출을** 클릭 하 여 인증서 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="ebab0-172">메시지가 표시 되 면 가상 스마트 카드를 만드는 데 사용 된 PIN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebab0-173">기본 가상 스마트 카드 PIN 값은 ' 12345678 '입니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="ebab0-174">인증서가 발급 되 면 **이 인증서 설치** 를 클릭 하 여 등록 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="ebab0-175">"이 웹 브라우저가 인증서 요청 생성을 지원 하지 않습니다" 오류가 발생 하 여 인증서 요청이 실패 하면 문제를 해결할 수 있는 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="ebab0-176">AD FS 2.0 (Active Directory Federation Services) 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="ebab0-177">다음 섹션에서는 multi-factor authentication을 지원 하도록 AD FS 2.0 (Active Directory Federation Services)를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="ebab0-178">AD FS 2.0을 설치 하는 방법에 대 한 자세한 내용은 [AD fs 2.0 단계별 및 가이드 사용법](https://go.microsoft.com/fwlink/p/?LinkId=313374)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebab0-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="ebab0-179">AD FS 2.0을 설치할 때 Windows Server Manager를 사용 하 여 Active Directory Federation Services 역할을 추가 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ebab0-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="ebab0-180">대신 [Active Directory Federation Services 2.0 RTW 패키지](https://go.microsoft.com/fwlink/p/?LinkId=313375)를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="ebab0-181">2 단계 인증을 위해 AD FS를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="ebab0-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="ebab0-182">도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="ebab0-183">Windows PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="ebab0-184">Windows PowerShell 명령줄에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="ebab0-185">다음 명령을 실행 하 여 배포와 관련 된 서버 이름을 대체 하 여 수동 인증을 사용할 각 서버와 파트너 관계를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="ebab0-186">관리 도구 메뉴에서 AD FS 2.0 관리 콘솔을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="ebab0-187">**신뢰 관계** > **신뢰 당사자 신뢰**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="ebab0-188">비즈니스용 Skype 서버용으로 새 트러스트가 생성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="ebab0-189">다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 신뢰에 대 한 발급 권한 부여 규칙을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="ebab0-190">다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 신뢰에 대 한 발급 변환 규칙을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="ebab0-191">AD FS 2.0 관리 콘솔에서 신뢰 당사자 신뢰를 마우스 오른쪽 단추로 클릭 하 고 **클레임 규칙 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="ebab0-192">**발급 권한 부여 규칙** 탭을 선택 하 고 새 권한 부여 규칙이 성공적으로 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="ebab0-193">**발급 변형 규칙** 탭을 선택 하 고 새 변형 규칙이 성공적으로 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="ebab0-194">클라이언트 인증을 지원 하도록 AD FS 2.0 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="ebab0-195">AD FS 2.0에서 스마트 카드를 사용 하 여 인증을 지원 하도록 구성할 수 있는 인증 유형에는 두 가지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="ebab0-196">FBA (양식 기반 인증)</span><span class="sxs-lookup"><span data-stu-id="ebab0-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="ebab0-197">전송 계층 보안 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="ebab0-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="ebab0-198">폼 기반 인증을 사용 하 여 사용자 이름/암호를 사용 하거나 스마트 카드 및 PIN을 사용 하 여 인증할 수 있는 웹 페이지를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="ebab0-199">이 항목에서는 AD FS 2.0를 사용 하 여 전송 계층 보안 클라이언트 인증을 구현 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="ebab0-200">AD FS 2.0 인증 형식에 대 한 자세한 내용은 [AD fs 2.0: 로컬 인증 유형을 변경 하는 방법을](https://go.microsoft.com/fwlink/p/?LinkId=313384)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebab0-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="ebab0-201">클라이언트 인증을 지원 하도록 AD FS 2.0를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="ebab0-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="ebab0-202">도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="ebab0-203">Windows 탐색기를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="ebab0-204">C:\inetpub\adfs\ls로 이동</span><span class="sxs-lookup"><span data-stu-id="ebab0-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="ebab0-205">기존 web.config 파일의 백업 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="ebab0-206">메모장을 사용 하 여 기존 web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="ebab0-207">메뉴 모음에서 **편집** 을 선택 하 고 **찾기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="ebab0-208">Localauthenticationtypes \<\>를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="ebab0-209">4 개의 인증 유형이 한 줄당 하나씩 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="ebab0-210">TLSClient 인증 형식이 포함 된 줄을 섹션의 목록 맨 위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="ebab0-211">Web.config 파일을 저장 하 고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="ebab0-212">관리자 권한으로 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="ebab0-213">다음 명령을 실행 하 여 IIS를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="ebab0-214">비즈니스용 Skype 서버 수동 인증 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="ebab0-215">다음 섹션에서는 수동 인증을 지원 하도록 비즈니스용 Skype 서버를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="ebab0-216">이 기능을 사용 하도록 설정 하면, 2 단계 인증을 사용 하도록 설정 된 사용자는 비즈니스용 Skype 클라이언트를 사용 하 여 로그인 하기 위해 실제 또는 가상 스마트 카드와 유효한 PIN을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="ebab0-217">고객은 서비스 수준에서 등록자 및 웹 서비스에 대 한 수동 인증을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="ebab0-218">전역 수준에서 등록자와 웹 서비스에 대해 수동 인증이 사용 하도록 설정 되어 있는 경우 지원 되는 데스크톱 클라이언트를 사용 하 여 로그인 하지 않은 사용자에 대 한 조직 전체 인증 실패가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="ebab0-219">웹 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-219">Web Service Configuration</span></span>

<span data-ttu-id="ebab0-220">다음 단계에서는 수동 인증을 사용 하도록 설정 되는 디렉터, 엔터프라이즈 풀 및 Standard Edition 서버에 대 한 사용자 지정 웹 서비스 구성을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="ebab0-221">사용자 지정 웹 서비스 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ebab0-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="ebab0-222">비즈니스용 skype 관리자 계정을 사용 하 여 비즈니스용 Skype 서버 프런트 엔드 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="ebab0-223">비즈니스용 Skype 서버 관리 셸을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="ebab0-224">비즈니스용 Skype Server Management Shell 명령줄에서 다음 명령을 실행 하 여 수동 인증에 사용할 각 디렉터, 엔터프라이즈 풀 및 Standard Edition Server에 대 한 새 웹 서비스 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="ebab0-225">WsFedPassiveMetadataUri FQDN에 대 한 값은 AD FS 2.0 서버의 페더레이션 서비스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="ebab0-226">페더레이션 서비스 이름 값은 탐색 창에서 **서비스** 를 마우스 오른쪽 단추로 클릭 한 다음 **페더레이션 서비스 속성 편집**을 선택 하 여 AD FS 2.0 관리 콘솔에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="ebab0-227">다음 명령을 실행 하 여 UseWsFedPassiveAuth 및 WsFedPassiveMetadataUri 값이 올바르게 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="ebab0-228">클라이언트의 경우 Passive 인증은 webticket 인증에 가장 선호 하는 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="ebab0-229">수동 인증을 사용 하도록 설정 되는 모든 디렉터, Enterprise 풀 및 Standard Edition 서버에 대해 다음 cmdlet을 실행 하 여 비즈니스용 Skype Web Services에서 다른 모든 인증 유형을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="ebab0-230">다음 cmdlet을 실행 하 여 다른 모든 인증 유형을 사용 하지 않도록 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="ebab0-231">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="ebab0-231">Proxy Configuration</span></span>

<span data-ttu-id="ebab0-232">비즈니스용 skype Web Services에 대해 인증서 인증을 사용 하지 않도록 설정 하면 비즈니스용 Skype 클라이언트에서 등록 기관 서비스에 인증 하는 데 Kerberos 또는 NTLM 등의 덜 선호 하는 인증 유형을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="ebab0-233">클라이언트가 webticket을 검색할 수 있도록 인증서 인증이 여전히 필요 하지만, 등록 기관 서비스에 대해 Kerberos 및 NTLM을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="ebab0-234">다음 단계에서는 수동 인증을 사용 하도록 설정 되는 Edge 풀, 엔터프라이즈 풀 및 Standard Edition 서버에 대 한 사용자 지정 프록시 구성을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="ebab0-235">사용자 지정 프록시 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ebab0-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="ebab0-236">비즈니스용 Skype Server Management Shell 명령줄에서 다음을 실행 하 여 수동 인증에 사용할 각 비즈니스용 Skype Server Edge 풀, 엔터프라이즈 풀 및 Standard Edition Server에 대 한 새 프록시 구성을 만듭니다. 명령과</span><span class="sxs-lookup"><span data-stu-id="ebab0-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="ebab0-237">다음 명령을 실행 하 여 다른 모든 프록시 인증 유형이 비활성화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebab0-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="ebab0-238">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebab0-238">See also</span></span>

[<span data-ttu-id="ebab0-239">비즈니스용 Skype 서버에서 2 단계 인증 관리</span><span class="sxs-lookup"><span data-stu-id="ebab0-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="ebab0-240">비즈니스용 Skype 클라이언트 및 비즈니스용 Skype 서버에서 2 단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="ebab0-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
