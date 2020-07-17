---
title: 사용자 및 연락처 만들기
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f90e6cbb1afb9c4c2dd2b43e1448ca635899531b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="9094f-102">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="9094f-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9094f-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9094f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9094f-104">스트레스 및 성능 부하 테스트를 준비 하기 위해 Lync Server 2013 사용자 프로 비전 도구 (UserProvisioningTool.exe)를 사용 하 여 사용자 및 연락처를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="9094f-105">이 항목을 참조 하 여 읽을 때 유용한 용어 및 정의 목록이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="9094f-106">조직 구성 단위-Active Directory 도메인 서비스 OU (조직 구성 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="9094f-107">페더레이션/교차 풀 – 인터넷 서비스의 MSN 네트워크, AOL® 및 Yahoo®와 같은 다른 IM (인스턴트 메시징) 서비스의 사용자와 통신 하도록 설정할 수 있는 사용자 \! 입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="9094f-108">메일 그룹-사용자 그룹과의 통신을 시작 하는 데 사용 되는 Active Directory 도메인 서비스 사용자 목록을 포함 하는 Active Directory 도메인 서비스의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="9094f-109">Location Info Service-전화 별로 사용 하도록 설정 하 고 구성 하는 경우 E9-1-1) 서비스 9-1-1에 대 한 실제 위치 검색을 사용할 수 있는 Lync Server 2013 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="9094f-110">미국 전화 번호-인바운드 및 아웃 바운드 통화 및 RNL (역방향 번호 조회)를 라우팅하는 데 사용 되는 SIP URI 외에 사용자에 게 할당 되는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="9094f-111">UserProvisioningTool.exe을 사용 하 여 사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="9094f-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="9094f-112">부하 시뮬레이션을 위해 사용자 및 연락처를 만들려면 Lync Server 사용자 프로 비전 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="9094f-113">Lync server 사용자 프로 비전 도구는 Lync Server 스트레스 및 성능 도구 패키지와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="9094f-114">프런트 엔드 서버 또는 Standard Edition 서버에서 CapacityPlanningTool.msi (패키지 설치 관리자)가 실행 되었는지 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="9094f-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="9094f-115">프런트 엔드 서버 또는 Standard Edition Server에서 파일 UserProvisioningTool.exe (% InstalledDirectory% LyncStressAndPerfTool lyncstress)을 실행 하 여 Lync Server 사용자 프로 비전 도구를 시작 합니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="9094f-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9094f-116">UserProvisioningTool.exe를 실행 하려면 Domain Admins 보안 그룹의 구성원으로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="9094f-117">UserProvisioningTool.exe에서는 새 Active Directory 도메인 서비스 사용자를 만들고 구성 하므로이 컨텍스트에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9094f-118">많은 수의 사용자를 만들 때 (1만 이상), 고급 컴퓨터에서 UserProvisioningTool.exe를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="9094f-119">사용자가 만들어지는 동안에도 도메인 컨트롤러의 부하가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="9094f-120">Lync Server 사용자 프로 비전 도구가 열리면 **구성을** 클릭 하 고 **구성 로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="9094f-121">사용자 및 연락처 구성을 시작 하려면 패키지에 포함 된 기본 파일을 SampleData.xml에 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="9094f-122">이렇게 하면 시스템에서 수정 해야 하는 예제 데이터를 사용 하 여 필드를 미리 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="9094f-123">이미 사용자 지정 설정을 포함 하는 미리 구성 된 XML 파일이 있는 경우 해당 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="9094f-124">다음 섹션에서 설명 하는 대로 Lync Server 사용자 프로 비전 도구의 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="9094f-125">![사용자 만들기 탭](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "사용자 만들기 탭")</span><span class="sxs-lookup"><span data-stu-id="9094f-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="9094f-126">서버 옵션을 구성 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="9094f-127">**프런트 엔드 풀 FQDN**에 사용자를 호스트 하려는 Standard Edition Server 또는 프런트 엔드 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="9094f-128">**사용자 이름 접두사**에 테스트용으로 사용자 이름을 만드는 데 사용할 접두사를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="9094f-129">**암호**에서 모든 테스트 사용자 계정에 적용 되는 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="9094f-130">**Sip 도메인**에서 테스트 사용자의 sip Uri (Uniform resource identifier)에 사용할 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="9094f-131">**계정 도메인**에 테스트 사용자를 만들 현재 Active Directory 도메인 서비스 도메인의 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="9094f-132">**조직 구성 단위**에 사용자 개체를 만들 Active Directory 도메인 서비스 OU의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="9094f-133">OU가 없는 경우에는 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="9094f-134">**전화 지역 번호**에 사용자 계정 테스트에 사용할 3 자리 지역 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="9094f-135">전화 번호 지역 코드가 Active Directory 도메인 서비스의 다른 사용자 지역 코드와 충돌 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="9094f-136">Enterprise Voice에 대 한 테스트 사용자를 사용 하도록 설정 하려면 **음성 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="9094f-137">**사용자 수**에서 만들려는 테스트 사용자의 총 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="9094f-138">**시작 인덱스**에서 사용자 이름 접두사에 대 한 접미사로 사용 되는 시작 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="9094f-139">사용자 만들기 단추</span><span class="sxs-lookup"><span data-stu-id="9094f-139">Create Users Button</span></span>

