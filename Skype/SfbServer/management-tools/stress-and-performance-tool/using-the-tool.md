---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 실행 하려면 사용자, 연락처 및 사용자 프로필을 모두 관리 하 고, 실행할 도구를 구성한 다음 도구에 의해 생성 되는 출력 또는 결과를 검토 해야 합니다.
ms.openlocfilehash: 0bdffee133e583ebaf4177d3226479838495c69f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888867"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="98a03-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용</span><span class="sxs-lookup"><span data-stu-id="98a03-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="98a03-104">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 실행 하려면 사용자, 연락처 및 사용자 프로필을 모두 관리 하 고, 실행할 도구를 구성한 다음 도구에 의해 생성 되는 출력 또는 결과를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="98a03-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 실행 하는 데는 네 가지 영역이 있습니다 (실행 파일은 L Cperftool. exe).</span><span class="sxs-lookup"><span data-stu-id="98a03-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="98a03-106">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="98a03-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="98a03-107">사용자 프로필 구성</span><span class="sxs-lookup"><span data-stu-id="98a03-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="98a03-108">L Cperf도구 실행</span><span class="sxs-lookup"><span data-stu-id="98a03-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="98a03-109">결과 해석</span><span class="sxs-lookup"><span data-stu-id="98a03-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="98a03-110">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="98a03-110">Create Users and Contacts</span></span>
<span data-ttu-id="98a03-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="98a03-111"><a name="BKMK_CreateUsersAndContacts"> </a></span></span>

