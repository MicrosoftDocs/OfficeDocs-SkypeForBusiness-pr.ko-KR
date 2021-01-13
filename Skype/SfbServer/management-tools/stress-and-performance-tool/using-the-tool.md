---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 실행하려면 사용자, 연락처 및 사용자 프로필을 모두 관리하고 실행을 위해 도구를 구성한 다음 도구에서 생성한 출력 또는 결과를 검토할 수 있습니다.
ms.openlocfilehash: e008a85d22753a4e649da8501bd387675bb9b536
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814948"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="58414-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용</span><span class="sxs-lookup"><span data-stu-id="58414-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="58414-104">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 실행하려면 사용자, 연락처 및 사용자 프로필을 모두 관리하고 실행을 위해 도구를 구성한 다음 도구에서 생성한 출력 또는 결과를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="58414-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 실행과 관련된 네 가지 영역이 있습니다(실행 LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="58414-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="58414-106">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="58414-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="58414-107">사용자 프로필 구성</span><span class="sxs-lookup"><span data-stu-id="58414-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="58414-108">LyncPerfTool 실행</span><span class="sxs-lookup"><span data-stu-id="58414-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="58414-109">결과 해석</span><span class="sxs-lookup"><span data-stu-id="58414-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="58414-110">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="58414-110">Create Users and Contacts</span></span>
<span data-ttu-id="58414-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="58414-111"><a name="BKMK_CreateUsersAndContacts"> </a></span></span>

<span data-ttu-id="58414-112">비즈니스용 Skype 서버 2015(SB 2015) 사용자 프로비전 도구(UserProvisioningTool.exe)를 사용하여 스트레스 및 성능 테스트를 위한 사용자 및 연락처를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="58414-113">이 목록은 항목을 읽을 때 유용할 수 있는 유용한 용어 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="58414-114">**조직 구성 단위** - AD DS(Active Directory 도메인 서비스) OU(조직 구성 단위)</span><span class="sxs-lookup"><span data-stu-id="58414-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="58414-115">**페더타/크로스** 풀 - 다른 IM(인스턴트 메시징) 서비스의 사용자와 통신할 수 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="58414-116">**메일 목록** - 또는 DLS.</span><span class="sxs-lookup"><span data-stu-id="58414-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="58414-117">AD DS 사용자 목록을 포함하는 AD DS의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="58414-118">사용자 그룹 간 통신을 용이하게 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="58414-119">**위치 정보 서비스** - 전화당 사용하도록 설정하고 구성할 때 E911(Enhanced 911) 서비스의 실제 위치를 검색할 수 있는 비즈니스용 Skype 서버 2015 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="58414-120">**미국 전화** 번호 - RNL(역방향 번호 Lookup)에서 인바운드 및 아웃바운드 호출을 라우팅하는 데 사용되는 SIP URI 외에 사용자에게 할당된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="58414-121">사용자 및 연락처를 사용하여 UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="58414-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="58414-122">시작하기 전에 이 도구를 실행하려면 Domain Admins 보안 그룹의 구성원으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="58414-123">Active Directory 사용자를 만들게 예정이기 때문에 이 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="58414-124">비즈니스용 Skype 서버 사용자 프로비저닝 도구를 사용하여 부하 시뮬레이션을 위한 사용자 및 연락처를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="58414-125">비즈니스용 **Skype 서버 사용자 프로비저닝** 도구는 비즈니스용 Skype 서버 스트레스 및 성능 도구 **패키지와 함께 설치됩니다.**</span><span class="sxs-lookup"><span data-stu-id="58414-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="58414-126">패키지 설치 관리자(CapacityPlanningTool.msi)가 테스트할 프런트 엔드 서버 또는 Standard Edition 서버에서 실행되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="58414-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="58414-127">프런트 엔드 서버 또는 Standard Edition 서버에서 %InstalledDirectory%LyncStressAndPerfTool\LyncStress에 있는 파일 UserProvisioningTool.exe 실행하여 비즈니스용 Skype 서버 사용자 프로비저닝 도구를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58414-128">많은 수의 사용자(예: 10,000명 이상)를 만들 때 10,000명 이상의 사용자를 UserProvisioningTool.exe.</span><span class="sxs-lookup"><span data-stu-id="58414-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="58414-129">이 도구는 새 AD 사용자를 만들고 구성하기 때문에 이 작업을  *해야*  합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="58414-130">사용자 프로비전 도구가 열리면 구성을 클릭하고 구성 로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="58414-131">사용자 및 연락처 구성을 시작하고 패키지에 포함된 기본 파일("SampleData.xml")을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="58414-132">이렇게 하면 배포와 관련성이 있도록 변경해야 하는 예제 데이터가 필드에 미리 채우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="58414-133">이미 사용자 지정된 설정이 포함된 미리 구성한 XML 파일이 있는 경우 해당 파일을 대신 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="58414-134">아래 섹션에 설명된 바와 같이 사용자 프로비전 도구의 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="58414-135">서버 옵션을 구성하는 경우:</span><span class="sxs-lookup"><span data-stu-id="58414-135">To configure server options:</span></span>

1. <span data-ttu-id="58414-136">프런트 엔드 풀 **FQDN** 필드에 Standard Edition 서버의 FQDN(정규화된 도메인 이름) 또는 사용자를 호스팅할 프런트 엔드 풀을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="58414-137">사용자 **이름 Prefix** 필드에 테스트 목적으로 사용자 이름을 버스트하는 데 사용할 (예: "TestUser")를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="58414-138">암호 **필드에** 모든 테스트 사용자 계정에서 사용할 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="58414-139">계정 **도메인** 필드에 현재 AD 도메인의 도메인 이름(테스트 사용자를 만들 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="58414-140">조직 구성 **단위** 필드에 이러한 테스트 사용자를 만들 AD 도메인의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="58414-141">OU가 아직 없는 경우 OU가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="58414-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="58414-142">전화 **영역 코드** 필드에 모든 테스트 사용자 계정에서 사용할 3자리 영역 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="58414-143">선택한 영역 코드가 AD의 다른 사용자의 영역 코드와 충돌하지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="58414-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="58414-144">음성 사용  가능 확인란을 클릭하여 선택합니다. 테스트 사용자가 음성을 사용할 수 있도록 설정하려면 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="58414-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="58414-145">사용자 **수 필드에** 만들 테스트 사용자의 총 수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="58414-146">시작  인덱스 필드에서 사용자 이름 접두사에 접미사로 사용할 시작 번호를 지정합니다. 예를 들어 접두사는 "TestUser"이고 이름은 아래 예제에서 "0"으로 끝날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![사용자 만들기 탭을 표시하는 사용자 프로비전 도구입니다.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="58414-148">사용자 만들기 단추</span><span class="sxs-lookup"><span data-stu-id="58414-148">Create Users button</span></span>

<span data-ttu-id="58414-149">사용자 만들기 단추를 클릭하면 입력한 입력 매개 변수의 유효성이 검사됩니다. </span><span class="sxs-lookup"><span data-stu-id="58414-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="58414-150">유효성 검사 오류가 있는 경우 문제를 해결하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="58414-151">또는 모든 값이 올바른 경우 사용자가 AD(지정한 OU)에 나타나기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="58414-152">도구가 실행될 때 도구 아래쪽에 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="58414-153">진행률 표시줄이 활성화된 동안 응용 프로그램을 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="58414-154">사용자 만들기에는 시간이 걸리기 때문에 그에 따라 계획을 세우면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="58414-155">이 프로세스는 소수의 사용자에 대해 몇 분에서 몇 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="58414-156">테스트 환경에서 AD 도메인 컨트롤러에 액세스할 수 없는 경우 사용자가 만들 때 지정한 범위의 사용자 중 한 명으로 로그인하여 사용자 만들기의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="58414-157">접두사와 접미사는 사용자 이름과 함께 @sipDomain 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="58414-158">예를 들면 다음과 같습니다. <em>TestUser20@contoso.net.</em></span><span class="sxs-lookup"><span data-stu-id="58414-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="58414-159">사용자가 이미 있는 경우 사용자 만들기 단추를 클릭하면 구성 변경 내용으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="58414-160">사용자 삭제 단추</span><span class="sxs-lookup"><span data-stu-id="58414-160">Delete Users button</span></span>

<span data-ttu-id="58414-161">사용자 삭제 단추를 클릭하면 탭의 입력 매개 변수의 유효성이 검사됩니다. </span><span class="sxs-lookup"><span data-stu-id="58414-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="58414-162">유효성 검사 오류가 있는 경우 오류를 수정하라는 메시지가 표시되고 입력 값이 올바른 경우 지정된 테스트 사용자가 사용하지 않도록 설정되고 Active Directory에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="58414-163">이 탭의 맨 아래에 진행률 표시줄이 표시되고 진행률 표시줄이 활성화된 동안에는 응용 프로그램을 닫지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58414-164">미국 형식의 전화 번호만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="58414-165">전화 번호는 항상 사용자에게 할당됩니다. UserProvisioningTool.exe 만든 모든 사용자는 기본적으로 Enterprise Voice 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="58414-166">전화 번호를 사용하는 모든 시나리오(예: 회의 자동 전화 교환 또는 UC-PSTN 통화)는 이 전화 번호를 사용하여 통화를 올바르게 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="58414-167">따라서 모든 *사용자에게* 고유한 전화 *번호가 있어야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="58414-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="58414-168">**사용자를 두 번 만들어야 하는 경우 다른 지역 코드를 사용하지 않는 한 또는 이전 사용자가 Disable-CsUser cmdlet을 사용하여 사용하지 않도록 설정하지 않은 경우 명령이 실패합니다.**</span><span class="sxs-lookup"><span data-stu-id="58414-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58414-169">연락처를 만들기 전에 먼저 사용자 복제를 완료해야 합니다(사용자 탭에서 수행).</span><span class="sxs-lookup"><span data-stu-id="58414-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="58414-170">사용자를 방금 만든 경우 비즈니스용 Skype 서버 복제가 완료된 후 데이터베이스의 사용자 계정을 채우기 전까지 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="58414-171">**사용자가 복제를 완료하지 않은 경우 오류가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="58414-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="58414-172">사용자가 비즈니스용 Skype 서버 2015 프런트 엔드 서비스가 시작된 경우 또는 지정한 총 수의 마지막 사용자에 대해 Get-CsUser cmdlet을 실행하여 복제를 완료한 경우를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="58414-173">연락처 만들기 탭</span><span class="sxs-lookup"><span data-stu-id="58414-173">Contacts Creation tab</span></span>

<span data-ttu-id="58414-174">이 탭에서는 테스트에 대한 사용자의 연락처 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![콘텐츠 만들기 탭을 표시하는 사용자 프로비전 도구입니다.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="58414-176">사용자의 연락처를 구성하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="58414-177">사용자당 **평균** 연락처 필드에 각 사용자의 연락처 목록에 채우는 평균 연락처 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="58414-178">모든 **사용자에** 대해 동일한 수의 연락처를 만들 경우 고정 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="58414-179">사용자에 대해 만들어진 연락처 수를 다양하게 설정하려는 경우 해당 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="58414-180">사용자당 평균 연락처 그룹 **필드에** 사용자당 연락처 그룹 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="58414-181">이 수는 사용자당 평균 연락처 수보다 **작아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="58414-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="58414-182">**페더티드/교차** 풀 연락처 백분율 필드에 0에서 100 사이의 숫자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="58414-183">이 백분율의 연락처는 페더화 사용자와 함께 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="58414-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="58414-184">**페더러티/교차** 풀 사용자 접두사 필드에 로컬 사용자의 연락처 목록에 추가할 페더티된 사용자의 사용자 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="58414-185">**페더러티/교차** 풀 사용자 SIP 도메인 필드에 페더화 사용자의 SIP 도메인 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="58414-186">사용자 **만들기 탭에서** 정보가 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="58414-187">사용자 만들기 탭의 값으로 연락처가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="58414-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="58414-188">연락처 **만들기를 클릭하여** 연락처 만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="58414-189">이 프로세스는 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-189">This process can take several minutes.</span></span> <span data-ttu-id="58414-190">작업이 완료되면 "Operation Completed Successfully"라는 메시지와 함께 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="58414-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="58414-191">사용자 만들기 탭에서 만든 사용자로 로그온하여 만든 연락처의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="58414-192">연락처를 만든 후 이 도구는 대상 풀의 모든 프런트 엔드 서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="58414-193">이 작업을 통해 만들어진 연락처 수에 따라 프런트 엔드 서버가 시작되는 데는 최대 2시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="58414-194">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="58414-194">Distribution List</span></span>

<span data-ttu-id="58414-195">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 비즈니스용 Skype 2015 클라이언트의 DL(메일 목록) 확장 기능을 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="58414-196">사용자 프로비전 도구에서 DL 확장을 사용하도록 설정하지 않은 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![메일 목록 만들기 탭을 표시하는 사용자 프로비전 도구입니다.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="58414-198">메일 목록 탭에서는 스트레스 및 성능 도구가 메일 목록 확장 기능에 사용할 DLS를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="58414-199">DLS를 만들기 전에 ForestPrep 실행을 포함하여 비즈니스용 Skype 서버 2015를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="58414-200">이렇게 하지 않은 경우 DL 특성이 AD schema에 존재하지 않습니다. 따라서 도구에서 DLS를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="58414-201">메일 목록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="58414-202">메일  목록 수 필드에 만들 총 DLS 수를 제공합니다(여기서 권장되는 것은 사용자 수의 2배인 값으로 시작하는 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="58414-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="58414-203">메일 **목록 Prefix** 필드에 만든 모든 DLS에 사용할 수 있는 prefix를 입력합니다(예: *testDL).*</span><span class="sxs-lookup"><span data-stu-id="58414-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="58414-204">즉, 100 DLS에서 DL 이름은 testDL0, testDL1, testDL99와 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="58414-205">**Dist의** 최소 구성원. 목록 필드에 각 DL에 넣을 최소 사용자 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="58414-206">**Dist의 최대** 구성원 수. 목록 필드에 각 DL에 추가할 최대 사용자 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="58414-207">메일 목록 만들기 단추</span><span class="sxs-lookup"><span data-stu-id="58414-207">Create Distribution Lists button</span></span>

<span data-ttu-id="58414-208">메일 사용자 목록 만들기 단추를 클릭하면 이 도구는 Active Directory를 쿼리하여 해당 번호와 일치하는 메일 목록이 이미 존재하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="58414-209">이 도구는 존재하지 않는 DLS를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58414-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="58414-210">새로 만든 메일 그룹에 구성원을 추가할 때 사용자 만들기 탭에 지정된 범위에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="58414-211">위치 정보 서비스 구성 탭</span><span class="sxs-lookup"><span data-stu-id="58414-211">Location Info Service Config tab</span></span>

<span data-ttu-id="58414-212">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 위치 정보 서비스에 대한 더미 구성 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="58414-213">위치 정보 서비스는 일반적으로 서버에 큰 영향을 미치는 성능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![위치 정보 서비스 구성 탭을 보여주는 사용자 프로비전 도구입니다.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="58414-215">이 기능을 테스트하도록 선택한 경우 양식의 값을 입력하고 LIS 구성 파일 생성 단추를 클릭하면 생성됩니다. 호출되는 CSV 파일:</span><span class="sxs-lookup"><span data-stu-id="58414-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="58414-216">LIS_Subnet.csv</span><span class="sxs-lookup"><span data-stu-id="58414-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="58414-217">LIS_Switches.csv</span><span class="sxs-lookup"><span data-stu-id="58414-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="58414-218">LIS_Ports.csv</span><span class="sxs-lookup"><span data-stu-id="58414-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="58414-219">LIS_WAP.csv</span><span class="sxs-lookup"><span data-stu-id="58414-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="58414-220">LIS 데이터베이스로 이러한 파일을 가져오기 위해 다음 PowerShell cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="58414-221">Set-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="58414-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="58414-222">Set-CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="58414-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="58414-223">Set-CsLisPort</span><span class="sxs-lookup"><span data-stu-id="58414-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="58414-224">Set-CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="58414-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="58414-225">사용자 프로필 구성</span><span class="sxs-lookup"><span data-stu-id="58414-225">Configure User Profile</span></span>
<span data-ttu-id="58414-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="58414-226"><a name="BKMK_UserProfile"> </a></span></span>

<span data-ttu-id="58414-227">사용자 만들기 도구를 통해 사용자를 만든 후 비즈니스용 Skype 서버 2015 부하 구성 도구(UserProfileGenerator.exe)를 사용하여 사용자 프로필을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="58414-228">비즈니스용 Skype 서버 2015 부하 구성 도구 실행</span><span class="sxs-lookup"><span data-stu-id="58414-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="58414-229">로드 구성 도구(UserProfileGenerator.exe)를 시작하고 탭을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="58414-230">이 도구는 시뮬레이션을 실행해야 하는 각 클라이언트 컴퓨터에 대한 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58414-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="58414-231">각 클라이언트 디렉터리에는 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구(2015 스트레스 및 성능 도구)를 시작하는 스크립트가 LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="58414-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="58414-232">아래 섹션에서는 비즈니스용 Skype 서버 2015 부하 구성 도구의 각 탭에 있는 필드를 채우는 방법의 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58414-233">UserProfileGenerator.exe(부하 구성 도구)에 사용되는 사용자별 값은 풀에 대한 비즈니스용 Skype 서버 2015 사용자 만들기 도구(UserProvisioningTool.exe)에 지정된 값과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="58414-234">일반 구성 탭</span><span class="sxs-lookup"><span data-stu-id="58414-234">Common Configuration tab</span></span>

<span data-ttu-id="58414-235">로드 **구성 도구의** 일반 구성 탭은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="58414-236">다음 단계에 설명된 바와 같이 일반 구성 탭의 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![일반 구성 탭을 표시하는 사용자 프로비전 탭입니다.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="58414-238">사용 **가능한** 컴퓨터 수 필드에 스트레스 및 성능 도구를 실행하기 위해 사용할 컴퓨터 수를 LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="58414-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="58414-239">시뮬레이션할 사용자 4500명마다 한 대의 컴퓨터를 사용하는 것이 되지만 부하 수준을 줄이거나 도구에서 사용할 수 있는 기능의 일부만 사용하는 경우 이 수치가 달라질 수 있습니다(로드 수준은 일반 시나리오 탭에 설정).</span><span class="sxs-lookup"><span data-stu-id="58414-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="58414-240">사용자 **이름의 Prefix for User Names(사용자** 이름) 필드에 모든 사용자의 사용자 이름 필드에 대한 사전을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="58414-241">URI(Uniform Resource Identifier)에 로그인하려면 *UserPrefix[User Start Index... (사용자 수-1)] @User*  도메인(예: myUser009@Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="58414-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="58414-242">모든 **사용자에 대한 암호 필드에** 사용자를 만들 때 사용되는 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="58414-243">이 필드를 비워 두면 사용자 이름이 암호로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="58414-244">사용자 시작 **인덱스** 필드에 구성할 첫 번째 사용자의 인덱스를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="58414-245">부하 유형이나 수준에 따라 서로 다른 범위를 구성할 수 있지만 구성하려는 범위당 한 번씩 로드 구성 도구(UserProfileGenerator.exe)를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="58414-246">사용자 **수 필드에** 구성할 총 사용자 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="58414-247">사용자 **도메인 필드에** SIP URI에 사용되는 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="58414-248">이는 비즈니스용 Skype 서버 2015 프런트 엔드 서버 또는 Standard Edition 서버에 로그온하기 위해 각 사용자의 SIP URI를 생성하는 데 사용하며 계정 도메인과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="58414-249">계정 도메인 **필드에** AD DS 도메인 로그온을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="58414-250">**MPOP** 백분율(여러 현재 상태 지점 백분율) 필드에서 여러 컴퓨터 또는 장치에서 로그온한 사용자의 백분율(예: 10%)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="58414-251">인스턴스당 로그인 수(인스턴스당)에 최대 동시 **끝점** 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="58414-252">이는 사용자에 대한 최대 로그인 수로, 권장되는 속도는 초당 2(<=2)보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="58414-253">액세스 프록시 또는 풀 **FQDN** 필드에 클라이언트가 연결할 서버의 FQDN(정식 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="58414-254">사용자가 외부에서 로그온하는 경우 액세스 프록시를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="58414-255">사용자가 내부에 있는 경우 해당 Enterprise Pool 또는 Standard Edition 서버의 FQDN을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="58414-256">포트 **필드에** 사용자가 SIP에 사용할 포트를 입력합니다(기본값은 5061).</span><span class="sxs-lookup"><span data-stu-id="58414-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="58414-257">외부 네트워크 **서버 설정** 필드의 경우 액세스 프록시 또는 풀 FQDN을 부여하고 포트를 다시 **제공합니다.**</span><span class="sxs-lookup"><span data-stu-id="58414-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="58414-258">이러한 설정은 외부 끝점 로드 시뮬레이션에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="58414-259">일반 시나리오 탭</span><span class="sxs-lookup"><span data-stu-id="58414-259">General Scenarios tab</span></span>

![일반 시나리오 탭을 표시하는 로드 구성 도구](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="58414-261">실행하거나 사용하지 않도록 설정할 시나리오를 결정하여 제공되는 각 일반 시나리오에 대한 로드 수준 및 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="58414-262">다음은 일반적인 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="58414-263">로컬 정보 서비스를 사용하지 않도록 설정, 낮음,  중간, 높음 또는 사용자 지정 필드를 사용하지 않도록 설정한 모든 필드의 로드 **수준** **값** </span><span class="sxs-lookup"><span data-stu-id="58414-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="58414-264">설정을 선택하지만 사용 안 하게 설정하면 각 클라이언트에 대한 구성이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="58414-265">높은 결과로 서버에서 지원되는 최대 부하가 증가합니다. 중간 크기는 높은 부하의 60%입니다. 낮음은 30%입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="58414-266">**인스턴트 메시징 -** 여기에는 피어 투 피어 및 회의가 포함됩니다. 부하 수준에 적합한 값을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="58414-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="58414-267">**오디오 회의 -** 오디오 회의에 대한 로드 수준만 *선택 합니다.*</span><span class="sxs-lookup"><span data-stu-id="58414-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="58414-268">피어 투 피어 통화는 음성 시나리오 섹션에서 약간 까다로우면 됩니다. </span><span class="sxs-lookup"><span data-stu-id="58414-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="58414-269">고급 **탭을 열고** MultiView를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="58414-270">**응용 프로그램 공유 -** 응용 프로그램 공유에 대한 로드 수준을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="58414-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="58414-271">**데이터 공동 작업 -** 데이터 회의를 포함하는 데이터 공동 작업의 로드 수준을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="58414-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="58414-272">**메일 목록 확장 -** 고급 **단추를** 클릭하고 사용자 만들기 도구(사용자 만들기 도구)의 DL 탭에 구성된 값과 동일한 값으로 필드를 UserProvisioningTool.exe.</span><span class="sxs-lookup"><span data-stu-id="58414-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="58414-273">부하 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-273">Choose a load level.</span></span>
    
- <span data-ttu-id="58414-274">**주소부 웹 쿼리 -** 이 서비스는 주소부 파일 다운로드가 아닌 주소부 Lookup Service입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="58414-275">주소부 파일 다운로드에 이 기능을 사용하도록 설정하려면 고급 단추를 클릭하고 **EnableABSDownload를** True로 설정하십시오. </span><span class="sxs-lookup"><span data-stu-id="58414-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="58414-276">부하 수준에 대한 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="58414-277">**응답 그룹 서비스 -** 고급 **단추를** 클릭하고 에이전트를 프로비전할 때 이미 만든 응답 그룹의 응답 그룹 서비스 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="58414-278">하나 이상의 응답 그룹을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-278">You must choose at least one response group.</span></span> <span data-ttu-id="58414-279">더 많이 사용하기 위해 응답 그룹을 세미코론으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="58414-280">**RGSUriSuffixStartIndex** 및 **RGSUriSuffixEndIndex를** 실제 값으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="58414-281">부하 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-281">Choose a load level.</span></span>
    
- <span data-ttu-id="58414-282">**위치 정보 서비스 -** 사용 또는 사용 안신의 부하 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58414-283">각 시나리오에는 옆에 고급 단추와 기본 설정에 대한 변형을 사용하도록 설정하는 확인란 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="58414-284">*Ad-hoc를 선택하면* 도구가 1시간 내내 생성되는 회의 시뮬레이션을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="58414-285">Large  *Conf를 선택하면*  대규모 회의 시나리오가 시뮬레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="58414-286">*외부에서*  외부 사용자도 시뮬레이트할 수 있도록 도구에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="58414-287">이러한 단추와 확인란은 각 시나리오에 대한 추가 값으로, 스트레스 및 성능 도구의 동작을 변경하고 사용자 지정을 가능하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="58414-288">일반 시나리오 탭(위치 정보 서비스 제외)의 각 시나리오에 대해 부하 수준 값이 사용자 지정인 경우 대화 속도는 고급 대화 상자의 해당 필드를 사용하여 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="58414-289">필드 이름은 시나리오에 따라 다를 수 있지만 필드 설명은 상태입니다. 참고: 이 번호는 드롭다운 메뉴에서 사용자 지정을 선택한 *경우만 사용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="58414-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="58414-290">높음, 중간 및 낮음 값은 모든 시나리오의 균형을 이루는 사용자 모델에 따라 부호당 대화 비율을 변경합니다. </span><span class="sxs-lookup"><span data-stu-id="58414-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="58414-291">예상 사용량의 차이로 인해 부호당 로드 수준을 변경해야 하는 경우 사용자 지정 대화 비율을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="58414-292">음성 시나리오 탭</span><span class="sxs-lookup"><span data-stu-id="58414-292">Voice Scenarios tab</span></span>

<span data-ttu-id="58414-293">이 탭은 모든 음성 관련 시나리오를 구성하기 위한 탭입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![구성 도구 음성 시나리오 로드 탭](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="58414-295">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-295">Your options are:</span></span>
  
- <span data-ttu-id="58414-296">**VoIP -** 고급 **단추를** 클릭하고 PhoneAreaCode 및 LocationProfile(다이얼 플랜) 필드에 대한 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="58414-297">부하 수준에 대한 값도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="58414-298">VoIP 또는 UC/PSTN 게이트웨이의 부하 수준을 선택하면 외부 통화를 시뮬레이트하기 위해 UC(통합 통신) 구성 파일로의 PSTN(공용 전화망)이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="58414-299">**UC/PSTN 게이트웨이 -** 부하 수준 값을 선택해야 합니다. 사용 안 하게 를 선택할 때 고급 단추를 클릭하여 PSTN 영역 코드에 대한 값도 **제공해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="58414-300">중재 **서버** 및 PSTN 아래에서 추가를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="58414-301">지역 코드에 대한 경로가 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="58414-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="58414-302">비즈니스용 Skype 제어판 또는 비즈니스용 Skype 관리 셸을 사용하여 음성 경로 구성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="58414-303">**회의 참석자 -** 부하 수준 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="58414-304">Disabled 외의 값은 전화 번호 **필드를 사용하도록** 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="58414-305">사용할 자동 전화 교환 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="58414-306">**고급을** 클릭하고 **LocationProfile** 필드에 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="58414-307">**통화 파킹 서비스 -** 여기서 부하 수준을 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="58414-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="58414-308">**중재 서버 및 PSTN -** 사용하려는 각 중재 서버에는 자체 PSTN 시뮬레이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="58414-309">시뮬레이터에 사용할 클라이언트를 결정한 후 구성한 PSTN 시뮬레이터에서 해당 컴퓨터로 통화를 라우팅하도록 중재 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="58414-310">추가 **단추를** 클릭하여 중재 서버에 대한 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="58414-311">각 시나리오 옆에 고급 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="58414-312">고급 대화 상자에는 스트레스 및 성능 도구의 동작을 변경하고 사용자 지정을 사용하도록 설정하는 각 시나리오에 대한 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="58414-313">> 시나리오 탭의 각 시나리오에 대해 로드 수준 값이 사용자 지정인 경우 대화 속도는 고급 대화 상자의 해당 필드를 사용하여 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="58414-314">필드 이름은 시나리오에 따라 다를 수 있지만 필드 설명은 상태입니다. 참고: 이 번호는 드롭다운 메뉴에서 사용자 지정을 선택한 *경우만 사용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="58414-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="58414-315">Web App 탭</span><span class="sxs-lookup"><span data-stu-id="58414-315">Web App tab</span></span>

![구성 도구 로드, 웹앱 탭.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="58414-317">Web App은 프런트 엔드 서버에 설치된 UCWA(Unified Communications Web API) 서버를 통해 회의 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="58414-318">Web App 탭을 사용하여 모든 웹앱 관련 시나리오를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="58414-319">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-319">Options are:</span></span>
  
- <span data-ttu-id="58414-320">**일반 웹앱 설정 -** 추가 **설정** 단추를 클릭하고 **ReachTargetServerUrl을** 프런트 엔드 풀 VIP의 디렉터리 풀 VIP(가상 IP)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="58414-321">**응용 프로그램 공유 -** 부하 수준 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="58414-322">**데이터 공동 작업 -** 부하 수준 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="58414-323">**인스턴트 메시징 -** 부하 수준 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="58414-324">**음성 회의 -** 부하 수준 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58414-325">각 시나리오에는 그 **옆에** 고급 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="58414-326">고급 대화 상자에는 스트레스 및 성능 도구의 동작을 변경하고 customization.> 각 Web App 시나리오에 대해 로드 수준이 **사용자** 지정인 경우 **ConversationsPerHour** 필드에 지정된 값이 기본값 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="58414-327">이동성 탭</span><span class="sxs-lookup"><span data-stu-id="58414-327">Mobility tab</span></span>

<span data-ttu-id="58414-328">이 탭을 사용하여 모든 모바일 관련 시나리오를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![구성 도구 이동성 탭을 로드합니다.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="58414-330">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-330">The options here are:</span></span>
  
- <span data-ttu-id="58414-331">**일반 이동성 설정 -** 추가 **설정을 클릭하고** UcwaTargetServerUrl 필드를 DIRECTOR 풀 VIP(가상 IP) 또는 프런트 엔드 풀 VIP로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="58414-332">**현재 상태 및 P2P 인스턴트 메시징/오디오 -** 모바일 시뮬레이션을 사용하도록 설정하려면 부하 수준 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58414-333">각 시나리오에는 그 **옆에** 고급 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="58414-334">고급 대화 상자에는 스트레스 및 성능 도구의 동작을 변경하고 사용자 지정을 사용하도록 설정하는 각 시나리오에 대한 값이 포함되어 있습니다.> 각 모바일 시나리오에서 부하 수준이 **사용자** 지정인 경우 **ConversationsPerHour** 필드에 지정된 값이 기본값이 아닌 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="58414-335">요약 탭</span><span class="sxs-lookup"><span data-stu-id="58414-335">Summary tab</span></span>

<span data-ttu-id="58414-336">요약 탭에는 각 시나리오에 사용할 사용자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![로드 구성 도구 요약 탭](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="58414-338">요약 탭에는 각 시나리오에 사용할 사용자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="58414-339">사용자 지정 사용자 범위 생성 사용 확인란을  선택한 다음 사용자 지정할 사용자 범위가 있는 표에서 시나리오를 두 번 클릭하여 사용자 번호 범위를 수동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="58414-340">**확인(RunClient.bat)** 생성된 일괄 파일에 로그인 속도에 해당하는 지연을 포함하려면 시작할 때 로그인 지연을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="58414-341">이는 많은 수의 사용자가 로그인할 때 서버 오버로드를 방지하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="58414-342">파일 **생성을 클릭하고** 구성을 생성할 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="58414-343">파일이 성공적으로 만들어지면 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="58414-343">A dialog box will appear when your files have been successfully created.</span></span>
  
!['구성 파일을 로드했습니다. 성공적으로 생성되었습니다.' 메시지 상자](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="58414-346">LyncPerfTool 실행</span><span class="sxs-lookup"><span data-stu-id="58414-346">Run LyncPerfTool</span></span>
<span data-ttu-id="58414-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="58414-347"><a name="BKMK_RunTool"> </a></span></span>

<span data-ttu-id="58414-348">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구(LyncPerfTool.exe)를 실행하기 전에 사용자, 연락처 및 시나리오를 만들어야 LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="58414-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="58414-349">도구를 사용하여 이러한 작업을 수행하는 데 대한 자세한 내용은 이 문서의 이전 문서에서 사용자 및 연락처 [만들기](using-the-tool.md#BKMK_CreateUsersAndContacts) 및 사용자 프로필 [구성을](using-the-tool.md#BKMK_UserProfile) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58414-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="58414-350">이러한 도구를 실행하면 필수 매개 변수가 포함된 배치 파일의 일부로 스트레스 및 성능 도구로 실행되는 파일도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="58414-351">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 실행</span><span class="sxs-lookup"><span data-stu-id="58414-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="58414-352">부하 구성 도구(UserProfileGenerator.exe)는 성능 카운터를 등록하고 XML 구성 파일을 로드하여 스트레스 및 성능 도구(LyncPerfTool.exe)를 실행할 수 있는 배치 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58414-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="58414-353">일괄 처리 파일은 구성 파일당 LyncPerfTool.exe 인스턴스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="58414-354">배치 파일을 실행하기 위해 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="58414-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="58414-355">스트레스 및 성능 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="58414-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="58414-356">구성 폴더와 파일이 있는 폴더를 각 클라이언트 컴퓨터에 있는 디렉터리에 LyncPerfTool.exe 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="58414-357">예를 들어 1.28_13.16.16 폴더에 구성 파일을 생성한 경우 폴더에 구성 파일이 있는 LyncPerfTool.exe 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="58414-358">각 클라이언트에서 이 작업을 실행합니다.)</span><span class="sxs-lookup"><span data-stu-id="58414-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="58414-359">클라이언트 폴더로 이동하여 **RunClient 일괄** 처리 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="58414-360">Windows 탐색기에서 배치 파일을 두 번 클릭하면 해당 클라이언트에 대한 모든 구성 파일이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="58414-361">다음 구문을 사용하여 클라이언트 폴더에서 스크립트를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="58414-362">스트레스 및 성능 도구를 직접 실행하려면 명령 프롬프트를 열고 명령줄에 다음 명령을 입력합니다.(이 작업을 처음 실행할 때 이 항목의 부분에 나와 있는처럼 성능 카운터를 등록해야  `regsvr32 /i /n /s LyncPerfToolPerf.dll` 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="58414-363">도구에서 구성 파일에 값을 표시하려면 앞의 명령에 매개 변수를 포함하여 다음과  `/displayfile` 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="58414-364">프로세스를  *종료하기*  위해 Ctrl+C를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58414-365">스트레스 및 성능 도구를 직접 실행하기 전에 다음 명령을 통해 성능 카운터를 등록해야 합니다.  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="58414-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="58414-366">시작하는 스트레스 및 성능 도구의 모든 인스턴스는 일반적으로 초당 한 사용자씩 사용자 로그인을 즉시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="58414-367">풀의 최대 사용자 로그인 속도는 초당 약 12개입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="58414-368">즉, 사용자가 계속 로그인하는 동안 12개 이상의 LyncPerfTool.exe 인스턴스를 동시에 시작하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="58414-369">초당 1000명의 사용자가 완전히 로그인하는 데 20분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="58414-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="58414-370">결과 해석</span><span class="sxs-lookup"><span data-stu-id="58414-370">Interpreting the Results</span></span>
<span data-ttu-id="58414-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="58414-371"><a name="BKMK_Interpret"> </a></span></span>

<span data-ttu-id="58414-372">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에는 클라이언트의 작업과 문제가 발생하는지 여부를 이해하는 데 도움이 되는 많은 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="58414-373">클라이언트 카운터</span><span class="sxs-lookup"><span data-stu-id="58414-373">Client Counters</span></span>

<span data-ttu-id="58414-374">실행 중인 LyncPerfTool.exe 인스턴스마다 별도의 카운터 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="58414-375">각 인스턴스의 이름은 프로세스 ID로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="58414-376">클라이언트가 오버로드된 경우 다른 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="58414-377">이러한 문제를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="58414-378">클라이언트 컴퓨터에서 CPU 및 메모리 사용량을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="58414-379">CPU가 지속적으로 90%를 넘는 경우 사용자 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="58414-380">메모리 공간이 높을 때 페이지 파일이 공간이 부족하기 시작하면 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="58414-381">커밋 청구가 컴퓨터의 제한에 도달하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="58414-382">메모리 한도를 실행하는 경우 페이지 파일 크기를 늘리거나 사용자 수를 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="58414-383">주요 성능 카운터 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="58414-384">**일반 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-384">**General Information**</span></span>

|<span data-ttu-id="58414-385">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-385">**Performance Counter**</span></span>|<span data-ttu-id="58414-386">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-387">소요된 시간(분)입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="58414-388">프로세스가 시작된 이후로 소요된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="58414-389">활성 끝점</span><span class="sxs-lookup"><span data-stu-id="58414-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="58414-390">현재 서버에 연결된 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="58414-391">실패한 로그 로그</span><span class="sxs-lookup"><span data-stu-id="58414-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="58414-392">끝점 로그인 실패의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="58414-393">로그온 시도</span><span class="sxs-lookup"><span data-stu-id="58414-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="58414-394">끝점 로그인 시도의 총 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="58414-395">끝점 연결이 끊어진 경우</span><span class="sxs-lookup"><span data-stu-id="58414-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="58414-396">연결이 끊어진 총 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="58414-397">**현재 상태 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-397">**Presence Information**</span></span>

|<span data-ttu-id="58414-398">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-398">**Performance Counter**</span></span>|<span data-ttu-id="58414-399">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-400">SetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="58414-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="58414-401">현재 상태 변경 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-401">Total number of presence change attempts.</span></span> <span data-ttu-id="58414-402">다양한 유형의 현재 상태 변경에 대한 자세한 내용은 SetPresence(Presence Type) 호출 성능 카운터를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="58414-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="58414-403">SetPresence에 대한 NNN 응답</span><span class="sxs-lookup"><span data-stu-id="58414-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="58414-404">서버에서 받은 nnn 응답 코드의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="58414-405">GetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="58414-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="58414-406">현재 상태 요청 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="58414-407">GetPresence에 대한 NNN 응답</span><span class="sxs-lookup"><span data-stu-id="58414-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="58414-408">서버에서 받은 nnn 응답 코드의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="58414-409">**주소부 서비스 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-409">**Address Book service information**</span></span>

|<span data-ttu-id="58414-410">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-410">**Performance Counter**</span></span>|<span data-ttu-id="58414-411">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-412">ABS 전체/델타 파일 다운로드 시도</span><span class="sxs-lookup"><span data-stu-id="58414-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="58414-413">시도된 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-414">ABS 전체/델타 파일 다운로드 성공</span><span class="sxs-lookup"><span data-stu-id="58414-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="58414-415">시도된 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-416">주소부 웹 쿼리 서비스 관련 카운터</span><span class="sxs-lookup"><span data-stu-id="58414-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="58414-417">주소부 파일 다운로드 관련 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="58414-418">ABS WS 호출 시도</span><span class="sxs-lookup"><span data-stu-id="58414-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="58414-419">시도된 총 주소부 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-420">ABS WS 호출 성공</span><span class="sxs-lookup"><span data-stu-id="58414-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="58414-421">성공적인 응답 코드를 반환한 총 주소 책 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="58414-422">ABS WS 호출 실패</span><span class="sxs-lookup"><span data-stu-id="58414-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="58414-423">오류 응답 코드를 반환한 총 주소 번호부 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="58414-424">이 범주에는 ABS(주소 책 서비스) 파일 다운로드 및 주소부 웹 쿼리 서비스 요청을 모니터링하는 데 사용되는 카운터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="58414-425">**DL(메일 목록) 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="58414-426">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-426">**Performance Counter**</span></span>|<span data-ttu-id="58414-427">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-428">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="58414-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="58414-429">시도된 DLX(메일 목록 확장) 웹 서비스 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-430">Calls Succeeded</span><span class="sxs-lookup"><span data-stu-id="58414-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="58414-431">성공적인 응답 코드를 반환한 DLX 웹 서비스 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="58414-432">통화 실패</span><span class="sxs-lookup"><span data-stu-id="58414-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="58414-433">오류 응답 코드를 반환한 DLX 웹 서비스 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="58414-434">아래에 나열된 성능 카운터는 중재 서버, A/V 회의 서버, 에지 서버, 응답 그룹 응용 프로그램 및 전화 회의를 비롯한 모든 VoIP(Voice over IP) 통화에 대한 번호를 보고하며, 이러한 시나리오를 사용할 자동 전화 교환 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58414-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="58414-435">**VoIP 기본 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="58414-436">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-436">**Performance Counter**</span></span>|<span data-ttu-id="58414-437">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-438">활성 통화</span><span class="sxs-lookup"><span data-stu-id="58414-438">Calls Active</span></span>  <br/> |<span data-ttu-id="58414-439">현재 진행 중인 수신/수신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="58414-440">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="58414-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="58414-441">이미 종료된 수신/수신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="58414-442">Calls Declined</span><span class="sxs-lookup"><span data-stu-id="58414-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="58414-443">수신 음성 통화의 총 수가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="58414-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="58414-444">수신/전화 걸기 시도</span><span class="sxs-lookup"><span data-stu-id="58414-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="58414-445">시도된 총 수신/걸기 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-446">수신/수신 전화 설정</span><span class="sxs-lookup"><span data-stu-id="58414-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="58414-447">설정한 총 수신/걸기 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="58414-448">Received NNN 호출</span><span class="sxs-lookup"><span data-stu-id="58414-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="58414-449">서버에서 받은 nnn 응답 코드의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="58414-450">VoIP 통과 속도(%)</span><span class="sxs-lookup"><span data-stu-id="58414-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="58414-451">시도된 총 통화 수 설정/총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="58414-452">**응답 그룹 서비스 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="58414-453">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-453">**Performance Counter**</span></span>|<span data-ttu-id="58414-454">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-455">활성 통화</span><span class="sxs-lookup"><span data-stu-id="58414-455">Calls Active</span></span>  <br/> |<span data-ttu-id="58414-456">응답 그룹 응용 프로그램에 대한 총 활성 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="58414-457">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="58414-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="58414-458">시도된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="58414-459">**IM(인스턴트 메시징) 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="58414-460">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-460">**Performance Counter**</span></span>|<span data-ttu-id="58414-461">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-462">활성 통화</span><span class="sxs-lookup"><span data-stu-id="58414-462">Calls Active</span></span>  <br/> |<span data-ttu-id="58414-463">지속적인 수신/전송 인스턴트 메시징 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="58414-464">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="58414-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="58414-465">이미 종료된 수신/전송 인스턴트 메시징 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="58414-466">Received NNN 호출</span><span class="sxs-lookup"><span data-stu-id="58414-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="58414-467">서버에서 받은 nnn 응답 코드의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="58414-468">수신/보낸 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="58414-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="58414-469">모든 세션에 대해 수신되거나 전송된 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="58414-470">수신/전화 걸기 시도</span><span class="sxs-lookup"><span data-stu-id="58414-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="58414-471">시도된 총 수신/전송 인스턴트 메시징 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-472">수신/수신 전화 설정</span><span class="sxs-lookup"><span data-stu-id="58414-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="58414-473">설정한 수신/전송 인스턴트 메시지 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="58414-474">**앱 공유 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="58414-475">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-475">**Performance Counter**</span></span>|<span data-ttu-id="58414-476">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-477">활성 통화</span><span class="sxs-lookup"><span data-stu-id="58414-477">Calls Active</span></span>  <br/> |<span data-ttu-id="58414-478">진행되는 총 수신/호출 응용 프로그램 공유 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="58414-479">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="58414-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="58414-480">이미 종료된 수신/종료된 총 응용 프로그램 공유 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="58414-481">Received NNN 호출</span><span class="sxs-lookup"><span data-stu-id="58414-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="58414-482">서버에서 받은 nnn 응답 코드의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="58414-483">수신/전화 걸기 시도</span><span class="sxs-lookup"><span data-stu-id="58414-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="58414-484">시도된 총 수신/호출 응용 프로그램 공유 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-485">수신/수신 전화 설정</span><span class="sxs-lookup"><span data-stu-id="58414-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="58414-486">설정한 총 수신/호출 응용 프로그램 공유 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="58414-487">**CAA 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-487">**CAA Call Information**</span></span>

|<span data-ttu-id="58414-488">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-488">**Performance Counter**</span></span>|<span data-ttu-id="58414-489">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-490">활성 통화</span><span class="sxs-lookup"><span data-stu-id="58414-490">Calls Active</span></span>  <br/> |<span data-ttu-id="58414-491">현재 진행 중인 PSTN(수신/유선 전화망) 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="58414-492">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="58414-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="58414-493">이미 종료된 수신/수신 PSTN 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="58414-494">수신/전화 걸기 시도</span><span class="sxs-lookup"><span data-stu-id="58414-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="58414-495">시도된 수신/유출 PSTN 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="58414-496">수신/수신 전화 설정</span><span class="sxs-lookup"><span data-stu-id="58414-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="58414-497">설정한 수신/유출 PSTN 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="58414-498">**회의 정보**</span><span class="sxs-lookup"><span data-stu-id="58414-498">**Conference Information**</span></span>

|<span data-ttu-id="58414-499">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-499">**Performance Counter**</span></span>|<span data-ttu-id="58414-500">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-501">활성 인스턴트 메시징 회의</span><span class="sxs-lookup"><span data-stu-id="58414-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="58414-502">진행되는 총 인스턴트 메시징 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="58414-503">활성 오디오/비디오 회의</span><span class="sxs-lookup"><span data-stu-id="58414-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="58414-504">진행되는 총 A/V(오디오/비디오) 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="58414-505">활성 응용 프로그램 공유 회의</span><span class="sxs-lookup"><span data-stu-id="58414-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="58414-506">진행되는 총 응용 프로그램 공유 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="58414-507">참가자 수</span><span class="sxs-lookup"><span data-stu-id="58414-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="58414-508">현재 전화 회의에 연결된 총 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="58414-509">회의 일정 실패</span><span class="sxs-lookup"><span data-stu-id="58414-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="58414-510">회의를 예약하는 동안의 총 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="58414-511">회의 참가 실패</span><span class="sxs-lookup"><span data-stu-id="58414-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="58414-512">전화 회의에 연결하는 동안의 총 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="58414-513">**UCWA 클라이언트 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="58414-514">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="58414-514">**Performance Counter**</span></span>|<span data-ttu-id="58414-515">**설명**</span><span class="sxs-lookup"><span data-stu-id="58414-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58414-516">성공한 총 IMMCU 조인 수</span><span class="sxs-lookup"><span data-stu-id="58414-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="58414-517">참가한 총 인스턴트 메시징 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="58414-518">성공한 총 DMCU 조인 수</span><span class="sxs-lookup"><span data-stu-id="58414-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="58414-519">참가한 총 A/V 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58414-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