<span data-ttu-id="9094f-140">사용자 만들기 단추를 클릭 하면 모든 입력 매개 변수가 유효성 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="9094f-141">유효성 검사 오류가 있으면 해당 입력 값을 수정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="9094f-142">모든 입력 값이 올바르면 Active Directory 도메인 서비스에서 사용자를 만드는 것이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="9094f-143">진행률 표시줄이이 폼의 아래쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="9094f-144">진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="9094f-145">사용자 만들기가 느린 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-145">User Creation is a slow process.</span></span> <span data-ttu-id="9094f-146">몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-146">It can take several minutes.</span></span> <span data-ttu-id="9094f-147">사용자 수가 매우 큰 경우 프로세스에 몇 시간이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="9094f-148">사용자가 이미 있는 경우에는 변경 내용으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="9094f-149">범위에 있는 사용자 중 하나로 로그온 하 여 사용자가 만들어졌는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="9094f-150">사용자 접두사, 사용자 번호 및 @sipDomain를 지정 된 암호와 함께 사용자 이름 (예: LyncUser10@contoso.net)으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="9094f-151">사용자 삭제 단추</span><span class="sxs-lookup"><span data-stu-id="9094f-151">Delete Users Button</span></span>

<span data-ttu-id="9094f-152">사용자 삭제 단추를 클릭 하면 모든 입력 매개 변수가 유효성 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="9094f-153">유효성 검사 오류가 있으면 해당 입력 값을 수정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="9094f-154">모든 입력 값이 올바르면 Active Directory 도메인 서비스에서 사용자를 사용 하지 않도록 설정 하 고 삭제 하는 것이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="9094f-155">진행률 표시줄이이 폼의 아래쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="9094f-156">진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="9094f-157">미국 형식으로 된 전화 번호만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="9094f-158">전화 번호는 항상 사용자에 게 할당 되며 UserProvisioningTool.exe에서 만든 모든 사용자가 Enterprise Voice를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="9094f-159">전화 회의 자동 전화 교환 또는 UC-PSTN 통화와 같이 해당 번호를 사용 하는 모든 시나리오에서이 전화 번호를 사용 하 여 통화를 올바르게 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="9094f-160">따라서 모든 사용자에 게 고유한 전화 번호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="9094f-161">사용자를 두 번 만들어야 하는 경우 다른 지역 번호를 사용 하지 않거나 이전 사용자가 <STRONG>Disable-CsUser</STRONG> cmdlet을 사용 하 여 사용 하지 않도록 설정한 경우에만 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="9094f-162">연락처를 만들기 전에 먼저 사용자 탭에서 수행 하는 전체 복제를 완료 해야 합니다. 사용자를 방금 만든 경우 Lync Server 복제가 완료 될 때까지 기다린 후 데이터베이스의 사용자 계정을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="9094f-163">사용자가 복제를 완료 하지 않은 경우 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="9094f-164">Lync Server 2013 프런트 엔드 서비스가 시작 되었거나 마지막 사용자에 대해 <STRONG>csuser</STRONG> cmdlet을 성공적으로 실행 하 여 사용자가 복제를 완료 한 경우를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="9094f-165">대화 상대 만들기 탭</span><span class="sxs-lookup"><span data-stu-id="9094f-165">Contacts Creation Tab</span></span>

