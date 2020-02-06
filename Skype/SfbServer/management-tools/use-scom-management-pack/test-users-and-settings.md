---
title: 감시자 노드 테스트 사용자 및 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: '요약: 비즈니스용 Skype 서버 가상 거래에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.'
ms.openlocfilehash: ce0c82f6f850c7a2b632c828f938979747d99e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816117"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="70c3b-103">감시자 노드 테스트 사용자 및 설정 구성</span><span class="sxs-lookup"><span data-stu-id="70c3b-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="70c3b-104">**요약:** 비즈니스용 Skype 서버 가상 거래에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="70c3b-105">감시자 노드 역할을 하는 컴퓨터를 구성한 후에는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="70c3b-106">이러한 감시자 노드에서 사용할 [테스트 사용자 계정을 구성](test-users-and-settings.md#testuser) 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="70c3b-107">협상 인증 방법을 사용 하는 경우 **CsTestUserCredential** cmdlet을 사용 하 여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="70c3b-108">감시자 노드 구성 설정을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="70c3b-109">테스트 사용자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="70c3b-109">Configure Test User Accounts</span></span>
<span data-ttu-id="70c3b-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="70c3b-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="70c3b-111">테스트 계정은 실제 사용자를 나타낼 필요는 없지만 유효한 Active Directory 계정 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="70c3b-112">또한 이러한 계정은 비즈니스용 Skype Server에 대해 사용 하도록 설정 되어야 하 고, 유효한 SIP 주소가 있어야 하며, Enterprise Voice에서 사용할 수 있어야 합니다 (테스트-CsPstnPeerToPeerCall 가상 트랜잭션을 사용 하려면).</span><span class="sxs-lookup"><span data-stu-id="70c3b-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="70c3b-113">(가) 서버 인증 방법을 사용 하는 경우에는 이러한 계정이 존재 하는지 확인 하 고 별도로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="70c3b-114">테스트 하려는 각 풀에 대해 최소 두 개의 테스트 사용자를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="70c3b-115">협상 인증 방법을 사용 하는 경우 CsTestUserCredential cmdlet 및 비즈니스용 Skype Server Management Shell을 사용 하 여 이러한 테스트 계정이 가상 트랜잭션과 함께 작동 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="70c3b-116">다음과 같은 명령을 실행 하 여이 작업을 수행 합니다 (이러한 명령은 두 Active Directory 사용자 계정이 생성 되 고이 계정이 비즈니스용 Skype Server에 대해 사용 하도록 설정 되었다고 가정).</span><span class="sxs-lookup"><span data-stu-id="70c3b-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="70c3b-117">SIP 주소는 물론 사용자 이름 및 암호만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="70c3b-118">암호를 포함 하지 않으면 CsTestUserCredential cmdlet에서 해당 정보를 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="70c3b-119">사용자 이름은 앞의 코드 블록에 표시 된 domain name\user name 형식을 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="70c3b-120">테스트 사용자 자격 증명이 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="70c3b-121">다음과 유사한 정보가 각 사용자에 대해 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="70c3b-122">**사용자**</span><span class="sxs-lookup"><span data-stu-id="70c3b-122">**UserName**</span></span>|<span data-ttu-id="70c3b-123">**입력**</span><span class="sxs-lookup"><span data-stu-id="70c3b-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70c3b-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="70c3b-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="70c3b-125">System.webserver</span><span class="sxs-lookup"><span data-stu-id="70c3b-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="70c3b-126">기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="70c3b-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="70c3b-127">테스트 사용자를 만든 후 다음과 같은 명령을 사용 하 여 감시자 노드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="70c3b-128">이 명령은 기본 설정을 사용 하 고 기본적인 가상 트랜잭션 집합을 실행 하는 새 감시자 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="70c3b-129">또한 새 감시자 노드는 테스트 사용자 watcher1@litwareinc.com 및 watcher2@litwareinc.com를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="70c3b-130">감시자 노드가 있는 서버 인증을 사용 하는 경우 두 개의 테스트 계정이 Active Directory 및 비즈니스용 Skype Server에 대해 사용할 수 있는 유효한 사용자 계정이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="70c3b-131">감시자 노드가 협상 인증 방법을 사용 하는 경우 Set-CsTestUserCredential cmdlet을 사용 하 여 감시자 노드에 대해 이러한 사용자 계정도 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="70c3b-132">풀을 직접 대상으로 지정 하는 대신 로그인에 대 한 대상 풀의 자동 검색이 올바르게 구성 되어 있는지 확인 하려면 다음 단계를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="70c3b-133">확장 된 테스트 구성</span><span class="sxs-lookup"><span data-stu-id="70c3b-133">Configuring Extended Tests</span></span>

<span data-ttu-id="70c3b-134">공용 전환 전화 네트워크 연결을 확인 하는 PSTN 테스트를 사용 하도록 설정 하려는 경우 감시자 노드를 설정할 때 몇 가지 추가 구성을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="70c3b-135">먼저 비즈니스용 Skype 서버 관리 셸에서와 유사한 명령을 실행 하 여 테스트 사용자를 PSTN 테스트 형식과 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="70c3b-136">이 명령의 결과는 변수에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="70c3b-137">이 예제에서 변수 이름은 $pstnTest입니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="70c3b-138">그런 다음 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 변수 $pstnTest에 저장 된 테스트 유형을 비즈니스용 Skype 서버 풀에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="70c3b-139">예를 들어 다음 명령은 풀 atl-cs-001.litwareinc.com에 대 한 새 감시자 노드 구성을 만들고, 이전에 만든 두 개의 테스트 사용자를 추가 하 고, PSTN 테스트 형식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="70c3b-140">비즈니스용 Skype Server core 파일과 감시자 노드 컴퓨터에 RTCLocal 데이터베이스를 설치 하지 않은 경우에는 앞의 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="70c3b-141">여러 음성 정책을 테스트 하기 위해 **새로운 CsExtendedTest** cmdlet을 사용 하 여 각 정책에 대 한 확장 테스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="70c3b-142">제공 된 사용자는 원하는 음성 정책으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="70c3b-143">확장 된 테스트는 다음과 같이 쉼표 구분 기호를 사용 하 여 **새 CsWatcherNodeConfiguration** cmdlet에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="70c3b-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="70c3b-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="70c3b-145">**CsWatcherNodeConfiguration** Cmdlet은 테스트 매개 변수를 사용 하지 않고 호출 했기 때문에 새 감시자 노드에는 기본 가상 트랜잭션과 지정 된 확장 가상 트랜잭션만 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="70c3b-146">따라서 감시자 노드는 다음 구성 요소를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="70c3b-147">등록</span><span class="sxs-lookup"><span data-stu-id="70c3b-147">Registration</span></span>
    
- <span data-ttu-id="70c3b-148">메신저</span><span class="sxs-lookup"><span data-stu-id="70c3b-148">IM</span></span>
    
- <span data-ttu-id="70c3b-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="70c3b-149">GroupIM</span></span>
    
- <span data-ttu-id="70c3b-150">P2PAV (피어 투 피어 오디오/비디오 세션)</span><span class="sxs-lookup"><span data-stu-id="70c3b-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="70c3b-151">AvConference (오디오/회의)</span><span class="sxs-lookup"><span data-stu-id="70c3b-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="70c3b-152">현재 상태</span><span class="sxs-lookup"><span data-stu-id="70c3b-152">Presence</span></span>
    
- <span data-ttu-id="70c3b-153">ABS (주소록 서비스)</span><span class="sxs-lookup"><span data-stu-id="70c3b-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="70c3b-154">ABWQ (주소록 웹 서비스)</span><span class="sxs-lookup"><span data-stu-id="70c3b-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="70c3b-155">다음 구성 요소는 기본적으로 테스트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="70c3b-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="70c3b-156">ASConference</span></span>
    
- <span data-ttu-id="70c3b-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="70c3b-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="70c3b-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="70c3b-158">DataConference</span></span>
    
- <span data-ttu-id="70c3b-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="70c3b-159">DialinConferencing</span></span>
    
- <span data-ttu-id="70c3b-160">ExumConnectivity (Exchange 통합 메시징)</span><span class="sxs-lookup"><span data-stu-id="70c3b-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="70c3b-161">JoinLauncher 관리자</span><span class="sxs-lookup"><span data-stu-id="70c3b-161">JoinLauncher</span></span>
    
- <span data-ttu-id="70c3b-162">MCXP2PIM (레거시 모바일 장치 인스턴트 메시지)</span><span class="sxs-lookup"><span data-stu-id="70c3b-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="70c3b-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="70c3b-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="70c3b-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="70c3b-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="70c3b-165">PSTN (PSTN 게이트웨이 통화, 확장 된 테스트로 지정 됨)</span><span class="sxs-lookup"><span data-stu-id="70c3b-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="70c3b-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="70c3b-166">UcwaConference</span></span>
    
- <span data-ttu-id="70c3b-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="70c3b-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="70c3b-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="70c3b-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="70c3b-169">가상 트랜잭션 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="70c3b-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="70c3b-170">감시자 노드가 구성 되 면 Set-CsWatcherNodeConfiguration cmdlet을 사용 하 여 노드에서 가상 트랜잭션을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="70c3b-171">예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가 하려면 Add 메서드와 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="70c3b-172">여러 테스트는 쉼표를 사용 하 여 테스트 이름을 구분 하 여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="70c3b-173">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="70c3b-174">이러한 테스트 중 하나 이상 (예: DataConference)이 감시자 노드에 이미 사용 하도록 설정 되어 있으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="70c3b-175">이 경우 다음과 같은 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="70c3b-176">CsWatcherNodeConfiguration: ' urn: schema: WatcherNode: TestName ' 키 또는 고유 id 제약 조건에 대 한 중복 키 시퀀스 ' DataConference '가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="70c3b-177">이 오류가 발생 하면 변경 내용이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="70c3b-178">중복 테스트가 제거 되 면 명령이 다시 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="70c3b-179">감시자 노드에서 가상 트랜잭션을 제거 하려면 Remove 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="70c3b-180">예를 들어이 명령은 감시자 노드에서 ABWQ 테스트를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="70c3b-181">Replace 메서드를 사용 하 여 현재 사용 가능한 모든 테스트를 하나 이상의 새 테스트로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="70c3b-182">예를 들어 감시자 노드만 IM 테스트를 실행 하도록 하려면 다음 명령을 사용 하 여이를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="70c3b-183">이 명령을 실행 하면 IM을 제외한 지정 된 감시자 노드의 모든 가상 트랜잭션을 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="70c3b-184">감시자 노드 구성 보기 및 테스트</span><span class="sxs-lookup"><span data-stu-id="70c3b-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="70c3b-185">감시자 노드에 할당 된 테스트를 보려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="70c3b-186">이 명령은 노드에 할당 된 가상 트랜잭션에 따라 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="70c3b-187">등록 메신저 GroupIM P2PAV AvConference 현재 상태 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="70c3b-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="70c3b-188">가상 트랜잭션을 알파벳순으로 보려면 다음 명령을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="70c3b-189">감시자 노드가 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="70c3b-190">다음과 같은 정보가 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="70c3b-191">Id: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="70c3b-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="70c3b-192">TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="70c3b-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="70c3b-193">ExtendedTests: {TestUsers = IList<System.webserver>; Name = PSTN 테스트; Te ...}</span><span class="sxs-lookup"><span data-stu-id="70c3b-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="70c3b-194">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="70c3b-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="70c3b-195">PortNumber: 5061</span><span class="sxs-lookup"><span data-stu-id="70c3b-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="70c3b-196">감시자 노드가 올바르게 구성 되었는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="70c3b-197">이 명령은 배포에서 각 감시자 노드를 테스트 하 고 다음 작업이 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="70c3b-198">필수 등록자 역할이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="70c3b-199">필수 레지스트리 키가 생성 됩니다 (Set-CsWatcherNodeConfiguration cmdlet을 실행할 때 완료 됨).</span><span class="sxs-lookup"><span data-stu-id="70c3b-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="70c3b-200">서버에서 올바른 버전의 비즈니스용 Skype 서버를 실행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="70c3b-201">포트가 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="70c3b-202">지정 된 테스트 사용자에 게 필요한 자격 증명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="70c3b-203">감시자 노드 관리</span><span class="sxs-lookup"><span data-stu-id="70c3b-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="70c3b-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="70c3b-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="70c3b-205">감시자 노드에서 실행 되는 가상 트랜잭션을 수정 하는 것 외에도 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 감시자 노드의 사용 여부를 설정 하거나 해제 하 고 해당 테스트를 실행할 때 내부 웹 url 또는 외부 웹 url을 사용 하도록 감시자 노드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="70c3b-206">기본적으로 감시자 노드는 사용 하도록 설정 된 모든 가상 트랜잭션을 정기적으로 실행 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="70c3b-207">그러나 때로는 해당 트랜잭션을 일시 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="70c3b-208">예를 들어 감시자 노드가 네트워크에서 일시적으로 연결이 끊어지면 가상 트랜잭션을 실행할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="70c3b-209">네트워크에 연결 되지 않은 경우 해당 트랜잭션은 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="70c3b-210">감시자 노드를 일시적으로 사용 하지 않도록 설정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="70c3b-211">이 명령은 감시자 노드 atl 감시자 001.litwareinc.com에서 가상 트랜잭션의 실행을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="70c3b-212">가상 트랜잭션의 실행을 다시 시작 하려면 Enabled 속성을 다시 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="70c3b-213">Enabled 속성을 사용 하 여 감시자 노드를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="70c3b-214">감시자 노드를 영구적으로 삭제 하려면 **Remove-CsWatcherNodeConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="70c3b-215">이 명령은 지정 된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거 하 여 해당 컴퓨터가 가상 트랜잭션을 자동으로 실행 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="70c3b-216">그러나이 명령은 System Center 에이전트 파일 또는 비즈니스용 Skype 서버 시스템 파일을 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="70c3b-217">기본적으로 감시자 노드는 테스트를 수행할 때 조직의 외부 웹 Url을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="70c3b-218">그러나 조직의 내부 웹 Url을 사용 하도록 감시자 노드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="70c3b-219">이렇게 하면 관리자가 경계 네트워크 내에 있는 사용자의 URL 액세스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="70c3b-220">외부 Url 대신 내부 Url을 사용 하도록 감시자 노드를 구성 하려면 UseInternalWebURls 속성을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="70c3b-221">이 속성을 False ($False)로 다시 설정 하면 감시자가 다시 한 번 외부 Url을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="70c3b-222">종합 거래에 대 한 특별 한 설정 지침</span><span class="sxs-lookup"><span data-stu-id="70c3b-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="70c3b-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="70c3b-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="70c3b-224">대부분의 가상 트랜잭션은 있는 그대로 감시자 노드에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="70c3b-225">대부분의 경우, 가상 트랜잭션이 감시자 노드 구성 설정에 추가 되는 즉시 감시자 노드는 해당 테스트를 통과 하는 동안 해당 가상 트랜잭션을 사용 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="70c3b-226">그러나 다음 섹션에서 설명 하는 것 처럼 특별 한 설정 지침이 필요한 몇 가지 가상 트랜잭션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="70c3b-227">데이터 회의 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="70c3b-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="70c3b-228">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 먼저 Windows Internet® Explorer를 사용 하지 않도록 설정 하 고 네트워크에 대 한 인터넷 브라우저 프록시 설정을 사용할 수 없는 경우에만 데이터 회의 종합 트랜잭션을 실행 하는 것이 좋습니다. 서비스 계정으로 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="70c3b-229">감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **액세서리**를 차례로 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="70c3b-230">콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-230">In the console window, type the following command and then press ENTER.</span></span> 
    
```console
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="70c3b-231">명령 창에 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-231">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="70c3b-232">BITSAdmin은 더 이상 사용 되지 않으며 이후 버전의 Windows에서 사용할 수 없는 것으로 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-232">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="70c3b-233">Bits 서비스에 대 한 관리 도구가 이제 BITS PowerShell cmdlet에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-233">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="70c3b-234">계정 NetworkService에 대 한 인터넷 프록시 설정이 NO_PROXY으로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-234">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="70c3b-235">(connection = default)</span><span class="sxs-lookup"><span data-stu-id="70c3b-235">(connection = default)</span></span>
  
<span data-ttu-id="70c3b-236">이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-236">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="70c3b-237">Exchange 통합 메시징 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="70c3b-237">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="70c3b-238">UM (통합 메시징) 통합 트랜잭션은 테스트 사용자가 Exchange의 보이스 메일 계정에 연결할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-238">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="70c3b-239">테스트 사용자는 보이스 메일 계정을 사용 하 여 미리 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-239">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="70c3b-240">영구 채팅 종합 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="70c3b-240">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="70c3b-241">영구 채팅 종합 트랜잭션을 사용 하려면 먼저 채널을 만들고 사용자에 게이를 사용 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-241">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="70c3b-242">영구 채팅 종합 트랜잭션을 사용 하 여이 채널을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-242">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="70c3b-243">엔터프라이즈 내에서 실행 되어야 하는 설치 작업을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-243">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="70c3b-244">서버 이외의 컴퓨터에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RBAC (역할 기반 액세스 제어)에 대 한 CsPersistentChatAdministrators 역할의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-244">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="70c3b-245">서버 자체에서 실행 되는 경우 cmdlet을 실행 하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-245">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="70c3b-246">PSTN 피어 투 피어 통화 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="70c3b-246">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="70c3b-247">테스트-CsPstnPeerToPeerCall 합성 트랜잭션은 PSTN (공개 교환 전화 네트워크)을 통해 전화를 걸고 받는 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-247">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="70c3b-248">이 가상 트랜잭션을 실행 하려면 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-248">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="70c3b-249">UC를 사용 하는 두 테스트 사용자 (호출자와 받는 사람)</span><span class="sxs-lookup"><span data-stu-id="70c3b-249">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="70c3b-250">각 사용자 계정에 대 한 직접 안쪽 전화 걸기 (번호)</span><span class="sxs-lookup"><span data-stu-id="70c3b-250">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="70c3b-251">VoIP 정책 및 음성 경로-수신자의 번호로 전화를 걸어 PSTN 게이트웨이에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-251">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="70c3b-252">전화를 건 번호에 기반 하 여 전화를 받는 사람의 홈 풀로 다시 라우팅하는 통화와 미디어를 수락 하는 PSTN 게이트웨이.</span><span class="sxs-lookup"><span data-stu-id="70c3b-252">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="70c3b-253">통합 된 대화 상대 저장소 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="70c3b-253">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="70c3b-254">통합 된 연락처 저장소 가상 트랜잭션은 Exchange에서 사용자를 대신 하 여 연락처를 검색 하는 비즈니스용 Skype 서버의 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-254">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="70c3b-255">이 가상 트랜잭션을 사용 하려면 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-255">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="70c3b-256">Lyss-Exchange server에서 서버 인증을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-256">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="70c3b-257">테스트 사용자는 유효한 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-257">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="70c3b-258">이러한 조건이 충족 되 면 다음 Windows PowerShell cmdlet을 실행 하 여 테스트 사용자의 연락처 목록을 Exchange로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-258">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="70c3b-259">테스트 사용자 연락처 목록을 Exchange로 마이그레이션하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-259">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="70c3b-260">마이그레이션 진행 상황을 모니터링 하기 위해-설치 플래그 없이 같은 명령줄을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-260">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="70c3b-261">이 명령줄은 마이그레이션이 완료 된 후에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-261">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="70c3b-262">XMPP 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="70c3b-262">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="70c3b-263">XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) IM 가상 트랜잭션을 사용 하려면 하나 이상의 페더레이션 도메인으로 XMPP 기능을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-263">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="70c3b-264">XMPP 가상 트랜잭션을 사용 하도록 설정 하려면 라우팅할 수 있는 XMPP 도메인의 사용자 계정에 XmppTestReceiverMailAddress 매개 변수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-264">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="70c3b-265">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-265">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="70c3b-266">이 예제에서는 비즈니스용 Skype 서버 규칙이 있어야 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-266">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="70c3b-267">XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-267">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="70c3b-268">자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70c3b-268">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="70c3b-269">VIS (비디오 Interop 서버) 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="70c3b-269">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="70c3b-270">VIS (동영상 Interop 서버) 가상 트랜잭션은 가상 트랜잭션 지원 파일 ([VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921))을 다운로드 하 고 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-270">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="70c3b-271">VISSTSupportPackage를 설치 하려면 msi에 대 한 종속성 (시스템 요구 사항 아래)이 이미 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-271">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="70c3b-272">간단한 설치를 수행 하려면 VISSTSupportPackage를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-272">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="70c3b-273">.Msi는 "%ProgramFiles%\VIS 가상 트랜잭션 지원 패키지" 경로의 모든 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-273">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="70c3b-274">VIS 가상 트랜잭션을 실행 하는 방법에 대 한 자세한 내용은 [테스트-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70c3b-274">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="70c3b-275">가상 트랜잭션의 실행 빈도 변경</span><span class="sxs-lookup"><span data-stu-id="70c3b-275">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="70c3b-276"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="70c3b-276"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="70c3b-277">기본적으로 가상 트랜잭션은 구성 된 사용자와 15 분 마다 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-277">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="70c3b-278">가상 트랜잭션은 두 가지 가상 트랜잭션이 서로 충돌 하지 않도록 사용자 집합 내에서 순차적으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-278">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="70c3b-279">모든 가상 트랜잭션을 완료 하는 데 걸리는 시간을 제공 하기 위해 간격이 더 길게 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-279">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="70c3b-280">가상 트랜잭션을 더 자주 실행 하는 것이 바람직한 경우 특정 사용자 집합을 사용 하 여 실행 되는 가상 트랜잭션의 수를 줄여야 하 여 테스트를 원하는 시간 범위에서 가끔씩 네트워크 지연에 대 한 버퍼와 함께 완료할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-280">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="70c3b-281">더 많은 가상 트랜잭션을 실행 하는 것이 바람직한 경우 추가 가상 트랜잭션을 실행 하기 위해 더 많은 사용자 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-281">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="70c3b-282">가상 트랜잭션을 실행 하는 빈도를 변경 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-282">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="70c3b-283">System Center Operations Manager를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-283">Open System Center Operations Manager.</span></span> <span data-ttu-id="70c3b-284">제작 섹션을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-284">Click Authoring section.</span></span> <span data-ttu-id="70c3b-285">규칙 섹션 (작성 중)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-285">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="70c3b-286">규칙 섹션에서 "기본 종합 트랜잭션 러너 성과 수집 규칙"이 포함 된 규칙을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-286">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="70c3b-287">규칙을 마우스 오른쪽 단추로 클릭 하 고 재정의를 선택한 다음 규칙 재정의를 선택 하 고 "class: Pool 감시자"의 모든 개체에 대해 "를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-287">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="70c3b-288">속성 재정의 창에서 매개 변수 이름 "Frequency"를 선택 하 고 재정의 값을 원하는 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-288">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="70c3b-289">동일한 창에서이 재정의를 적용 해야 하는 관리 팩을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-289">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="70c3b-290">종합 거래에 대 한 풍부한 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="70c3b-290">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="70c3b-291"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="70c3b-291"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="70c3b-292">가상 트랜잭션은 시스템의 문제를 식별 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-292">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="70c3b-293">예를 들어 테스트-CsRegistration cmdlet은 사용자가 비즈니스용 Skype Server에 등록 하는 데 어려움을 겪고 있다는 사실을 관리자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-293">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="70c3b-294">그러나 실패의 실제 원인을 확인 하려면 추가 세부 정보가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-294">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="70c3b-295">이러한 이유로 가상 트랜잭션은 풍부한 로깅을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-295">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="70c3b-296">다양 한 로깅 기능을 통해 가상 트랜잭션을는 하는 각 활동에 대해 다음 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-296">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="70c3b-297">활동이 시작 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-297">The time that the activity started.</span></span>
    
- <span data-ttu-id="70c3b-298">작업이 완료 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-298">The time that the activity finished.</span></span>
    
- <span data-ttu-id="70c3b-299">수행 된 작업 (예: 회의 만들기, 참가 또는 종료, 비즈니스용 Skype Server에 로그인, 인스턴트 메시지 보내기)</span><span class="sxs-lookup"><span data-stu-id="70c3b-299">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="70c3b-300">활동이 실행 될 때 생성 되는 정보, 세부 정보, 경고 또는 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="70c3b-300">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="70c3b-301">SIP 등록 메시지.</span><span class="sxs-lookup"><span data-stu-id="70c3b-301">SIP registration messages.</span></span>
    
- <span data-ttu-id="70c3b-302">활동이 실행 될 때 생성 되는 예외 레코드 또는 진단 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-302">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="70c3b-303">활동 실행의 순 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-303">The net result of running the activity.</span></span>
    
<span data-ttu-id="70c3b-304">이 정보는 가상 트랜잭션을 실행할 때마다 자동으로 생성 되지만 자동으로 표시 되거나 로그 파일에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-304">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="70c3b-305">가상 트랜잭션을 수동으로 실행 하는 경우 OutLoggerVariable 매개 변수를 사용 하 여 정보가 저장 되는 Windows PowerShell 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-305">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="70c3b-306">여기서는 두 가지 방법 중 하나를 사용 하 여 XML 또는 HTML 형식의 풍부한 로그에서 오류 메시지를 저장 및/또는 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-306">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="70c3b-307">문제 해결 정보를 검색 하려면 OutLoggerVariable 매개 변수를 지정 하 고 다음을 선택 하는 변수 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-307">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="70c3b-308">변수 이름 앞에 $ 문자를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="70c3b-308">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="70c3b-309">RegistrationTest ($RegistrationTest 아님) 등의 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-309">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="70c3b-310">이 명령을 실행 하면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-310">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="70c3b-311">대상 Fqdn: atl-cs-001.litwareinc.com Result: 실패 한 지연: 00:00:00 오류 메시지:이 컴퓨터에는 할당 된 인증서가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-311">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="70c3b-312">진단:이 오류 메시지에 대 한 자세한 내용은 여기에 표시 된 것 보다 더 자세히 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-312">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="70c3b-313">HTML 형식으로이 정보에 액세스 하려면 다음과 유사한 명령을 사용 하 여 가변 RegistrationTest에 저장 된 정보를 HTML 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-313">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="70c3b-314">또는 ToXML () 메서드를 사용 하 여 데이터를 XML 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-314">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="70c3b-315">Windows Internet Explorer, Microsoft Visual Studio 또는 HTML/XML 파일을 열 수 있는 다른 응용 프로그램을 사용 하 여 이러한 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-315">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="70c3b-316">System Center 내에서 실행 되는 가상 트랜잭션은 오류에 대 한 이러한 로그 파일을 자동으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-316">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="70c3b-317">비즈니스용 Skype Server PowerShell이 가상 트랜잭션을 로드 하 고 실행할 수 있으려면 실행이 실패 하는 경우 이러한 로그가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-317">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="70c3b-318">기본적으로 비즈니스용 Skype 서버는 공유 되지 않는 폴더에 로그 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-318">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="70c3b-319">이러한 로그에 쉽게 액세스할 수 있게 하려면이 폴더를 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c3b-319">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="70c3b-320">예: \\atl-감시자-litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="70c3b-320">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