<span data-ttu-id="98a03-112">스트레스 및 성능 테스트를 위해 사용자 및 연락처를 만들려면 비즈니스용 Skype 서버 2015 (SB 2015) 사용자 프로비저닝 도구 (UserProvisioningTool)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="98a03-113">이는 항목을 읽을 때 유용할 수 있는 유용한 용어 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="98a03-114">**조직 구성 단위** -AD DS (Active Directory 도메인 서비스) OU (조직 구성 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="98a03-115">**페더레이션/교차 풀** -다른 IM (인스턴트 메시징) 서비스에서 사용자와 통신할 수 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="98a03-116">**메일** 그룹 또는 dl.</span><span class="sxs-lookup"><span data-stu-id="98a03-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="98a03-117">Ad DS 사용자 목록을 포함 하는 AD DS의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="98a03-118">사용자 그룹 간의 통신을 촉진 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="98a03-119">**위치 정보 서비스** -휴대폰에서 사용 하도록 설정 하 고 구성 하는 비즈니스용 Skype 서버 2015 서비스는 향상 된 911 (E911) 서비스에 대 한 실제 위치 검색을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="98a03-120">**미국 전화 번호** -역방향 번호 조회 (RNL)에서 인바운드 및 아웃 바운드 호출을 라우팅하는 데 사용 되는 SIP URI 외에 사용자에 게 할당 된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="98a03-121">UserProvisioningTool를 사용 하 여 사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="98a03-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="98a03-122">시작 하기 전에 도메인 관리자 보안 그룹의 구성원으로 로그인 하 여이 도구를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="98a03-123">Active Directory 사용자를 만들기 때문에이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="98a03-124">부하 시뮬레이션을 위해 사용자 및 연락처를 만들려면 비즈니스용 Skype 서버 사용자 프로 비전 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="98a03-125">비즈니스용 **Skype 서버 사용자 프로비저닝 도구** 는 비즈니스용 **skype 서버 스트레스 및 성능 도구** 패키지와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="98a03-126">패키지 설치 관리자 (CapacityPlanningTool)가 프런트 엔드 서버 또는 테스트할 Standard Edition 서버에서 실행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="98a03-127">프런트 엔드 서버 또는 Standard Edition Server에서 UserProvisioningTool (% InstalledDirectory% LyncStressAndPerfTool \ L C스트레스가에 위치)를 실행 하 여 비즈니스용 Skype 서버 사용자 제공 도구를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="98a03-128">많은 수의 사용자를 만들 때 (예: 1만 이상) UserProvisioningTool를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="98a03-129">도구가 *새* 광고 사용자를 만들고 구성 하기 때문에이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="98a03-130">사용자 프로비저닝 도구가 열리면 구성을 클릭 하 고 로드 구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="98a03-131">사용자 및 연락처 구성을 시작 하려면 패키지에 포함 된 기본 파일 ("SampleData")을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="98a03-132">이렇게 하면 배포에 맞게 변경 해야 하는 예제 데이터를 사용 하 여 필드의 미리 채우기가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="98a03-133">사용자 지정 설정이 이미 포함 되어 있는 미리 구성 된 XML 파일이 있는 경우 해당 파일을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="98a03-134">아래 섹션에서 설명 하는 대로 사용자 프로비저닝 도구에 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="98a03-135">서버 옵션을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-135">To configure server options:</span></span>

1. <span data-ttu-id="98a03-136">**프런트 엔드 풀 fqdn** 필드에 Standard Edition SERVER의 fqdn (정규화 된 도메인 이름) 또는 사용자를 호스트할 프런트 엔드 풀을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="98a03-137">**사용자 이름 접두사** 필드에 테스트 목적으로 사용자 이름을 bust 하는 데 사용할 접두사를 입력 합니다 (예: "TestUser").</span><span class="sxs-lookup"><span data-stu-id="98a03-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="98a03-138">**암호** 필드에 모든 테스트 사용자 계정에서 사용 될 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="98a03-139">**계정 도메인** 필드에 현재 AD 도메인의 도메인 이름 (테스트 사용자를 만들려는 대상)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="98a03-140">**조직 구성 단위** 필드에 이러한 테스트 사용자를 만들 광고 도메인의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="98a03-141">OU가 아직 없는 경우 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="98a03-142">**전화 번호 지역 번호** 필드에 모든 테스트 사용자 계정에서 사용할 세 자리 지역 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="98a03-143">선택한 지역 번호가 광고의 다른 사용자 지역 코드와 충돌 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="98a03-144">엔터프라이즈 음성에 대 한 테스트 사용자를 사용 하도록 설정 하려면 **음성 사용** 확인란을 클릭 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="98a03-145">**사용자 수** 필드에 만들려는 총 테스트 사용자 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="98a03-146">**시작 인덱스** 필드에서 사용자 이름 접두사에 대 한 접미사로 사용할 시작 번호를 지정 합니다 (예: 접두사는 "TestUser"이 고, 첫 번째 이름은 아래 예제에서 "0"으로 종료 됨).</span><span class="sxs-lookup"><span data-stu-id="98a03-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![사용자 만들기 탭을 보여 주는 사용자 프로비저닝 도구](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="98a03-148">사용자 만들기 단추</span><span class="sxs-lookup"><span data-stu-id="98a03-148">Create Users button</span></span>

<span data-ttu-id="98a03-149">**사용자 만들기** 단추를 클릭 하면 입력 한 입력 매개 변수의 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="98a03-150">유효성 검사 오류가 있는 경우 오류를 수정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="98a03-151">또는 모든 값이 올바르면 사용자가 지정한 OU에 관계 없이 AD에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="98a03-152">도구를 실행할 때 진행률 표시줄이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="98a03-153">진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫지 마세요.</span><span class="sxs-lookup"><span data-stu-id="98a03-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="98a03-154">사용자 만들기에는 시간이 소요 되므로 적절 하 게 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="98a03-155">이 프로세스는 소수의 사용자를 위해 몇 분에서 많은 사용자를 위해 몇 시간까지 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="98a03-156">테스트 환경에서 AD 도메인 컨트롤러에 대 한 액세스 권한이 없는 경우에는 사용자가 만드는 사용자 범위에 있는 사용자 중 한 명으로 로그인 하 여 사용자 만들기의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="98a03-157">접두사와 접미사는 사용자 이름으로 @sipDomain 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="98a03-158">예: <em>TestUser20@contoso.net</em> .</span><span class="sxs-lookup"><span data-stu-id="98a03-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a03-159">사용자가 이미 있는 경우 사용자 만들기 단추를 클릭 하면 구성 변경 내용으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="98a03-160">사용자 삭제 단추</span><span class="sxs-lookup"><span data-stu-id="98a03-160">Delete Users button</span></span>

<span data-ttu-id="98a03-161">**사용자 삭제** 단추를 클릭 하면 탭의 입력 매개 변수 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="98a03-162">유효성 검사 오류가 있는 경우 해당 오류를 해결 하 라는 메시지가 표시 되 고 입력 값이 올바르면 지정 된 테스트 사용자가 Active Directory에서 비활성화 되 고 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="98a03-163">이 탭의 아래쪽에 진행률 표시줄이 표시 되 고 진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a03-164">미국 형식의 전화 번호만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="98a03-165">전화 번호는 항상 사용자에 게 할당 되며 UserProvisioningTool에서 만든 모든 사용자는 기본적으로 Enterprise Voice에 대해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="98a03-166">전화 번호를 사용 하는 모든 시나리오 (예: 회의 자동 전화 교환 또는 UC-PSTN 통화)는이 전화 번호를 사용 하 여 통화를 올바르게 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="98a03-167">이러한 이유로 *모든 사용자* 는 *고유한 전화 번호* 를가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a03-168">**사용자를 두 번 만들어야 하는 경우 다른 지역 번호를 사용 하지 않거나 이전 사용자가 CsUser cmdlet을 사용 하 여 비활성화 된 경우를 제외 하 고 명령이 실패 합니다.**</span><span class="sxs-lookup"><span data-stu-id="98a03-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="98a03-169">연락처를 만들기 전에 먼저 사용자 복제를 완료 해야 합니다 (사용자 탭에서 수행 됨).</span><span class="sxs-lookup"><span data-stu-id="98a03-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="98a03-170">방금 사용자를 만든 경우 비즈니스용 Skype 서버 복제가 완료 될 때까지 기다린 후 데이터베이스의 사용자 계정을 채울 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="98a03-171">**사용자가 복제를 완료 하지 않은 경우 오류가 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="98a03-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="98a03-172">비즈니스용 Skype 서버 2015 프론트 엔드 서비스가 시작 된 경우 또는 사용자가 지정한 총 번호의 마지막 사용자에 대 한 가져오기-CsUser cmdlet을 성공적으로 실행 하는 경우이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="98a03-173">연락처 만들기 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-173">Contacts Creation tab</span></span>

<span data-ttu-id="98a03-174">이 탭에서는 테스트에 대 한 사용자의 연락처 세부 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![콘텐츠 만들기 탭이 표시 된 사용자 프로비저닝 도구](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="98a03-176">사용자의 연락처를 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="98a03-177">**사용자 당 평균 연락처** 필드에 각 사용자의 대화 상대 목록에 입력할 평균 연락처 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="98a03-178">모든 사용자에 대해 동일한 수의 연락처를 만들려면 **수정** 됨 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="98a03-179">사용자에 게 생성 되는 연락처 수를 변경 하려면 해당 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="98a03-180">**사용자 당 평균 대화 상대 그룹** 필드에 사용자 당 대화 상대 그룹 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="98a03-181">이 번호는 **사용자 당 평균 연락처**보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="98a03-182">**페더레이션된/교차 풀 연락처 백분율** 필드에 0과 100 사이의 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="98a03-183">이 연락처의 백분율은 페더레이션 사용자와 함께 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="98a03-184">**페더레이션/교차 풀 사용자 접두사** 필드에서 로컬 사용자의 연락처 목록에 추가 될 페더레이션 사용자의 사용자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="98a03-185">**페더레이션된/교차 풀 사용자 Sip 도메인** 필드에 페더레이션 사용자의 Sip 도메인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="98a03-186">**사용자 만들기** 탭에서 정보가 정확한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="98a03-187">사용자 만들기 탭의 값을 통해 연락처가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="98a03-188">**연락처** 만들기를 클릭 하 여 연락처 만들기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="98a03-189">이 프로세스는 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-189">This process can take several minutes.</span></span> <span data-ttu-id="98a03-190">완료 되 면 "작업이 완료 되었습니다." 라는 메시지가 표시 되는 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="98a03-191">사용자 만들기 탭에서 만든 사용자로 로그온 하 여 만든 연락처의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="98a03-192">연락처를 만든 후이 도구는 대상 풀의 모든 프런트 엔드 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="98a03-193">이 작업으로 만든 연락처 수에 따라 프런트 엔드 서버를 시작 하는 데 걸리는 시간이 최대 2 시간까지 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="98a03-194">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="98a03-194">Distribution List</span></span>

<span data-ttu-id="98a03-195">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 비즈니스용 Skype 2015 클라이언트에서 DL (메일 그룹) 확장 기능을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="98a03-196">사용자 프로비저닝 도구에서 DL 확장을 사용 하지 않으려는 경우이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![메일 그룹 만들기 탭을 보여 주는 사용자 프로비저닝 도구](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="98a03-198">메일 그룹 탭에서 스트레스 및 성능 도구가 메일 그룹 확장 기능에 사용할 Dl을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="98a03-199">Dl을 만들기 전에 ForestPrep를 실행 하는 것을 포함 하 여 비즈니스용 Skype 서버 2015를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="98a03-200">이 작업을 수행 하지 않으면 DL 특성이 광고 스키마에 존재 하지 않으므로 도구가 Dl을 만들 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="98a03-201">메일 그룹을 구성 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="98a03-202">메일 그룹 **수** 필드에 만들려는 dl의 총 수를 지정 합니다 (여기서는 사용자 수를 두 배로 하는 값으로 시작 하는 것이 권장 됨).</span><span class="sxs-lookup"><span data-stu-id="98a03-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="98a03-203">메일 그룹 **접두사** 필드에 사용자가 만든 모든 dl에 사용할 접두사를 입력 합니다 (예: *testdl* ).</span><span class="sxs-lookup"><span data-stu-id="98a03-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="98a03-204">즉, 100 Dl에서 DL 이름에는 testDL0, testDL1, testDL99까지 등의 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="98a03-205">목록 필드 **의 최소 구성원** 에서 각 DL에 입력할 최소 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="98a03-206">목록 필드 **의 최대 구성원** 에서 각 DL에 추가할 최대 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="98a03-207">메일 그룹 만들기 단추</span><span class="sxs-lookup"><span data-stu-id="98a03-207">Create Distribution Lists button</span></span>

<span data-ttu-id="98a03-208">메일 그룹 만들기 단추를 클릭 하면 도구는 Active Directory를 쿼리하여 접두사 및 번호와 일치 하는 메일 그룹이 이미 존재 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="98a03-209">이 도구는 아직 존재 하지 않는 Dl을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="98a03-210">새로 만든이 메일 그룹에 구성원을 추가 하는 경우 사용자 만들기 탭에 지정 된 범위에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="98a03-211">위치 정보 서비스 구성 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-211">Location Info Service Config tab</span></span>

<span data-ttu-id="98a03-212">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 위치 정보 서비스에 대 한 더미 구성 파일을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="98a03-213">일반적으로 위치 정보 서비스는 서버에 중대 한 성능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![위치 정보 서비스 구성 탭을 보여 주는 사용자 프로비저닝 도구](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="98a03-215">이 기능을 테스트 하도록 선택 하는 경우 양식에 값을 입력 하 고, 만들 LIS Config 파일 생성 단추를 클릭 합니다. CSV 파일 호출:</span><span class="sxs-lookup"><span data-stu-id="98a03-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="98a03-216">.Csv LIS_Subnet</span><span class="sxs-lookup"><span data-stu-id="98a03-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="98a03-217">.Csv LIS_Switches</span><span class="sxs-lookup"><span data-stu-id="98a03-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="98a03-218">.Csv LIS_Ports</span><span class="sxs-lookup"><span data-stu-id="98a03-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="98a03-219">.Csv LIS_WAP</span><span class="sxs-lookup"><span data-stu-id="98a03-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="98a03-220">이러한 파일을 LIS 데이터베이스로 가져오려면 다음 PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="98a03-221">Set-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="98a03-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="98a03-222">Set-CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="98a03-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="98a03-223">Set-CsLisPort</span><span class="sxs-lookup"><span data-stu-id="98a03-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="98a03-224">Set-CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="98a03-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="98a03-225">사용자 프로필 구성</span><span class="sxs-lookup"><span data-stu-id="98a03-225">Configure User Profile</span></span>
<span data-ttu-id="98a03-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="98a03-226"><a name="BKMK_UserProfile"> </a></span></span>

<span data-ttu-id="98a03-227">사용자 만들기 도구를 통해 사용자를 만든 후 비즈니스용 Skype Server 2015 부하 구성 도구 (UserProfileGenerator)를 사용 하 여 사용자 프로필을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="98a03-228">비즈니스용 Skype 서버 2015 로드 구성 도구 실행</span><span class="sxs-lookup"><span data-stu-id="98a03-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="98a03-229">로드 구성 도구 (UserProfileGenerator)를 시작 하 고 탭을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="98a03-230">이 도구는 시뮬레이션을 실행 하는 데 필요한 각 클라이언트 컴퓨터에 대 한 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="98a03-231">각 클라이언트 디렉터리에는 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 시작 하는 스크립트와 함께 제공 됩니다 (L<c13> Cperftool. exe).</span><span class="sxs-lookup"><span data-stu-id="98a03-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="98a03-232">아래 섹션에서는 비즈니스용 Skype Server 2015 부하 구성 도구의 각 탭에 있는 필드를 채우는 방법을 보여 주는 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="98a03-233">로드 구성 도구 (UserProfileGenerator)에서 사용 되는 사용자 관련 값은 풀에 대 한 비즈니스용 Skype 서버 2015 사용자 만들기 도구 (UserProvisioningTool)에 지정 된 값과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="98a03-234">일반 구성 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-234">Common Configuration tab</span></span>

<span data-ttu-id="98a03-235">로드 구성 도구의 **공통 구성** 탭이 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="98a03-236">일반 구성 탭의 필드를 다음 단계에 설명 된 대로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![일반 구성 탭이 표시 된 사용자 프로비저닝 탭](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="98a03-238">**사용할 수 있는 컴퓨터 수** 필드에 스트레스 및 성능 도구 (L cperftool. exe)를 실행 하는 데 사용할 컴퓨터 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="98a03-239">모든 4500 사용자에 대해 컴퓨터 1 대를 사용 하는 것이 좋지만, 로드 수준을 줄이거나 도구의 사용 가능한 기능 중 일부만 사용할 경우 (로드 수준은 일반 시나리오 탭에서 설정 된 경우)에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="98a03-240">**사용자 이름 접두사** 필드에 모든 사용자의 사용자 이름 필드에 대 한 접두사를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="98a03-241">URI (Uniform Resource Identifier)를 사용 하 여 로그인 하려면: *Userprefix [사용자 시작 색인 ...]을 사용 합니다. (사용자 수-1)] @User 도메인* (예: myUser009@Contoso.com).</span><span class="sxs-lookup"><span data-stu-id="98a03-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="98a03-242">**모든 사용자의 암호** 필드에 사용자를 만드는 동안 사용 되는 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="98a03-243">이 필드를 비워 두면 사용자 이름이 암호로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="98a03-244">**사용자 시작 인덱스** 필드에 구성할 첫 번째 사용자의 인덱스를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="98a03-245">다양 한 형식 또는 부하 수준에 대해 서로 다른 범위를 구성할 수 있지만 구성 하려는 범위에 따라 로드 구성 도구 (UserProfileGenerator)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="98a03-246">**사용자 수** 필드에 구성할 총 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="98a03-247">**사용자 도메인** 필드에 SIP URI에 사용 되는 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="98a03-248">이는 각 사용자의 SIP URI를 생성 하 여 비즈니스용 Skype 서버 2015 프런트 엔드 서버 또는 Standard Edition 서버에 로그온 하는 데 사용 되며 계정 도메인과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="98a03-249">**계정 도메인** 필드에 AD DS 도메인 로그온을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="98a03-250">**MPOP 백분율** (현재 시점 표시 백분율) 필드에 여러 컴퓨터 또는 장치에서 로그온 한 사용자의 백분율 (예: 10%)에 대 한 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="98a03-251">초 **당 로그인 (인스턴스당)** 필드에 최대 동시 끝점 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="98a03-252">이는 사용자에 대 한 최대 로그 기능 수 이며 권장 사항은 초당 2 (<= 2) 보다 작거나 같은 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="98a03-253">**액세스 프록시 또는 풀 FQDN** 필드에 클라이언트가 연결할 서버의 정규화 된 도메인 이름 (FQDN)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="98a03-254">사용자가 외부에서 로그인 하는 경우에는 액세스 프록시를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="98a03-255">사용자가 internal 인 경우 해당 엔터프라이즈 풀 또는 Standard Edition 서버의 FQDN을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="98a03-256">**포트** 필드에 사용자가 SIP에 대해 사용할 포트를 입력 합니다 (기본값은 5061입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="98a03-257">**외부 네트워크 서버 설정** 필드에 대해 액세스 프록시 또는 풀 FQDN과 다시 **포트**를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="98a03-258">이러한 설정은 외부 끝점 부하 시뮬레이션에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="98a03-259">일반 시나리오 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-259">General Scenarios tab</span></span>

![일반 시나리오 탭을 보여 주는 로드 구성 도구](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="98a03-261">실행할 항목을 결정 하거나 사용 하지 않도록 설정 하 여 제공 되는 각 일반 시나리오에 대해 부하 수준 및 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="98a03-262">일반 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a03-263">모든 필드에 대 한 로드 수준 값 (지역 정보 서비스는 **사용할 수 없음**, **낮음**, **보통**, **높음**또는 **사용자 지정**)입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="98a03-264">설정을 선택 하 고 사용 하지 않도록 설정한 경우 각 클라이언트에 대 한 구성이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="98a03-265">높은 결과는 서버에서 지원 되는 최대 로드입니다. medium은 높은 부하의 60%입니다. low는 30%입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="98a03-266">**인스턴트 메시지-** 여기에는 피어 투 피어 및 회의가 포함 됩니다. 로드 수준에 적합 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="98a03-267">**오디오 회의-** 오디오 회의에 대 한 *부하 수준만 선택* 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="98a03-268">피어 투 피어 통화는 **음성 시나리오** 섹션에서 나중에 tackled 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="98a03-269">**고급** 탭을 열고 MultiView을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="98a03-270">**응용 프로그램 공유-** 응용 프로그램 공유에 대 한 부하 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="98a03-271">**데이터 공동 작업-** 데이터 회의를 포함 하는 데이터 공동 작업에 대 한 부하 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="98a03-272">**메일 그룹 확장** **고급** 단추를 클릭 하 고 사용자 만들기 도구 (UserProvisioningTool)의 DL 탭에 구성 된 동일한 값이 있는 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="98a03-273">부하 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-273">Choose a load level.</span></span>
    
- <span data-ttu-id="98a03-274">**주소록 웹 쿼리-** 주소록 파일 다운로드가 아닌 주소록 조회 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="98a03-275">주소록 파일 다운로드에 대해이 기능을 사용 하도록 설정 하려면 **고급** 단추를 클릭 하 고 **EnableABSDownload** 를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="98a03-276">부하 수준에 대 한 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="98a03-277">**응답 그룹 서비스-** **고급** 단추를 클릭 하 고 응답 그룹 서비스 에이전트를 프로 비전 할 때 이미 만든 응답 그룹의 uri를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="98a03-278">하나 이상의 응답 그룹을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-278">You must choose at least one response group.</span></span> <span data-ttu-id="98a03-279">더 많은 기능을 사용 하려면 응답 그룹을 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="98a03-280">실제 값으로 **RGSUriSuffixStartIndex** 및 **RGSUriSuffixEndIndex** 를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="98a03-281">부하 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-281">Choose a load level.</span></span>
    
- <span data-ttu-id="98a03-282">**위치 정보 서비스-** 사용 또는 사용 안 함 중으로 로드 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="98a03-283">각 시나리오에는 그 옆에 고급 단추가 있고, 기본 설정을 변형 하는 데 사용할 수 있는 확인란 집합을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="98a03-284">*Ad-hoc* 을 선택 하면 시간 동안 생성 되는 회의 시뮬레이션이 도구에 생성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="98a03-285">*대형* 컨퍼런스를 선택 하면 대규모 회의 시나리오가 시뮬레이트된 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="98a03-286">*외부* 는 도구에 게 외부 사용자를 시뮬레이트하기도 록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="98a03-287">이러한 단추와 확인란은 각 시나리오와 관련 된 추가 값으로, 스트레스 및 성능 도구의 동작을 변경 하 고 사용자 지정할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="98a03-288">일반 시나리오 탭의 각 시나리오 (위치 정보 서비스 제외)의 경우 로드 수준 값이 **사용자 지정**이면 고급 대화 상자의 해당 필드를 사용 하 여 대화 속도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="98a03-289">필드 이름은 시나리오에 따라 다를 수 있지만, 필드 설명은 다음과 같습니다. *참고이 번호는 드롭다운 메뉴에서 사용자 지정이 선택 된 경우에만 사용 됩니다* .</span><span class="sxs-lookup"><span data-stu-id="98a03-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="98a03-290">값이 **높음**, **중간**, **낮음**인 경우 모든 시나리오의 잔고에 해당 하는 사용자 모델을 사용 하 여 적용 된 모달 대화의 요금을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="98a03-291">예상 사용량의 차이로 인해 각 모달의 로드 수준을 변경 해야 하는 경우 사용자 지정 대화 속도를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="98a03-292">음성 시나리오 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-292">Voice Scenarios tab</span></span>

<span data-ttu-id="98a03-293">이 탭을 통해 모든 음성 관련 시나리오를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![로드 구성 도구 음성 시나리오 탭](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="98a03-295">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-295">Your options are:</span></span>
  
- <span data-ttu-id="98a03-296">**VoIP-** **고급** 단추를 클릭 하 고 PhoneAreaCode 및 locationprofile (다이얼 플랜) 필드에 대 한 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="98a03-297">또한 로드 수준에 대 한 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="98a03-298">VoIP 또는 UC/PSTN 게이트웨이를 사용할 수 있도록 설정 된 경우, 외부 통화를 시뮬레이트하기 위해 PSTN (통합 통신 네트워크) 구성 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="98a03-299">**UC/PSTN 게이트웨이-** 부하 수준 값을 선택 해야 하며, 사용 안 함을 제외한 다른 항목을 선택 하면, **고급** 단추를 클릭 하 여 PSTN 지역 코드에 대 한 값을 제공 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="98a03-300">중재 서버 및 PSTN 아래에서 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="98a03-301">지역 번호에 대해 경로가 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="98a03-302">Skype for Business 제어판 또는 비즈니스용 Skype 관리 셸을 사용 하 여 음성 경로 구성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="98a03-303">**회의 수행자-** 로드 수준에 대 한 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="98a03-304">사용 안 함을 제외한 모든 값은 **전화 번호** 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="98a03-305">사용할 자동 전화 교환의 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="98a03-306">**고급** 을 클릭 하 고 **locationprofile** 필드에 대 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="98a03-307">**통화 파킹 서비스-** 여기서는 부하 수준을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="98a03-308">**중재 서버 및 PSTN-** 사용 하려는 각 중재 서버에는 고유한 PSTN 시뮬레이터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="98a03-309">시뮬레이터에 사용할 클라이언트를 결정 한 후에는 사용자가 구성한 PSTN Simulator에서 해당 컴퓨터로 호출을 라우팅하도록 중재 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="98a03-310">**추가** 단추를 클릭 하 여 중재 서버의 값을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="98a03-311">각 시나리오에는 옆에 고급 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="98a03-312">고급 대화 상자에는 스트레스 및 성능 도구의 동작을 변경 하 고 사용자 지정을 활성화 하는 각 시나리오에 대 한 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="98a03-313">음성 시나리오 탭의 각 시나리오에 대 한 > 로드 수준의 값이 **사용자 지정**인 경우에는 대화 비율이 고급 대화 상자의 해당 필드를 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="98a03-314">필드 이름은 시나리오에 따라 다를 수 있지만, 필드 설명은 다음과 같습니다. *참고이 번호는 드롭다운 메뉴에서 사용자 지정이 선택 된 경우에만 사용 됩니다* .</span><span class="sxs-lookup"><span data-stu-id="98a03-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="98a03-315">웹 앱 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-315">Web App tab</span></span>

![로드 구성 도구, 웹 앱 탭](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="98a03-317">웹 앱은 프런트 엔드 서버에 설치 된 통합 커뮤니케이션 웹 API (와) 서버를 통해 회의 시나리오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="98a03-318">웹 앱 탭을 사용 하 여 모든 웹 앱 관련 시나리오를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="98a03-319">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-319">Options are:</span></span>
  
- <span data-ttu-id="98a03-320">**일반 웹 앱 설정-** **추가 설정** 단추를 클릭 하 고 **ReachTargetServerUrl** 를 프런트 엔드 풀 vip의 디렉터리 풀 vip (가상 IP)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="98a03-321">**응용 프로그램 공유-** 로드 수준에 대 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="98a03-322">**데이터 공동 작업-** 로드 수준에 대 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="98a03-323">**인스턴트 메시지-** 로드 수준에 대 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="98a03-324">**음성 회의-** 로드 수준에 대 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="98a03-325">각 시나리오에는 옆에 **고급** 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="98a03-326">고급 대화 상자에는 스트레스 및 성능 도구의 동작을 변경 하 고 사용자 지정을 가능 하 게 하는 각 시나리오에 대 한 값이 포함 되어 있습니다. 로드 수준이 **사용자 지정**인 경우 각 웹 앱 시나리오에 대 한 > **ConversationsPerHour** 필드에 지정 된 값이 기본값 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="98a03-327">모바일 기능 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-327">Mobility tab</span></span>

<span data-ttu-id="98a03-328">이 탭을 사용 하 여 모든 이동성 관련 시나리오를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![부하 구성 도구 이동성 탭](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="98a03-330">여기에는 다음과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-330">The options here are:</span></span>
  
- <span data-ttu-id="98a03-331">**일반 이동성 설정-** **추가 설정을** 클릭 하 고 필드 UcwaTargetServerUrl를 디렉터 풀 vip (가상 IP) 또는 프런트 엔드 풀 vip로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="98a03-332">**현재 상태 및 P2P 인스턴트 메시지/오디오-** 부하 수준에 대 한 값을 선택 하 여 이동성 시뮬레이션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="98a03-333">각 시나리오에는 옆에 **고급** 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="98a03-334">고급 대화 상자에는 스트레스 및 성능 도구의 동작을 변경 하 고 사용자 지정을 가능 하 게 하는 각 시나리오에 대 한 값이 포함 됩니다. 부하 수준이 **사용자 지정**인 경우 각 모바일 시나리오에 대 한 > **ConversationsPerHour** 필드에 지정 된 값이 기본값 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="98a03-335">요약 탭</span><span class="sxs-lookup"><span data-stu-id="98a03-335">Summary tab</span></span>

<span data-ttu-id="98a03-336">요약 탭에는 각 시나리오에 사용할 사용자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![로드 구성 도구 요약 탭](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="98a03-338">요약 탭에는 각 시나리오에 사용할 사용자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="98a03-339">사용자 **지정 사용자 범위 생성 사용** 확인란을 선택 하 고 사용자 지정 하려는 사용자 범위를 포함 하는 표에서 시나리오를 두 번 클릭 하 여 사용자 번호 범위를 수동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="98a03-340">선택 (Runclient) 로그인 속도에 맞게 생성 된 일괄 처리 파일에 지연 시간을 포함 하기 위해 **시작할 때 로그인 지연을 추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="98a03-341">이는 많은 사용자에 게 로그인 할 때 서버 오버 로드가 발생 하지 않도록 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="98a03-342">**파일 생성** 을 클릭 하 고 구성을 생성 하려는 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="98a03-343">파일이 성공적으로 만들어졌으면 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-343">A dialog box will appear when your files have been successfully created.</span></span>
  
![' 성공적으로 생성 된 구성 파일 로드 ' 메시지 상자](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="98a03-346">L Cperf도구 실행</span><span class="sxs-lookup"><span data-stu-id="98a03-346">Run LyncPerfTool</span></span>
<span data-ttu-id="98a03-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="98a03-347"><a name="BKMK_RunTool"> </a></span></span>

<span data-ttu-id="98a03-348">비즈니스용 Skype Server 2015 스트레스 및 성능 도구 (L보완 Cperftool)를 실행 하기 전에 사용자, 연락처 및 시나리오를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="98a03-349">도구를 사용 하 여 이러한 작업을 수행 하는 방법에 대 한 자세한 내용은이 문서의 앞부분에 나오는 사용자 [및 연락처 만들기](using-the-tool.md#BKMK_CreateUsersAndContacts) 및 [사용자 프로필 구성을](using-the-tool.md#BKMK_UserProfile) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98a03-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="98a03-350">이러한 도구를 실행 하면 필요한 매개 변수를 포함 하는 배치 파일의 일부로 스트레스 및 성능 도구를 사용 하 여 실행 되는 파일도 생성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="98a03-351">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 실행</span><span class="sxs-lookup"><span data-stu-id="98a03-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="98a03-352">로드 구성 도구 (UserProfileGenerator)는 성능 카운터를 등록 하 고 XML 구성 파일을 로드 하 여 스트레스 및 성능 도구 (L Cperftool)를 실행할 수 있는 배치 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="98a03-353">일괄 처리 파일은 각 구성 파일에 대해 L Cperftool의 인스턴스 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="98a03-354">배치 파일을 실행 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="98a03-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="98a03-355">스트레스 및 성능 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="98a03-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="98a03-356">각 클라이언트 컴퓨터에서 L Cperftool .exe를 사용 하는 디렉터리에 구성 폴더 및 파일이 있는 폴더를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="98a03-357">예를 들어 1.28 _ 13.16.16 폴더의 구성 파일을 생성 한 경우 해당 폴더를 l Cperftool이 포함 된 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="98a03-358">각 클라이언트에서이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="98a03-359">클라이언트 폴더로 이동 하 고 **Runclient** batch 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="98a03-360">Windows 탐색기에서 배치 파일을 두 번 클릭 하 여 해당 클라이언트에 대 한 모든 구성 파일을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="98a03-361">다음 구문을 사용 하 여 클라이언트 폴더에서 스크립트를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="98a03-362">스트레스 및 성능 도구를 직접 실행 하려면 명령 프롬프트를 열고 명령줄에 다음 명령을 입력 합니다 (이 항목의 뒷부분에 나오는 참고와 같이 성능 카운터 `regsvr32 /i /n /s LyncPerfToolPerf.dll`를 등록 해야 합니다.).</span><span class="sxs-lookup"><span data-stu-id="98a03-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="98a03-363">도구에 구성 파일의 값이 표시 되도록 하려면 앞의 명령에 `/displayfile` 매개 변수를 포함 하면 다음과 같은 모양이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="98a03-364">프로세스를 *종료* 하려면 Ctrl + C를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a03-365">스트레스 및 성능 도구를 직접 실행 하기 전에 다음 명령을 통해 성능 카운터를 등록 해야 합니다.`regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="98a03-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a03-366">시작 하는 스트레스 및 성능 도구의 모든 인스턴스는 사용자의 로그인을 즉시 시작 하 고, 일반적으로 초 당 1 명의 사용자에 대 한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="98a03-367">풀의 최고 사용자 로그인 속도는 초당 약 12입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="98a03-368">즉, 사용자가 계속 해 서 로그인 하는 동안 12 개 이상의 L Cperftool .exe 인스턴스를 시작 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="98a03-369">1000 사용자는 초당 1 초에 완전히 로그인 하는 데 약 20 분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="98a03-370">결과 해석</span><span class="sxs-lookup"><span data-stu-id="98a03-370">Interpreting the Results</span></span>
<span data-ttu-id="98a03-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="98a03-371"><a name="BKMK_Interpret"> </a></span></span>

<span data-ttu-id="98a03-372">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에는 클라이언트가 수행 하는 작업을 이해 하는 데 도움이 되는 다양 한 카운터와 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="98a03-373">클라이언트 카운터</span><span class="sxs-lookup"><span data-stu-id="98a03-373">Client Counters</span></span>

<span data-ttu-id="98a03-374">실행 중인 L Cperftool의 각 인스턴스에는 별도의 카운터 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="98a03-375">각 인스턴스는 해당 프로세스 ID로 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="98a03-376">클라이언트가 오버 로드 되 면 다른 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="98a03-377">이러한 문제가 발생 하지 않도록 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="98a03-378">클라이언트 컴퓨터의 CPU 및 메모리 사용량을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="98a03-379">CPU가 90 퍼센트 이상으로 일관 되는 경우 사용자 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="98a03-380">메모리 사용량이 높으면 페이지 파일의 공간이 부족 하 게 되 면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="98a03-381">커밋 충전량이 컴퓨터의 한도에 도달 하 고 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="98a03-382">메모리 제한을 실행 하는 경우 페이지 파일 크기를 늘리거나 사용자 수를 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="98a03-383">주요 성능 카운터 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="98a03-384">**일반 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-384">**General Information**</span></span>

|<span data-ttu-id="98a03-385">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-385">**Performance Counter**</span></span>|<span data-ttu-id="98a03-386">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-387">분 내에 소요 된 시간</span><span class="sxs-lookup"><span data-stu-id="98a03-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="98a03-388">프로세스가 시작 된 이후 경과한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="98a03-389">활성 끝점</span><span class="sxs-lookup"><span data-stu-id="98a03-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="98a03-390">현재 서버에 연결 된 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="98a03-391">실패 한 로그온</span><span class="sxs-lookup"><span data-stu-id="98a03-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="98a03-392">끝점 로그인 실패의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="98a03-393">로그온 시도</span><span class="sxs-lookup"><span data-stu-id="98a03-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="98a03-394">끝점 로그인 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="98a03-395">끝점 연결 끊김</span><span class="sxs-lookup"><span data-stu-id="98a03-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="98a03-396">연결이 끊어진 끝점의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="98a03-397">**현재 상태 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-397">**Presence Information**</span></span>

|<span data-ttu-id="98a03-398">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-398">**Performance Counter**</span></span>|<span data-ttu-id="98a03-399">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-400">SetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="98a03-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="98a03-401">현재 상태 변경 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-401">Total number of presence change attempts.</span></span> <span data-ttu-id="98a03-402">다른 유형의 현재 변경 내용에 대해서는 SetPresence 상태 (현재 상태 유형) 통화 성능 카운터를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98a03-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="98a03-403">NNN의 SetPresence 상태에 대 한 응답</span><span class="sxs-lookup"><span data-stu-id="98a03-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="98a03-404">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="98a03-405">GetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="98a03-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="98a03-406">현재 상태 요청 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="98a03-407">A GetPresence 상태에 대 한 NNN 응답</span><span class="sxs-lookup"><span data-stu-id="98a03-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="98a03-408">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="98a03-409">**주소록 서비스 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-409">**Address Book service information**</span></span>

|<span data-ttu-id="98a03-410">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-410">**Performance Counter**</span></span>|<span data-ttu-id="98a03-411">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-412">ABS 전체/델타 파일 다운로드를 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="98a03-413">시도한 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-414">ABS 전체/델타 파일 다운로드 성공</span><span class="sxs-lookup"><span data-stu-id="98a03-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="98a03-415">시도한 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-416">주소록 웹 쿼리 서비스 관련 카운터</span><span class="sxs-lookup"><span data-stu-id="98a03-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="98a03-417">주소록 파일 다운로드 관련 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="98a03-418">ABS WS 호출 시도</span><span class="sxs-lookup"><span data-stu-id="98a03-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="98a03-419">시도한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-420">ABS WS 호출 성공</span><span class="sxs-lookup"><span data-stu-id="98a03-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="98a03-421">성공적인 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="98a03-422">ABS WS 호출 실패</span><span class="sxs-lookup"><span data-stu-id="98a03-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="98a03-423">오류 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="98a03-424">이 범주에는 ABS (주소록 서비스) 파일 다운로드 및 주소록 웹 쿼리 서비스 요청을 모니터링 하는 데 사용 되는 카운터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="98a03-425">**DL (메일 그룹) 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="98a03-426">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-426">**Performance Counter**</span></span>|<span data-ttu-id="98a03-427">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-428">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="98a03-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="98a03-429">시도 된 DLX (메일 그룹 확장) 웹 서비스 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-430">통화 성공</span><span class="sxs-lookup"><span data-stu-id="98a03-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="98a03-431">성공적인 응답 코드를 반환한 총 DLX 웹 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="98a03-432">통화 실패</span><span class="sxs-lookup"><span data-stu-id="98a03-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="98a03-433">오류 응답 코드를 반환 하는 DLX 웹 서비스 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="98a03-434">다음 시나리오를 사용 하는 경우 중재 서버, A/V 회의 서버, Edge 서버, 응답 그룹 응용 프로그램, 회의 자동 전화 교환 등의 호출을 포함 하 여 모든 VoIP (Voice over IP) 통화에 대 한 번호를 아래에 나열 된 성능 카운터를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="98a03-435">**VoIP 기본 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="98a03-436">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-436">**Performance Counter**</span></span>|<span data-ttu-id="98a03-437">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-438">통화 활성</span><span class="sxs-lookup"><span data-stu-id="98a03-438">Calls Active</span></span>  <br/> |<span data-ttu-id="98a03-439">현재 진행 중인 총 수신/발신 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="98a03-440">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="98a03-441">이미 종료 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="98a03-442">통화가 거절 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="98a03-443">거절 된 총 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="98a03-444">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="98a03-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="98a03-445">시도한 총 수신/발신 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-446">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="98a03-447">설정 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="98a03-448">받은 통화 NNN</span><span class="sxs-lookup"><span data-stu-id="98a03-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="98a03-449">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="98a03-450">VoIP 통과 율 (%)</span><span class="sxs-lookup"><span data-stu-id="98a03-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="98a03-451">총 통화/총 통화를 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="98a03-452">**응답 그룹 서비스 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="98a03-453">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-453">**Performance Counter**</span></span>|<span data-ttu-id="98a03-454">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-455">통화 활성</span><span class="sxs-lookup"><span data-stu-id="98a03-455">Calls Active</span></span>  <br/> |<span data-ttu-id="98a03-456">응답 그룹 응용 프로그램에 대 한 총 활성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="98a03-457">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="98a03-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="98a03-458">시도한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="98a03-459">**인스턴트 메시지 (IM) 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="98a03-460">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-460">**Performance Counter**</span></span>|<span data-ttu-id="98a03-461">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-462">통화 활성</span><span class="sxs-lookup"><span data-stu-id="98a03-462">Calls Active</span></span>  <br/> |<span data-ttu-id="98a03-463">진행 중인 수신/발신 인스턴트 메시징 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="98a03-464">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="98a03-465">이미 종료 된 수신/발신 인스턴트 메시징 전화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="98a03-466">받은 통화 NNN</span><span class="sxs-lookup"><span data-stu-id="98a03-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="98a03-467">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="98a03-468">수신/전송 된 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="98a03-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="98a03-469">모든 세션에 대해 수신 또는 전송 된 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="98a03-470">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="98a03-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="98a03-471">시도한 총 수신/발신 인스턴트 메시징 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-472">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="98a03-473">설정 된 수신/발신 인스턴트 메시지 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="98a03-474">**앱 공유 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="98a03-475">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-475">**Performance Counter**</span></span>|<span data-ttu-id="98a03-476">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-477">통화 활성</span><span class="sxs-lookup"><span data-stu-id="98a03-477">Calls Active</span></span>  <br/> |<span data-ttu-id="98a03-478">진행 중인 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="98a03-479">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="98a03-480">이미 종료 된 수신/발신 응용 프로그램 공유 전화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="98a03-481">받은 통화 NNN</span><span class="sxs-lookup"><span data-stu-id="98a03-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="98a03-482">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="98a03-483">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="98a03-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="98a03-484">시도한 총 수신/발신 응용 프로그램 공유 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-485">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="98a03-486">설정 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="98a03-487">**통화 정보를 ca**</span><span class="sxs-lookup"><span data-stu-id="98a03-487">**CAA Call Information**</span></span>

|<span data-ttu-id="98a03-488">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-488">**Performance Counter**</span></span>|<span data-ttu-id="98a03-489">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-490">통화 활성</span><span class="sxs-lookup"><span data-stu-id="98a03-490">Calls Active</span></span>  <br/> |<span data-ttu-id="98a03-491">현재 진행 중인 수신/송신 공공 전화망 (PSTN) 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="98a03-492">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="98a03-493">이미 종료 된 수신/송신 PSTN 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="98a03-494">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="98a03-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="98a03-495">시도한 총 수신/송신 PSTN 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="98a03-496">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="98a03-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="98a03-497">설정 된 수신/발신 PSTN 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="98a03-498">**컨퍼런스 정보**</span><span class="sxs-lookup"><span data-stu-id="98a03-498">**Conference Information**</span></span>

|<span data-ttu-id="98a03-499">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-499">**Performance Counter**</span></span>|<span data-ttu-id="98a03-500">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-501">활성 인스턴트 메시지 회의</span><span class="sxs-lookup"><span data-stu-id="98a03-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="98a03-502">진행 중인 인스턴트 메시지 회의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="98a03-503">활성 오디오/비디오 회의</span><span class="sxs-lookup"><span data-stu-id="98a03-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="98a03-504">진행 중인 총 오디오/비디오 (A/V) 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="98a03-505">활성 응용 프로그램 공유 회의</span><span class="sxs-lookup"><span data-stu-id="98a03-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="98a03-506">진행 중인 응용 프로그램 공유 컨퍼런스의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="98a03-507">참가자 수</span><span class="sxs-lookup"><span data-stu-id="98a03-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="98a03-508">현재 컨퍼런스에 연결 된 총 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="98a03-509">컨퍼런스 일정 실패</span><span class="sxs-lookup"><span data-stu-id="98a03-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="98a03-510">회의를 예약 하려고 시도 하는 동안 발생 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="98a03-511">컨퍼런스 참가 실패</span><span class="sxs-lookup"><span data-stu-id="98a03-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="98a03-512">회의에 연결 하려고 시도 하는 동안 발생 한 총 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="98a03-513">**A/WA 클라이언트 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="98a03-514">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="98a03-514">**Performance Counter**</span></span>|<span data-ttu-id="98a03-515">**설명**</span><span class="sxs-lookup"><span data-stu-id="98a03-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98a03-516">성공한 IMMCU 조인의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="98a03-517">참가 한 총 인스턴트 메시징 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="98a03-518">성공한 DMCU 조인의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="98a03-519">참가 한 총 A/V 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98a03-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