<span data-ttu-id="9094f-166">연락처 만들기 탭에서는 사용자의 연락처에 대 한 세부 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="9094f-167">![연락처 만들기 탭](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "연락처 만들기 탭")</span><span class="sxs-lookup"><span data-stu-id="9094f-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="9094f-168">사용자의 연락처를 구성 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="9094f-169">사용자 당 평균 대화 상대 수에서 각 사용자의 대화 상대 목록에 채울 평균 대화 상대 개수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="9094f-170">모든 사용자에 대해 동일한 수의 연락처를 만들려면 고정 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="9094f-171">사용자에 대해 만들어진 연락처 수를 변경 하려면 확인란을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="9094f-172">사용자 당 평균 대화 상대 그룹 수에서 사용자 당 대화 상대 그룹의 개수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="9094f-173">이 숫자는 사용자 당 평균 대화 상대 수보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="9094f-174">페더레이션/교차 풀 대화 상대 백분율에서 0에서 100 사이의 숫자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="9094f-175">이 연락처의 백분율은 페더레이션 사용자와 함께 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="9094f-176">페더레이션/교차 풀 사용자 접두사에서 로컬 사용자의 대화 상대 목록에 추가 될 페더레이션 사용자의 사용자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="9094f-177">페더레이션/교차 풀 사용자 SIP 도메인에서 페더레이션 사용자의 SIP 도메인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9094f-178">연락처를 만들 때 어떤 사용자도 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="9094f-179">사용자 만들기 탭에서 매개 변수가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="9094f-180">연락처를 만들 사용자 범위는 사용자 만들기 탭에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="9094f-181">연락처 만들기를 클릭 하 여 연락처 만들기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="9094f-182">이 프로세스는 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-182">This process can take several minutes.</span></span> <span data-ttu-id="9094f-183">작업이 완료 되 면 "작업을 성공적으로 완료 했습니다." 라는 메시지가 표시 되는 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="9094f-184">사용자 만들기 탭에서 만든 사용자로 로그온 하 여 만든 연락처의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9094f-185">연락처가 만들어지면이 도구는 대상 풀에서 모든 프런트 엔드 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="9094f-186">이 작업을 통해 만들어진 연락처 수에 따라 프런트 엔드 서버를 시작 하는 데 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="9094f-187">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="9094f-187">Distribution List</span></span>

<span data-ttu-id="9094f-188">Lync Server 2013 스트레스 및 성능 도구의 기능 중 하나는 Lync 2013에서 메일 그룹 (DL) 확장 기능을 시뮬레이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="9094f-189">UserProvisioningTool에서 DL 확장을 사용 하도록 설정 하지 않을 경우이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="9094f-190">![메일 그룹 만들기 탭](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "메일 그룹 만들기 탭")</span><span class="sxs-lookup"><span data-stu-id="9094f-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="9094f-191">메일 그룹 탭에서는 스트레스 및 성능 도구에서 메일 그룹 확장 기능에 사용할 Dl을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="9094f-192">Dl을 만들기 전에 Lync Server 2013이 이미 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="9094f-193">Lync Server 2013 ForestPrep를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="9094f-194">그렇지 않으면 DL 특성이 Active Directory 도메인 서비스 스키마에 없고 도구에서 Dl을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="9094f-195">메일 그룹을 구성 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="9094f-196">메일 그룹 수에서 만들려는 Dl의 총 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="9094f-197">(사용자 수를 두 번 사용 하는 것이 좋습니다.)</span><span class="sxs-lookup"><span data-stu-id="9094f-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="9094f-198">0부터 n-1까지 번호가 매겨집니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="9094f-199">메일 그룹 접두사에서 Dl에 포함 될 접두사를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="9094f-200">예를 들어 100 Dl과 testDL의 접두사를 지정 하는 경우 Dl의 이름은 testDL0, testDL1 등이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="9094f-201">배포의 최소 구성원 목록에서 각 메일 그룹에 추가할 최소 사용자 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="9094f-202">최대 구성원 목록에서 각 메일 그룹에 추가할 최대 사용자 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="9094f-203">메일 그룹 만들기 단추</span><span class="sxs-lookup"><span data-stu-id="9094f-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="9094f-204">메일 그룹 만들기 단추를 클릭 하면이 도구는 Active Directory 도메인 서비스에 쿼리하여 접두사와 번호와 일치 하는 메일 그룹이 이미 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="9094f-205">이 도구는 아직 없는 항목만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="9094f-206">새로 만든이 메일 그룹에 구성원을 추가 하면 사용자 만들기 탭에 지정 된 범위에서 사용자를 선택 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="9094f-207">위치 정보 서비스 구성 탭</span><span class="sxs-lookup"><span data-stu-id="9094f-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="9094f-208">Lync Server 2013 스트레스 및 성능 도구의 기능 중 하나는 위치 정보 서비스에 대 한 더미 구성 파일을 생성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="9094f-209">일반적으로 위치 정보 서비스는 서버에 대 한 성능에 큰 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="9094f-210">![위치 정보 서비스 구성 탭](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "위치 정보 서비스 구성 탭")</span><span class="sxs-lookup"><span data-stu-id="9094f-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="9094f-211">이 기능을 테스트 하도록 선택한 경우 양식에 언급 된 값을 입력 한 다음 LIS Config 파일 생성 단추를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="9094f-212">이 도구는 LIS \_Subnet.csv, lis \_Switches.csv, Lis \_Ports.csv 및 LISWAP.csv 라는 CSV 파일을 생성 합니다 \_ .</span><span class="sxs-lookup"><span data-stu-id="9094f-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="9094f-213">그런 다음 **CsLisSubnet** Cmdlet, **CsLisSwitch** cmdlet, **CsLisPort** cmdlet 및 **CsWirelessAccessPoint** cmdlet을 각각 사용 하 여 이러한 CSV 파일을 LIS 데이터베이스로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9094f-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

