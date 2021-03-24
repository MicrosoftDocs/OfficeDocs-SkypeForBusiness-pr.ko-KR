---
title: 감시자 노드 테스트 사용자 및 설정 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '요약: 비즈니스용 Skype 서버 가상 트랜잭션에 대한 테스트 사용자 계정 및 감시자 노드 설정을 구성합니다.'
ms.openlocfilehash: 4069b1b51dc826beb631306e941eb40146188f42
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111604"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="4eeba-103">감시자 노드 테스트 사용자 및 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4eeba-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="4eeba-104">**요약:** 비즈니스용 Skype 서버 가상 트랜잭션에 대한 테스트 사용자 계정 및 감시자 노드 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="4eeba-105">감시자 노드로 사용할 컴퓨터를 구성한 후 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="4eeba-106">[이러한 감시자 노드에서](test-users-and-settings.md#testuser) 사용할 테스트 사용자 계정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="4eeba-107">협상 인증 방법을 사용하는 경우 **Set-CsTestUserCredential** cmdlet을 사용하여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="4eeba-108">감시자 노드 구성 설정을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="4eeba-109">테스트 사용자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="4eeba-109">Configure Test User Accounts</span></span>
<span data-ttu-id="4eeba-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="4eeba-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="4eeba-111">테스트 계정은 실제 사용자만 나타내는 것은 아니며 유효한 Active Directory 계정이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="4eeba-112">또한 이러한 계정은 비즈니스용 Skype 서버에 대해 사용하도록 설정해야 합니다. 유효한 SIP 주소가 있어야 합니다. 가상 트랜잭션을 사용하려면 Enterprise Voice 사용하도록 설정해야 Test-CsPstnPeerToPeerCall 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="4eeba-113">TrustedServer 인증 방법을 사용하는 경우 이러한 계정이 있는지 확인하여 다음에 따라 구성하기만하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="4eeba-114">테스트할 각 풀에 대해 두 개 이상의 테스트 사용자를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="4eeba-115">협상 인증 방법을 사용하는 경우 Set-CsTestUserCredential cmdlet 및 비즈니스용 Skype 서버 관리 셸을 사용하여 이러한 테스트 계정이 가상 트랜잭션에서 작동하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="4eeba-116">다음 명령과 유사한 명령을 실행하여 이 작업을 실행합니다. 이러한 명령은 두 개의 Active Directory 사용자 계정이 만들어졌다고 가정하고 이러한 계정이 비즈니스용 Skype 서버에서 사용하도록 설정되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="4eeba-117">SIP 주소뿐만 아니라 사용자 이름과 암호도 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="4eeba-118">암호를 포함하지 않는 경우 Set-CsTestUserCredential cmdlet에 해당 정보를 입력하라는 메시지가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="4eeba-119">이전 코드 블록에 표시된 도메인 이름\사용자 이름 형식을 사용하여 사용자 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="4eeba-120">테스트 사용자 자격 증명이 만들어졌다는 확인을 위해 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="4eeba-121">이와 유사한 정보는 각 사용자에 대해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="4eeba-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="4eeba-122">**UserName**</span></span>|<span data-ttu-id="4eeba-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="4eeba-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4eeba-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="4eeba-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="4eeba-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="4eeba-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="4eeba-126">기본 가상 트랜잭션을 통해 기본 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="4eeba-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="4eeba-127">테스트 사용자를 만든 후 다음 명령을 사용하여 감시자 노드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="4eeba-128">이 명령은 기본 설정을 사용하는 새 감시자 노드를 만들고 기본 가상 트랜잭션 집합을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="4eeba-129">또한 새 감시자 노드는 테스트 사용자 및 watcher1@litwareinc.com watcher2@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4eeba-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="4eeba-130">감시자 노드에서 TrustedServer 인증을 사용하는 경우 두 테스트 계정은 Active Directory 및 비즈니스용 Skype 서버에 대해 사용하도록 설정된 유효한 사용자 계정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="4eeba-131">감시자 노드에서 협상 인증 방법을 사용하는 경우 감시자 노드에 대해 이러한 사용자 계정도 이 cmdlet을 사용하여 Set-CsTestUserCredential 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="4eeba-132">풀을 직접 대상으로 지정하는 대신 로그인할 대상 풀의 자동 검색이 올바르게 구성되어 있는지 확인하려면 다음 단계를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="4eeba-133">확장 테스트 구성</span><span class="sxs-lookup"><span data-stu-id="4eeba-133">Configuring Extended Tests</span></span>

