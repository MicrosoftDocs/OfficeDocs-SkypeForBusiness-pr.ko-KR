---
title: 비즈니스용 Skype 서버에서 2단계 인증 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '요약: 비즈니스용 Skype 서버에서 2단계 인증을 구성합니다.'
ms.openlocfilehash: 8651be3fbc07bb890637bc8d1c7c99a827d1ea1e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096824"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="fd2ed-103">비즈니스용 Skype 서버에서 2단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="fd2ed-104">**요약:** 비즈니스용 Skype 서버에서 2단계 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="fd2ed-105">다음 섹션에서는 배포에 대해 2단계 인증을 구성하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="fd2ed-106">2단계 인증에 대한 자세한 내용은 온라인 관리자에 대해 Office 365 다단계 인증 사용 [- 그리드 사용자 게시물을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=313332)</span><span class="sxs-lookup"><span data-stu-id="fd2ed-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="fd2ed-107">스마트 카드 인증을 지원하도록 엔터프라이즈 루트 인증 기관 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="fd2ed-108">다음 단계에서는 스마트 카드 인증을 지원하도록 엔터프라이즈 루트 CA를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="fd2ed-109">엔터프라이즈 루트 CA를 설치하는 방법에 대한 자세한 내용은 엔터프라이즈 루트 인증 기관 [설치를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="fd2ed-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span></span>

1. <span data-ttu-id="fd2ed-110">도메인 관리자 계정을 사용하여 엔터프라이즈 CA 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="fd2ed-111">시스템 관리자를 시작하고 인증 기관 웹 등록 역할이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="fd2ed-112">관리 도구 **메뉴에서** 인증 기관 관리 **콘솔을** 여세요.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="fd2ed-113">탐색 창에서 인증 **기관 을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="fd2ed-114">인증서 **템플릿을 마우스 오른쪽 단추로 클릭하고** 새로 **고치기** 를 선택한 다음 **발급할 인증서 템플릿 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="fd2ed-115">등록 **에이전트,** **스마트 카드 사용자** 및 스마트 카드 **로그온을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="fd2ed-116">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-116">Click **OK**.</span></span>

8. <span data-ttu-id="fd2ed-117">인증서 **템플릿을 마우스 오른쪽 단추로 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="fd2ed-118">관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-118">Select **Manage**.</span></span>

10. <span data-ttu-id="fd2ed-119">Smartcard 사용자 템플릿의 속성을 엽니 다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="fd2ed-120">보안 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="fd2ed-121">사용 권한을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="fd2ed-122">읽기/등록(허용) 권한이 있는 개별 사용자 AD 계정 추가 또는</span><span class="sxs-lookup"><span data-stu-id="fd2ed-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="fd2ed-123">읽기/등록(허용) 권한이 있는 스마트 카드 사용자가 포함된 보안 그룹 추가 또는</span><span class="sxs-lookup"><span data-stu-id="fd2ed-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="fd2ed-124">읽기/등록(허용) 권한이 있는 도메인 사용자 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="fd2ed-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="fd2ed-125">가상 스마트 카드용 Windows 8 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="fd2ed-126">2단계 인증 및 스마트 카드 기술을 배포할 때 고려해야 할 한 가지 요소는 구현 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="fd2ed-127">Windows 8은 다양한 새로운 보안 기능을 제공하며, 가장 흥미로운 새로운 기능 중 하나는 가상 스마트 카드에 대한 지원입니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="fd2ed-128">사양 버전 1.2를 충족하는 TPM(신뢰할 수 있는 플랫폼 모듈) 칩이 장착된 컴퓨터의 경우 이제 조직은 하드웨어에 추가 투자를 하지 않고도 스마트 카드 로그온의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="fd2ed-129">자세한 내용은 [Windows 8에서 가상 스마트 카드 사용을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=313365)</span><span class="sxs-lookup"><span data-stu-id="fd2ed-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="fd2ed-130">가상 스마트 카드에 대해 Windows 8을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="fd2ed-131">비즈니스용 Skype 사용 가능 사용자의 자격 증명을 사용하여 Windows 8 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="fd2ed-132">Windows 8 시작 화면에서 커서를 화면의 오른쪽 아래 모서리로 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="fd2ed-133">검색 **옵션을** 선택한 다음Command 프롬프트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="fd2ed-134">명령 프롬프트를 **마우스 오른쪽 단추로** 클릭한 다음 **관리자 권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="fd2ed-135">다음 명령을 실행하여 TPM(신뢰할 수 있는 플랫폼 모듈) 관리 콘솔을 니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="fd2ed-136">TPM 관리 콘솔에서 TPM 사양 버전이 1.2 이상인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd2ed-137">TPM(호환 가능한 트러스트 플랫폼 모듈)을 찾을 수 없다는 대화 상자가 수신되면 컴퓨터에 호환되는 TPM 모듈이 있으며 시스템 BIOS에서 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="fd2ed-138">TPM 관리 콘솔 닫기</span><span class="sxs-lookup"><span data-stu-id="fd2ed-138">Close the TPM management console</span></span>

8. <span data-ttu-id="fd2ed-139">명령 프롬프트에서 다음 명령을 사용하여 새 가상 스마트 카드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="fd2ed-140">가상 스마트 카드를 만들 때 사용자 지정 PIN 값을 제공하기 위해 대신 /pin prompt를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="fd2ed-141">명령 프롬프트에서 다음 명령을 실행하여 컴퓨터 관리 콘솔을 니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="fd2ed-142">컴퓨터 관리 콘솔에서 장치 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="fd2ed-143">스마트 **카드 판독기를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="fd2ed-144">새 가상 스마트 카드 판독기가 성공적으로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="fd2ed-145">스마트 카드 인증을 위해 사용자 등록</span><span class="sxs-lookup"><span data-stu-id="fd2ed-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="fd2ed-146">일반적으로 스마트 카드 인증을 위해 사용자를 등록하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="fd2ed-147">보다 쉬운 방법은 사용자가 웹 등록을 사용하여 스마트 카드 인증을 직접 등록하도록 하는 반면, 보다 복잡한 방법은 등록 에이전트를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="fd2ed-148">이 항목에서는 스마트 카드 인증서에 대한 자체 등록에 대해 중점적으로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="fd2ed-149">사용자를 등록 에이전트로 대신하여 등록하는 자세한 내용은 [Enroll for Certificates on Behalf of Other Users을 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="fd2ed-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="fd2ed-150">스마트 카드 인증을 위해 사용자를 등록</span><span class="sxs-lookup"><span data-stu-id="fd2ed-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="fd2ed-151">비즈니스용 Skype 사용 가능 사용자의 자격 증명을 사용하여 Windows 8 Workstation에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="fd2ed-152">시작 Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="fd2ed-153">인증 기관 웹 **등록** 페이지(예: 로 https://MyCA.contoso.com/certsrv) 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd2ed-154">10 Internet Explorer 사용하는 경우 호환성 모드에서 이 웹 사이트를 보아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="fd2ed-155">시작 **페이지에서** 인증서 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="fd2ed-156">그런 다음 고급 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="fd2ed-157">이 CA에 요청 만들기 및 **제출을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="fd2ed-158">인증서 **템플릿 섹션에서 Smartcard** **사용자를** 선택하고 다음 값을 사용하여 고급 인증서 요청을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="fd2ed-159">**주요 옵션은** 다음 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="fd2ed-160">새 키 **집합 만들기 라디오** 단추 선택</span><span class="sxs-lookup"><span data-stu-id="fd2ed-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="fd2ed-161">**CSP의 경우** **Microsoft 기본 스마트 카드 암호화 공급자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="fd2ed-162">키 **사용에 대해** **Exchange를** 선택합니다(사용 가능한 유일한 옵션).</span><span class="sxs-lookup"><span data-stu-id="fd2ed-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="fd2ed-163">키 **크기로** 2048을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="fd2ed-164">자동 키 **컨테이너 이름이 선택되어 있는지** 확인</span><span class="sxs-lookup"><span data-stu-id="fd2ed-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="fd2ed-165">다른 상자는 선택하지 않은 것으로 떠 .</span><span class="sxs-lookup"><span data-stu-id="fd2ed-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="fd2ed-166">추가 **옵션에서** 다음 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="fd2ed-167">요청 **형식의 경우** **CMC 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="fd2ed-168">해시 **알고리즘의 경우** **sha1 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="fd2ed-169">**이름에** 대해Mardcard 인증서를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="fd2ed-170">실제 스마트 카드 판독기를 사용하는 경우 장치에 스마트 카드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="fd2ed-171">**제출을** 클릭하여 인증서 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="fd2ed-172">메시지가 표시될 때 가상 스마트 카드를 만드는 데 사용된 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd2ed-173">기본 가상 스마트 카드 PIN 값은 '12345678'입니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="fd2ed-174">인증서가 발급된 후 이  인증서 설치를 클릭하여 등록 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="fd2ed-175">"이 웹 브라우저에서 인증서 요청 생성을 지원하지 않습니다."라는 오류와 함께 인증서 요청이 실패하면 다음 세 가지 방법으로 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="fd2ed-176">AD FS 2.0(Active Directory Federation Services) 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="fd2ed-177">다음 섹션에서는 다단계 인증을 지원하도록 AD FS 2.0(Active Directory Federation Services)을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="fd2ed-178">AD FS 2.0을 설치하는 방법에 대한 자세한 내용은 [AD FS 2.0 단계별](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))및 방법 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>

> [!NOTE]
> <span data-ttu-id="fd2ed-179">AD FS 2.0을 설치할 때 Windows Server Manager를 사용하여 Active Directory Federation Services 역할을 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="fd2ed-180">대신 [Active Directory Federation Services 2.0 RTW 패키지를 다운로드하여 설치합니다.](https://go.microsoft.com/fwlink/p/?LinkId=313375)</span><span class="sxs-lookup"><span data-stu-id="fd2ed-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="fd2ed-181">2단계 인증에 대해 AD FS를 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="fd2ed-182">도메인 관리자 계정을 사용하여 AD FS 2.0 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="fd2ed-183">Windows PowerShell을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="fd2ed-184">명령 Windows PowerShell 명령줄에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="fd2ed-185">다음 명령을 실행하여 배포와 관련한 서버 이름을 바꾸어 수동 인증을 사용하도록 설정할 각 서버와 파트너 관계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="fd2ed-186">관리 도구 메뉴에서 AD FS 2.0 관리 콘솔을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="fd2ed-187">**트러스트 관계**  >  **신뢰 파티 트러스트 를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="fd2ed-188">비즈니스용 Skype 서버에 대한 새 트러스트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="fd2ed-189">다음 명령을 실행하여 신뢰할 수 있는 Windows PowerShell 트러스트에 대한 issuance Authorization Rule을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="fd2ed-190">다음 명령을 실행하여 신뢰 파티 트러스트에 대한 Windows PowerShell 변환 규칙을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="fd2ed-191">AD FS 2.0 관리 콘솔에서 신뢰하는 사용자 트러스트 를 마우스 오른쪽 단추로 클릭하고 클레임 규칙 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="fd2ed-192">**Issuance Authorization Rules(발행 권한 부여 규칙)** 탭을 선택하고 새 권한 부여 규칙이 성공적으로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="fd2ed-193">**Issuance Transform Rules(발행 변환 규칙)** 탭을 선택하고 새 변환 규칙이 성공적으로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="fd2ed-194">클라이언트 인증을 지원하도록 AD FS 2.0 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="fd2ed-195">AD FS 2.0에서 스마트 카드를 사용한 인증을 지원하도록 구성할 수 있는 두 가지 인증 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="fd2ed-196">FBA(양식 기반 인증)</span><span class="sxs-lookup"><span data-stu-id="fd2ed-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="fd2ed-197">전송 계층 보안 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="fd2ed-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="fd2ed-198">양식 기반 인증을 사용하면 사용자가 사용자 이름/암호를 사용하여 또는 스마트 카드와 PIN을 사용하여 인증할 수 있는 웹 페이지를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="fd2ed-199">이 항목에서는 AD FS 2.0을 사용하여 전송 계층 보안 클라이언트 인증을 구현하는 방법을 중점적으로 다루고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="fd2ed-200">AD FS 2.0 인증 유형에 대한 자세한 내용은 [AD FS 2.0: 로컬](https://go.microsoft.com/fwlink/p/?LinkId=313384)인증 유형을 변경하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="fd2ed-201">클라이언트 인증을 지원하도록 AD FS 2.0을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="fd2ed-202">도메인 관리자 계정을 사용하여 AD FS 2.0 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="fd2ed-203">Windows 탐색기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="fd2ed-204">C:\inetpub\adfs\ls로 탐색</span><span class="sxs-lookup"><span data-stu-id="fd2ed-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="fd2ed-205">기존 데이터베이스 파일의 백업 복사본을 web.config.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="fd2ed-206">메모장에서 web.config 기존 파일 열기</span><span class="sxs-lookup"><span data-stu-id="fd2ed-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="fd2ed-207">메뉴 표시줄에서 편집을 **선택한** 다음 찾기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd2ed-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="fd2ed-208">\<localAuthenticationTypes\>를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="fd2ed-209">네 가지 인증 유형이 나열되어 있습니다(한 줄에 하나씩).</span><span class="sxs-lookup"><span data-stu-id="fd2ed-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="fd2ed-210">TLSClient 인증 유형이 포함된 줄을 섹션의 목록 맨 위로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="fd2ed-211">파일 파일을 저장하고 web.config 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="fd2ed-212">관리자 권한으로 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="fd2ed-213">다음 명령을 실행하여 IIS를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="fd2ed-214">비즈니스용 Skype 서버 수동 인증 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="fd2ed-215">다음 섹션에서는 수동 인증을 지원하도록 비즈니스용 Skype 서버를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="fd2ed-216">2단계 인증을 사용하도록 설정한 사용자는 실제 또는 가상 스마트 카드와 유효한 PIN을 사용하여 비즈니스용 Skype 클라이언트를 사용하여 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="fd2ed-217">고객은 서비스 수준에서 등록자 및 웹 서비스에 대해 수동 인증을 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="fd2ed-218">전역 수준에서 등록자 및 웹 서비스에 대해 수동 인증을 사용하도록 설정하면 지원되는 데스크톱 클라이언트로 로그인하지 않은 사용자의 조직 전체 인증 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="fd2ed-219">웹 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-219">Web Service Configuration</span></span>

<span data-ttu-id="fd2ed-220">다음 단계에서는 수동 인증을 사용하도록 설정되는 Director, Enterprise Pools 및 Standard Edition 서버에 대한 사용자 지정 웹 서비스 구성을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="fd2ed-221">사용자 지정 웹 서비스 구성을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="fd2ed-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="fd2ed-222">비즈니스용 Skype 관리자 계정을 사용하여 비즈니스용 Skype 서버 프런트 엔드 서버에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="fd2ed-223">비즈니스용 Skype 서버 관리 셸을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="fd2ed-224">비즈니스용 Skype 서버 관리 셸 명령줄에서 다음 명령을 실행하여 수동 인증을 사용하도록 설정되는 각 Director, Enterprise Pool 및 Standard Edition 서버에 대해 새 웹 서비스 구성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="fd2ed-225">WsFedPassiveMetadataUri FQDN 값은 AD FS 2.0 서버의 페더ATION 서비스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="fd2ed-226">Federation Service Name 값은 탐색 창에서 서비스를 마우스 오른쪽 단추로 클릭한 다음  **Federation Service** 속성 편집을 선택하여 AD FS 2.0 관리 콘솔에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="fd2ed-227">다음 명령을 실행하여 UseWsFedPassiveAuth 및 WsFedPassiveMetadataUri 값이 올바르게 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="fd2ed-228">클라이언트의 경우 수동 인증은 webticket 인증에 대한 최소 선호 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="fd2ed-229">수동 인증을 사용하도록 설정할 모든 Director, Enterprise Pools 및 Standard Edition 서버에 대해 다음 cmdlet을 실행하여 비즈니스용 Skype 웹 서비스에서 다른 모든 인증 유형을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="fd2ed-230">다음 cmdlet을 실행하여 다른 모든 인증 유형이 사용하지 않도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="fd2ed-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="fd2ed-231">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="fd2ed-231">Proxy Configuration</span></span>

<span data-ttu-id="fd2ed-232">비즈니스용 Skype 웹 서비스에 대해 인증서 인증을 사용하지 않도록 설정하면 비즈니스용 Skype 클라이언트는 덜 선호되는 인증 유형(예: Kerberos 또는 NTLM)을 사용하여 등록자 서비스에 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="fd2ed-233">클라이언트가 웹틱킷을 검색할 수 있도록 허용하려면 인증서 인증이 계속 필요하며, 등록자 서비스에 대해 Kerberos 및 NTLM을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="fd2ed-234">다음 단계에서는 수동 인증을 사용하도록 설정되는 에지 풀, 엔터프라이즈 풀 및 Standard Edition 서버에 대한 사용자 지정 프록시 구성을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="fd2ed-235">사용자 지정 프록시 구성을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="fd2ed-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="fd2ed-236">비즈니스용 Skype 서버 관리 셸 명령줄에서 다음 명령을 실행하여 수동 인증을 사용하도록 설정되는 각 비즈니스용 Skype 서버 에지 풀, 엔터프라이즈 풀 및 Standard Edition 서버에 대해 새 프록시 구성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd2ed-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="fd2ed-237">다음 명령을 실행하여 다른 모든 프록시 인증 유형이 사용하지 않도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="fd2ed-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="fd2ed-238">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd2ed-238">See also</span></span>

[<span data-ttu-id="fd2ed-239">비즈니스용 Skype 서버에서 2단계 인증 관리</span><span class="sxs-lookup"><span data-stu-id="fd2ed-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="fd2ed-240">비즈니스용 Skype 클라이언트 및 비즈니스용 Skype 서버에서 2단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="fd2ed-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)