<span data-ttu-id="4eeba-134">PSTN 테스트를 사용하도록 설정하여 공용 전화망과의 연결을 확인하려면 감시자 노드를 설정할 때 몇 가지 추가 구성을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="4eeba-135">먼저 비즈니스용 Skype 서버 관리 셸에서 이와 유사한 명령을 실행하여 테스트 사용자를 PSTN 테스트 유형과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="4eeba-136">이 명령의 결과는 변수에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="4eeba-137">이 예제에서는 변수의 이름이 $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="4eeba-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="4eeba-138">다음으로 **New-CsWatcherNodeConfiguration** cmdlet을 사용하여 테스트 유형(변수 $pstnTest에 저장)을 비즈니스용 Skype 서버 풀에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="4eeba-139">예를 들어 다음 명령은 이전에 만든 두 테스트 사용자를 추가하고 atl-cs-001.litwareinc.com PSTN 테스트 유형을 추가하는 풀 풀에 대한 새 감시자 노드 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="4eeba-140">감시자 노드 컴퓨터에 비즈니스용 Skype 서버 핵심 파일 및 RTCLocal 데이터베이스를 설치하지 않은 경우 위의 명령이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="4eeba-141">여러 음성 정책을 테스트하기 위해 **New-CsExtendedTest** cmdlet을 사용하여 각 정책에 대한 확장 테스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="4eeba-142">제공된 사용자는 원하는 음성 정책으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="4eeba-143">확장 테스트는 **New-CsWatcherNodeConfiguration** cmdlet에 comma-delimiters를 사용하여 다음을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="4eeba-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="4eeba-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="4eeba-145">Tests 매개 변수를 사용하지 않고 **New-CsWatcherNodeConfiguration** cmdlet을 호출하기 때문에 새 감시자 노드에 대해 기본 가상 트랜잭션 및 지정된 확장 가상 트랜잭션만 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="4eeba-146">따라서 감시자 노드는 다음 구성 요소를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="4eeba-147">Registration</span><span class="sxs-lookup"><span data-stu-id="4eeba-147">Registration</span></span>
    
- <span data-ttu-id="4eeba-148">IM</span><span class="sxs-lookup"><span data-stu-id="4eeba-148">IM</span></span>
    
- <span data-ttu-id="4eeba-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="4eeba-149">GroupIM</span></span>
    
- <span data-ttu-id="4eeba-150">P2PAV(피어 투 피어 오디오/비디오 세션)</span><span class="sxs-lookup"><span data-stu-id="4eeba-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="4eeba-151">AvConference(오디오/회의)</span><span class="sxs-lookup"><span data-stu-id="4eeba-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="4eeba-152">현재 상태</span><span class="sxs-lookup"><span data-stu-id="4eeba-152">Presence</span></span>
    
- <span data-ttu-id="4eeba-153">ABS(주소장 서비스)</span><span class="sxs-lookup"><span data-stu-id="4eeba-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="4eeba-154">ABWQ(주소 예약 웹 서비스)</span><span class="sxs-lookup"><span data-stu-id="4eeba-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="4eeba-155">다음 구성 요소는 기본적으로 테스트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="4eeba-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="4eeba-156">ASConference</span></span>
    
- <span data-ttu-id="4eeba-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="4eeba-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="4eeba-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="4eeba-158">DataConference</span></span>
    
- <span data-ttu-id="4eeba-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="4eeba-159">DialinConferencing</span></span>
    
- <span data-ttu-id="4eeba-160">ExumConnectivity(Exchange 통합 메시징)</span><span class="sxs-lookup"><span data-stu-id="4eeba-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="4eeba-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="4eeba-161">JoinLauncher</span></span>
    
- <span data-ttu-id="4eeba-162">MCXP2PIM(레거시 모바일 장치 인스턴트 메시징)</span><span class="sxs-lookup"><span data-stu-id="4eeba-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="4eeba-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="4eeba-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="4eeba-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="4eeba-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="4eeba-165">PSTN(확장 테스트로 지정된 PSTN 게이트웨이 통화)</span><span class="sxs-lookup"><span data-stu-id="4eeba-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="4eeba-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="4eeba-166">UcwaConference</span></span>
    
- <span data-ttu-id="4eeba-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="4eeba-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="4eeba-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="4eeba-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="4eeba-169">가상 트랜잭션 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="4eeba-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="4eeba-170">감시자 노드를 구성한 후 Set-CsWatcherNodeConfiguration cmdlet을 사용하여 노드에서 가상 트랜잭션을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="4eeba-171">예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가하기 위해 Add 메서드 및 다음과 같은 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="4eeba-172">테스트 이름을 콤보로 구분하여 여러 테스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="4eeba-173">예:</span><span class="sxs-lookup"><span data-stu-id="4eeba-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="4eeba-174">이러한 테스트 중 하나 이상(예: DataConference)이 감시자 노드에서 이미 활성화된 경우 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="4eeba-175">이 경우 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="4eeba-176">Set-CsWatcherNodeConfiguration : 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' 키 또는 고유 ID 제약 조건에 대한 중복 키 시퀀스 'DataConference'가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="4eeba-177">이 오류가 발생하면 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="4eeba-178">중복 테스트를 제거한 후 명령을 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="4eeba-179">감시자 노드에서 가상 트랜잭션을 제거하려면 Remove 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="4eeba-180">예를 들어 다음 명령은 감시자 노드에서 ABWQ 테스트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="4eeba-181">Replace 메서드를 사용하여 현재 사용하도록 설정된 모든 테스트를 하나 이상의 새 테스트로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="4eeba-182">예를 들어 감시자 노드가 IM 테스트만 실행하도록 하려는 경우 다음 명령을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="4eeba-183">이 명령을 실행하면 지정된 감시자 노드의 모든 가상 트랜잭션이 IM을 제외하고 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="4eeba-184">감시자 노드 구성 보기 및 테스트</span><span class="sxs-lookup"><span data-stu-id="4eeba-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="4eeba-185">감시자 노드에 할당된 테스트를 확인하려는 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="4eeba-186">이 명령은 노드에 할당된 가상 트랜잭션에 따라 이와 유사한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="4eeba-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="4eeba-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="4eeba-188">가상 트랜잭션을 사전순으로 보시다가 다음 명령을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="4eeba-189">감시자 노드가 만들어졌다는 확인을 위해 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="4eeba-190">이와 유사한 정보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="4eeba-191">ID : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4eeba-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="4eeba-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="4eeba-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="4eeba-193">ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="4eeba-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="4eeba-194">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4eeba-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="4eeba-195">PortNumber : 5061</span><span class="sxs-lookup"><span data-stu-id="4eeba-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="4eeba-196">감시자 노드가 올바르게 구성되어 있는지 확인하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="4eeba-197">이 명령은 배포의 각 감시자 노드를 테스트하고 다음 작업이 완료된지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="4eeba-198">필수 등록자 역할이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="4eeba-199">필수 레지스트리 키가 만들어집니다(cmdlet을 Set-CsWatcherNodeConfiguration 완료).</span><span class="sxs-lookup"><span data-stu-id="4eeba-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="4eeba-200">서버에서 올바른 버전의 비즈니스용 Skype 서버를 실행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="4eeba-201">포트가 올바르게 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="4eeba-202">할당된 테스트 사용자에게는 필수 자격 증명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="4eeba-203">감시자 노드 관리</span><span class="sxs-lookup"><span data-stu-id="4eeba-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="4eeba-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="4eeba-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="4eeba-205">감시자 노드에서 실행되는 가상 트랜잭션을 수정하는 것 외에도 **Set-CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드를 설정 및 사용하지 않습니다. 그리고 테스트를 실행할 때 내부 웹 URL 또는 외부 웹 URL을 사용하도록 감시자 노드를 구성하는 등 두 가지 중요한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="4eeba-206">기본적으로 감시자 노드는 설정된 모든 가상 트랜잭션을 주기적으로 실행하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="4eeba-207">그러나 이러한 트랜잭션을 일시 중단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="4eeba-208">예를 들어 감시자 노드가 일시적으로 네트워크에서 연결이 해제된 경우에는 가상 트랜잭션을 실행할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="4eeba-209">네트워크 연결이 없는 경우 해당 트랜잭션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="4eeba-210">감시자 노드를 일시적으로 사용하지 않도록 설정하기 위해 비즈니스용 Skype 서버 관리 셸에서 이와 유사한 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="4eeba-211">이 명령은 감시자 노드 atl 감시자 노드에서 가상 트랜잭션을 실행하지 않도록 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4eeba-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="4eeba-212">가상 트랜잭션 실행을 다시 시작하려면 Enabled 속성을 다시 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="4eeba-213">Enabled 속성을 사용하면 감시자 노드를 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="4eeba-214">감시자 노드를 영구적으로 삭제하려면 **Remove-CsWatcherNodeConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="4eeba-215">이 명령은 지정된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거하여 해당 컴퓨터가 가상 트랜잭션을 자동으로 실행하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="4eeba-216">그러나 이 명령은 System Center 에이전트 파일 또는 비즈니스용 Skype 서버 시스템 파일을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="4eeba-217">기본적으로 감시자 노드는 테스트를 수행 할 때 조직의 외부 웹 URL을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="4eeba-218">그러나 조직의 내부 웹 URL을 사용하도록 감시자 노드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="4eeba-219">이렇게 하면 관리자가 경계 네트워크 내부에 있는 사용자에 대한 URL 액세스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="4eeba-220">외부 URL 대신 내부 URL을 사용하도록 감시자 노드를 구성하기 위해 UseInternalWebURls 속성을 True($True) 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="4eeba-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="4eeba-221">이 속성을 기본값 False($False)로 다시 설정하면 감시자는 외부 URL을 다시 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="4eeba-222">가상 트랜잭션에 대한 특별 설치 지침</span><span class="sxs-lookup"><span data-stu-id="4eeba-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="4eeba-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="4eeba-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="4eeba-224">대부분의 가상 트랜잭션은 감시자 노드에서 있는 동안 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="4eeba-225">대부분의 경우 가상 트랜잭션이 감시자 노드 구성 설정에 추가되는 즉시 감시자 노드는 테스트 통과 중에 해당 가상 트랜잭션 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="4eeba-226">그러나 다음 섹션에 설명된 특정 설치 지침이 필요한 일부 가상 트랜잭션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="4eeba-227">데이터 회의 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4eeba-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="4eeba-228">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 다음 단계를 완료하여 네트워크 서비스 계정에 대한 Windows Internet Explorer® 인터넷 브라우저 프록시 설정을 먼저 사용하지 않도록 설정하지 않는 한 데이터 회의 가상 트랜잭션을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="4eeba-229">감시자 노드 컴퓨터에서 **시작,** 모든 프로그램, **보조프로그램,** 명령 프롬프트를 마우스 오른쪽 단추로 클릭한 다음 관리자 **권한으로 실행을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="4eeba-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="4eeba-230">콘솔 창에서 다음 명령을 입력하고 Enter를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="4eeba-231">명령 창에 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="4eeba-232">이 메시지는 네트워크 서비스 계정에 대한 Internet Explorer 프록시 설정을 사용하지 않도록 설정했다는 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="4eeba-233">Exchange 통합 메시징 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4eeba-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="4eeba-234">Exchange UM(통합 메시징) 가상 트랜잭션은 테스트 사용자가 Exchange에 있는 음성메일 계정에 연결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="4eeba-235">테스트 사용자는 음성메일 계정으로 미리 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="4eeba-236">영구 채팅 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4eeba-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="4eeba-237">영구 채팅 가상 트랜잭션을 사용하려면 먼저 채널을 만들고 테스트 사용자에게 해당 트랜잭션을 사용할 수 있는 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="4eeba-238">영구 채팅 가상 트랜잭션을 사용하여 이 채널을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="4eeba-239">이 설치 작업은 엔터프라이즈 내에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="4eeba-240">서버가 아닌 컴퓨터로부터 실행되는 경우 cmdlet을 실행하는 사용자는 RBAC(액세스 제어)에 대한 CsPersistentChatAdministrators 역할의 Role-Based 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="4eeba-241">서버 자체에서 실행하는 경우 cmdlet을 실행하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="4eeba-242">PSTN 피어 투 피어 통화 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4eeba-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="4eeba-243">가상 Test-CsPstnPeerToPeerCall PSTN(전화망)을 통해 통화를 걸고 받을 수 있는 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="4eeba-244">이 가상 트랜잭션을 실행하려면 다음을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="4eeba-245">UC 사용 테스트 사용자 2명(발신자 및 수신자)</span><span class="sxs-lookup"><span data-stu-id="4eeba-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="4eeba-246">각 사용자 계정에 대한 DID(Direct Inward Dialing) 번호</span><span class="sxs-lookup"><span data-stu-id="4eeba-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="4eeba-247">수신자 번호로 걸린 통화가 PSTN 게이트웨이에 연결될 수 있도록 하는 VoIP 정책 및 음성 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="4eeba-248">전화를 거는 번호를 기준으로 수신자 홈 풀로 통화를 다시 라우팅하는 통화 및 미디어를 허용하는 PSTN 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="4eeba-249">통합 연락처 저장소 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4eeba-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="4eeba-250">통합 연락처 저장소 가상 트랜잭션은 비즈니스용 Skype 서버가 Exchange에서 사용자를 대신하여 연락처를 검색할 수 있는 기능을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="4eeba-251">이 가상 트랜잭션을 사용하려면 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="4eeba-252">Lyss-Exchange 서버 인증을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="4eeba-253">테스트 사용자에게 유효한 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="4eeba-254">이러한 조건이 충족된 후 다음 Windows PowerShell cmdlet을 실행하여 테스트 사용자의 연락처 목록을 Exchange로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="4eeba-255">테스트 사용자 연락처 목록이 Exchange로 마이그레이션될 때 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="4eeba-256">마이그레이션 진행률을 모니터링하기 위해 -Setup 플래그 없이 동일한 명령줄을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="4eeba-257">이 명령줄은 마이그레이션이 완료된 후에 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="4eeba-258">XMPP 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4eeba-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="4eeba-259">XMPP(Extensible Messaging and Presence Protocol) IM 가상 트랜잭션을 사용하려면 하나 이상의 페더럴 도메인으로 XMPP 기능을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="4eeba-260">XMPP 가상 트랜잭션을 사용하도록 설정하려면 라우팅 가능한 XMPP 도메인의 사용자 계정으로 XmppTestReceiverMailAddress 매개 변수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="4eeba-261">예:</span><span class="sxs-lookup"><span data-stu-id="4eeba-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="4eeba-262">이 예에서 비즈니스용 Skype 서버 규칙은 비즈니스용 Skype 서버의 메시지를 XMPP litwareinc.com 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="4eeba-263">XMPP 게이트웨이 및 Proxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4eeba-264">자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4eeba-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="4eeba-265">VIS(Video Interop Server) 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4eeba-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="4eeba-266">VIS(Video Interop Server) 가상 트랜잭션을 사용하려면 가상 트랜잭션 지원[ 파일(VISSTSupportPackage.msi)을 다운로드하여 설치해야 ](https://www.microsoft.com/download/details.aspx?id=46921)합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="4eeba-267">이 VISSTSupportPackage.msi msi에 대한 종속성(시스템 요구 사항 아래)이 이미 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="4eeba-268">간단한 VISSTSupportPackage.msi 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="4eeba-269">.msi는 "%ProgramFiles%\VIS Synthetic Transaction Support Package" 경로에 모든 파일을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="4eeba-270">VIS 가상 트랜잭션을 실행하는 방법에 대한 자세한 내용은 [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4eeba-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="4eeba-271">가상 트랜잭션의 실행 빈도 변경</span><span class="sxs-lookup"><span data-stu-id="4eeba-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="4eeba-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="4eeba-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="4eeba-273">기본적으로 가상 트랜잭션은 구성된 사용자와 15분마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="4eeba-274">가상 트랜잭션은 사용자 집합 내에서 시차적으로 실행되어 두 가상 트랜잭션이 서로 충돌하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="4eeba-275">모든 가상 트랜잭션이 완료될 시간을 제공하려면 더 긴 간격이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="4eeba-276">가상 트랜잭션을 더 자주 실행하는 것이 바람직한 경우 특정 사용자 집합과 함께 실행되는 가상 트랜잭션 수를 줄이면 테스트가 필요한 시간 범위에서 일부 버퍼로 완료되어 네트워크 지연이 발생하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="4eeba-277">더 많은 가상 트랜잭션을 실행하는 것이 바람직한 경우 더 많은 사용자 집합을 만들어 추가 가상 트랜잭션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="4eeba-278">가상 트랜잭션이 실행되는 빈도를 변경하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="4eeba-279">System Center Operations Manager를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="4eeba-280">작성 섹션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-280">Click Authoring section.</span></span> <span data-ttu-id="4eeba-281">규칙 섹션(제작 아래)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="4eeba-282">규칙 섹션에서 이름이 "Main Synthetic Transaction Runner Performance Collection Rule"인 규칙을 찾아보세요.</span><span class="sxs-lookup"><span data-stu-id="4eeba-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="4eeba-283">규칙을 마우스 오른쪽 단추로 클릭하고 다시 다시 표시를 선택하고 규칙 다시 고지를 선택한 다음 "클래스의 모든 개체: 풀 감시자"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="4eeba-284">속성 오버라이드 창에서 매개 변수 이름 "Frequency"를 선택하고 값 1회를 원하는 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="4eeba-285">같은 창에서 이 오버라이드를 적용해야 하는 관리 팩을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="4eeba-286">가상 트랜잭션에 고급 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="4eeba-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="4eeba-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="4eeba-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="4eeba-288">가상 트랜잭션은 시스템 문제를 식별하는 데 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="4eeba-289">예를 들어 Test-CsRegistration cmdlet은 사용자에게 비즈니스용 Skype 서버에 등록하는 데 문제가 있다는 사실을 관리자에게 경고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="4eeba-290">그러나 오류의 실제 원인을 확인하려면 추가 세부 정보가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="4eeba-291">이러한 이유로 가상 트랜잭션은 풍부한 로깅을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="4eeba-292">다양한 로깅을 통해 가상 트랜잭션이 진행하는 각 활동에 대해 다음 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="4eeba-293">활동이 시작된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="4eeba-294">활동이 완료된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="4eeba-295">수행된 작업(예: 전화 회의 만들기, 참가 또는 나가기, 비즈니스용 Skype 서버에 로그인, 인스턴트 메시지 보내기)</span><span class="sxs-lookup"><span data-stu-id="4eeba-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="4eeba-296">활동이 시작될 때 생성되는 정보, 자세한 정보, 경고 또는 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="4eeba-297">SIP 등록 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="4eeba-298">예외 레코드 또는 활동이 실행될 때 생성된 진단 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="4eeba-299">활동 실행의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="4eeba-300">이 정보는 가상 트랜잭션이 실행될 때마다 자동으로 생성되지만 로그 파일에 자동으로 표시되거나 저장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="4eeba-301">가상 트랜잭션을 수동으로 실행하는 경우 OutLoggerVariable 매개 변수를 사용하여 정보가 Windows PowerShell 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="4eeba-302">두 가지 방법 중 하나를 사용하여 XML 또는 HTML 형식으로 서식 있는 로그에 오류 메시지를 저장 및/또는 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="4eeba-303">문제 해결 정보를 검색하기 위해 OutLoggerVariable 매개 변수를 지정하고 그 다음에 선택한 변수 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="4eeba-304">변수 이름 앞에 $ 문자를 붙이지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4eeba-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="4eeba-305">RegistrationTest와 같은 변수 이름을 $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="4eeba-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="4eeba-306">이 명령을 실행하면 출력은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="4eeba-307">대상 Fqdn : atl-cs-001.litwareinc.com 결과 : 오류 대기 시간 : 00:00:00 오류 메시지: 이 컴퓨터의 인증서가 할당되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="4eeba-308">진단 : 여기에 표시된 오류 메시지보다 이 오류에 대한 훨씬 자세한 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="4eeba-309">이 정보에 HTML 형식으로 액세스하려면 이 명령과 유사한 명령을 사용하여 RegistrationTest 변수에 저장된 정보를 HTML 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="4eeba-310">또는 ToXML() 메서드를 사용하여 데이터를 XML 파일에 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="4eeba-311">이러한 파일은 Windows Internet Explorer, Microsoft Visual Studio 또는 HTML/XML 파일을 열 수 있는 다른 응용 프로그램을 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="4eeba-312">System Center Operations Manager 내부에서 실행되는 가상 트랜잭션은 오류에 대해 이러한 로그 파일을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="4eeba-313">이러한 로그는 비즈니스용 Skype 서버 PowerShell이 가상 트랜잭션을 로드하고 실행할 수 있게 되기 전에 실행이 실패할 경우 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4eeba-314">기본적으로 비즈니스용 Skype 서버는 공유되지 않는 폴더에 로그 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="4eeba-315">이러한 로그에 쉽게 액세스할 수 있도록 이 폴더를 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeba-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="4eeba-316">예: \\ atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="4eeba-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>