---
title: 감시자 노드 테스트 사용자 및 설정 구성
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 비즈니스용 Skype 서버 가상 트랜잭션에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.'
ms.openlocfilehash: f13680d16a248be339ee7cd4a085d7d0894146dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033677"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="e1dd2-103">감시자 노드 테스트 사용자 및 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e1dd2-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="e1dd2-104">**요약:** 비즈니스용 Skype 서버 가상 트랜잭션에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="e1dd2-105">감시자 노드로 작동할 컴퓨터를 구성한 후에는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="e1dd2-106">다음 감시자 노드에 사용할 [테스트 사용자 계정을 구성](test-users-and-settings-2019.md#testuser) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="e1dd2-107">협상 인증 방법을 사용 하는 경우에는 **get-cstestusercredential** cmdlet을 사용 하 여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="e1dd2-108">감시자 노드 구성 설정을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="e1dd2-109">테스트 사용자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="e1dd2-109">Configure Test User Accounts</span></span>
<span data-ttu-id="e1dd2-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dd2-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="e1dd2-111">테스트 계정은 실제 사용자를 나타낼 필요가 없지만 유효한 Active Directory 계정 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="e1dd2-112">또한 비즈니스용 Skype 서버에서 이러한 계정을 사용 하도록 설정 해야 하 고, 유효한 SIP 주소가 있어야 하며, Enterprise Voice를 사용 하도록 설정 해야 합니다 (테스트-CsPstnPeerToPeerCall 가상 트랜잭션을 사용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="e1dd2-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="e1dd2-113">가 중 서버 인증 방법을 사용 하는 경우에는 이러한 계정이 존재 하는지 확인 하 고 별도로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="e1dd2-114">테스트할 각 풀에 대해 테스트 사용자를 세 명 이상 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="e1dd2-115">협상 인증 방법을 사용 하는 경우에는 Get-cstestusercredential cmdlet 및 비즈니스용 Skype 서버 관리 셸을 사용 하 여 이러한 테스트 계정이 가상 트랜잭션과 함께 작동 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="e1dd2-116">다음과 같은 명령을 실행 하 여이 작업을 수행 합니다 (이러한 명령은 세 개의 Active Directory 사용자 계정이 만들어져 있고 비즈니스용 Skype 서버에 대해 이러한 계정을 사용 하도록 설정 했다고 가정 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="e1dd2-117">SIP 주소 뿐만 아니라 사용자 이름 및 암호를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="e1dd2-118">암호를 포함 하지 않으면 Get-cstestusercredential cmdlet은 해당 정보를 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="e1dd2-119">사용자 이름은 앞의 코드 블록에 표시 된 domain 이름 \ 사용자 name 형식을 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="e1dd2-120">테스트 사용자 자격 증명이 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="e1dd2-121">각 사용자에 대해 다음과 같은 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="e1dd2-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="e1dd2-122">**UserName**</span></span>|<span data-ttu-id="e1dd2-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="e1dd2-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1dd2-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="e1dd2-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="e1dd2-125">System.object.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="e1dd2-126">기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="e1dd2-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="e1dd2-127">테스트 사용자를 만든 후에는 다음과 같은 명령을 사용 하 여 감시자 노드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="e1dd2-128">이 명령은 기본 설정을 사용 하 고 기본 트랜잭션 집합을 실행 하는 새 감시자 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="e1dd2-129">또한 새 감시자 노드는 test users watcher1@litwareinc.com, watcher2@litwareinc.com 및 watcher3@litwareinc.com를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="e1dd2-130">감시자 노드가로 서버 인증을 사용 하는 경우 세 가지 테스트 계정은 Active Directory 및 비즈니스용 Skype 서버에 대해 사용 가능한 모든 유효한 사용자 계정이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="e1dd2-131">감시자 노드가 Negotiate authentication 메서드를 사용 하는 경우에는 Get-cstestusercredential cmdlet을 사용 하 여이 사용자 계정도 감시자 노드에 대해 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="e1dd2-132">풀을 직접 대상으로 지정 하는 대신 대상 풀의 자동 검색이 올바르게 구성 되었는지 확인 하려면 대신 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="e1dd2-133">확장 테스트 구성</span><span class="sxs-lookup"><span data-stu-id="e1dd2-133">Configuring Extended Tests</span></span>

<span data-ttu-id="e1dd2-134">공중 전화망과의 연결을 확인 하는 PSTN 테스트를 사용 하도록 설정 하려는 경우에는 감시자 노드를 설정할 때 추가 구성을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="e1dd2-135">먼저 비즈니스용 Skype 서버 관리 셸에서와 비슷한 명령을 실행 하 여 테스트 사용자를 PSTN 테스트 유형에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="e1dd2-136">이 명령의 결과는 변수에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="e1dd2-137">이 예제에서 변수 이름은 $pstnTest입니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="e1dd2-138">다음으로, **get-cswatchernodeconfiguration** cmdlet을 사용 하 여 $pstnTest 변수에 저장 된 테스트 유형을 비즈니스용 Skype 서버 풀에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="e1dd2-139">예를 들어 다음 명령은 atl-cs-001.litwareinc.com 풀에 대 한 새 감시자 노드 구성을 만들고 이전에 만든 3 개의 테스트 사용자를 추가한 다음 PSTN 테스트 유형을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="e1dd2-140">감시자 노드 컴퓨터에 비즈니스용 Skype 서버 코어 파일과 RTCLocal 데이터베이스를 설치 하지 않은 경우에는 위의 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="e1dd2-141">여러 음성 정책을 테스트 하려면 **new-csextendedtest** cmdlet을 사용 하 여 각 정책에 대 한 확장 테스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="e1dd2-142">제공 된 사용자는 원하는 음성 정책을 사용 하 여 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="e1dd2-143">확장 된 테스트는 다음과 같은 쉼표 구분 기호를 사용 하 여 **get-cswatchernodeconfiguration** cmdlet으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="e1dd2-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="e1dd2-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="e1dd2-145">**Get-cswatchernodeconfiguration** Cmdlet은 테스트 매개 변수를 사용 하지 않고 호출 했기 때문에 새 감시자 노드에 기본 가상 트랜잭션과 지정 된 확장 가상 트랜잭션만 사용할 수 있도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="e1dd2-146">따라서 감시자 노드는 다음과 같은 구성 요소를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="e1dd2-147">등록</span><span class="sxs-lookup"><span data-stu-id="e1dd2-147">Registration</span></span>
    
- <span data-ttu-id="e1dd2-148">메시징을</span><span class="sxs-lookup"><span data-stu-id="e1dd2-148">IM</span></span>
    
- <span data-ttu-id="e1dd2-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="e1dd2-149">GroupIM</span></span>
    
- <span data-ttu-id="e1dd2-150">P2PAV (피어 투 피어 오디오/비디오 세션)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="e1dd2-151">AvConference (오디오/회의)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="e1dd2-152">이들의</span><span class="sxs-lookup"><span data-stu-id="e1dd2-152">Presence</span></span>
    
- <span data-ttu-id="e1dd2-153">ABS (주소록 서비스)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="e1dd2-154">ABWQ (주소록 웹 서비스)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="e1dd2-155">다음 구성 요소는 기본적으로 테스트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="e1dd2-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="e1dd2-156">ASConference</span></span>
    
- <span data-ttu-id="e1dd2-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="e1dd2-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="e1dd2-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="e1dd2-158">DataConference</span></span>
    
- <span data-ttu-id="e1dd2-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="e1dd2-159">DialinConferencing</span></span>
    
- <span data-ttu-id="e1dd2-160">ExumConnectivity (Exchange 통합 메시징)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="e1dd2-161">JoinLauncher 관리자</span><span class="sxs-lookup"><span data-stu-id="e1dd2-161">JoinLauncher</span></span>
    
- <span data-ttu-id="e1dd2-162">MCXP2PIM (레거시 모바일 장치 인스턴트 메시징)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="e1dd2-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="e1dd2-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="e1dd2-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="e1dd2-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="e1dd2-165">PSTN (PSTN 게이트웨이 호출, 확장 된 테스트로 지정)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="e1dd2-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="e1dd2-166">UcwaConference</span></span>
    
- <span data-ttu-id="e1dd2-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="e1dd2-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="e1dd2-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="e1dd2-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="e1dd2-169">가상 트랜잭션 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="e1dd2-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="e1dd2-170">감시자 노드를 구성한 후에는 Get-cswatchernodeconfiguration cmdlet을 사용 하 여 노드에서 가상 트랜잭션을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="e1dd2-171">예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가 하려면 Add 메서드와 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="e1dd2-172">테스트 이름을 쉼표로 구분 하 여 여러 테스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="e1dd2-173">예:</span><span class="sxs-lookup"><span data-stu-id="e1dd2-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="e1dd2-174">이러한 테스트 (예: DataConference) 중 하나 이상이 이미 감시자 노드에 대해 사용 하도록 설정 되어 있으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="e1dd2-175">이 경우 다음과 같은 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="e1dd2-176">Get-cswatchernodeconfiguration: ' urn: schema: DataConference ' 키 또는 고유 id 제약 조건에 중복 된 키 시퀀스 ' Watchernode.msi executable '이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="e1dd2-177">이 오류가 발생 하면 변경 내용이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="e1dd2-178">이 명령은 중복 된 테스트를 제거한 후 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="e1dd2-179">감시자 노드에서 가상 트랜잭션을 제거 하려면 Remove 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="e1dd2-180">예를 들어이 명령은 감시자 노드에서 ABWQ 테스트를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="e1dd2-181">Replace 메서드를 사용 하 여 현재 사용 가능한 모든 테스트를 하나 이상의 새 테스트로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="e1dd2-182">예를 들어 감시자 노드가 IM 테스트만 실행 하도록 하려면 다음 명령을 사용 하 여 해당 노드를 구성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="e1dd2-183">이 명령을 실행 하면 IM을 제외한 지정 된 감시자 노드의 모든 가상 트랜잭션이 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="e1dd2-184">감시자 노드 구성 보기 및 테스트</span><span class="sxs-lookup"><span data-stu-id="e1dd2-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="e1dd2-185">감시자 노드에 할당 된 테스트를 보려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="e1dd2-186">이 명령은 노드에 할당 된 가상 트랜잭션에 따라 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="e1dd2-187">등록 메신저 GroupIM P2PAV AvConference 현재 상태 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="e1dd2-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="e1dd2-188">사전순으로 가상 트랜잭션을 보려면 다음 명령을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="e1dd2-189">감시자 노드가 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="e1dd2-190">그러면 다음과 같은 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="e1dd2-191">Id: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="e1dd2-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="e1dd2-192">ExtendedTests: {TestUsers = IList<System.string>; 이름 = PSTN 테스트; Te ...}</span><span class="sxs-lookup"><span data-stu-id="e1dd2-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="e1dd2-193">TargetFqdn: atl-cs-001.litwareinc.com PortNumber: 5061To 노드가 올바르게 구성 되었는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="e1dd2-194">이 명령은 배포의 각 감시자 노드를 테스트 하 고 다음 작업이 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="e1dd2-195">필요한 등록자 역할이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="e1dd2-196">필요한 레지스트리 키가 만들어집니다 (Get-cswatchernodeconfiguration cmdlet을 실행할 때 완료 됨).</span><span class="sxs-lookup"><span data-stu-id="e1dd2-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="e1dd2-197">서버에서 비즈니스용 Skype 서버의 올바른 버전을 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="e1dd2-198">포트가 올바르게 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="e1dd2-199">할당 된 테스트 사용자에 게 필요한 자격 증명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="e1dd2-200">감시자 노드 관리</span><span class="sxs-lookup"><span data-stu-id="e1dd2-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="e1dd2-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dd2-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="e1dd2-202">감시자 노드에서 실행 되는 가상 트랜잭션을 수정 하는 것 외에도 **get-cswatchernodeconfiguration** cmdlet을 사용 하 여 감시자 노드를 설정 및 해제 하 고, 테스트를 실행할 때 내부 웹 url 또는 외부 웹 url 중 하나를 사용 하도록 감시자 노드를 구성 하는 두 가지 중요 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="e1dd2-203">기본적으로 감시자 노드는 설정된 모든 가상 트랜잭션을 주기적으로 실행하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="e1dd2-204">그러나 때때로 이러한 트랜잭션을 일시 중단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="e1dd2-205">예를 들어 감시자 노드가 일시적으로 네트워크에서 연결이 해제된 경우에는 가상 트랜잭션을 실행할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="e1dd2-206">네트워크 연결이 없으면 이러한 트랜잭션이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="e1dd2-207">감시자 노드를 일시적으로 사용 하지 않도록 설정 하려면 비즈니스용 Skype 서버 관리 셸에서와 비슷한 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="e1dd2-208">이 명령은 감시자 노드 atl 감시자 001.litwareinc.com에서 가상 트랜잭션의 실행을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="e1dd2-209">가상 트랜잭션 실행을 다시 시작하려면 Enabled 속성을 다시 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="e1dd2-210">Enabled 속성을 사용하면 감시자 노드를 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="e1dd2-211">감시자 노드를 영구적으로 삭제하려면 **Remove-CsWatcherNodeConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="e1dd2-212">이 명령은 지정 된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거 하 여 해당 컴퓨터에서 가상 트랜잭션을 자동으로 실행 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="e1dd2-213">그러나이 명령은 System Center 에이전트 파일 또는 비즈니스용 Skype 서버 시스템 파일은 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="e1dd2-214">기본적으로 감시자 노드는 테스트를 수행할 때 조직의 외부 웹 Url을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="e1dd2-215">그러나 조직의 내부 웹 Url을 사용 하도록 감시자 노드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="e1dd2-216">이렇게 하면 관리자가 경계 네트워크 내부에 있는 사용자에 대한 URL 액세스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="e1dd2-217">외부 Url 대신 내부 Url을 사용 하도록 감시자 노드를 구성 하려면 UseInternalWebURls 속성을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="e1dd2-218">이 속성을 False ($False)로 다시 설정 하면 감시자가 다음에 외부 Url을 다시 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="e1dd2-219">가상 트랜잭션에 대한 특별 설치 지침</span><span class="sxs-lookup"><span data-stu-id="e1dd2-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="e1dd2-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dd2-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="e1dd2-221">대부분의 가상 트랜잭션은 감시자 노드에서 그대로 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="e1dd2-222">대부분의 경우에는 가상 트랜잭션이 감시자 노드 구성 설정에 추가 되는 즉시, 감시자 노드는 해당 테스트 가공 패스 중에 해당 가상 트랜잭션을 사용 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="e1dd2-223">그러나 다음 섹션에서 설명 하는 것 처럼 특별 한 설치 지침이 필요한 몇 가지 가상 트랜잭션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="e1dd2-224">데이터 회의 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e1dd2-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="e1dd2-225">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 먼저 Windows Internet Explorer를 사용 하지 않도록 설정 하 고 네트워크에 대 한 Internet browser 프록시 설정® 않으면 데이터 회의 가상 트랜잭션을 실행할 수 없게 됩니다. 서비스 계정 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="e1dd2-226">감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **보조 프로그램**을 차례로 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="e1dd2-227">콘솔 창에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="e1dd2-228">명령 창에 다음과 같은 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="e1dd2-229">BITSAdmin은 더 이상 사용 되지 않으며 향후 버전의 Windows에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="e1dd2-230">Bits 서비스용 관리 도구가 이제 BITS PowerShell cmdlet에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="e1dd2-231">계정 NetworkService에 대 한 인터넷 프록시 설정이 NO_PROXY로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="e1dd2-232">(connection = default)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-232">(connection = default)</span></span>
  
<span data-ttu-id="e1dd2-233">이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="e1dd2-234">Exchange 통합 메시징 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e1dd2-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="e1dd2-235">Exchange UM (통합 메시징) 가상 트랜잭션은 테스트 사용자가 Exchange에서 홈에 있는 음성 메일 계정에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="e1dd2-236">테스트 사용자는 음성 메일 계정을 사용 하 여 미리 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="e1dd2-237">영구 채팅 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e1dd2-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="e1dd2-238">영구 채팅 가상 트랜잭션을 사용 하려면 먼저 채널을 만들고 사용자에 게이를 사용 하기 위한 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="e1dd2-239">영구 채팅 가상 트랜잭션을 사용 하 여이 채널을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="e1dd2-240">이 설치 작업을 실행 해야 하는 경우 엔터프라이즈 내에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="e1dd2-241">서버 이외의 시스템에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RBAC (역할 기반 액세스 제어)에 대 한 CsPersistentChatAdministrators 역할의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="e1dd2-242">서버 자체에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="e1dd2-243">PSTN 피어 투 피어 통화 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e1dd2-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="e1dd2-244">테스트-CsPstnPeerToPeerCall 가상 트랜잭션은 공중 전화망 (PSTN)을 통해 전화를 걸거나 받을 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="e1dd2-245">이 가상 트랜잭션을 실행 하려면 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="e1dd2-246">UC를 사용 하는 두 테스트 사용자 (발신자 및 수신자)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="e1dd2-247">각 사용자 계정에 대한 DID(Direct Inward Dialing) 번호</span><span class="sxs-lookup"><span data-stu-id="e1dd2-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="e1dd2-248">전화 번호에 대 한 통화가 PSTN 게이트웨이에 도달할 수 있도록 하는 VoIP 정책 및 음성 경로</span><span class="sxs-lookup"><span data-stu-id="e1dd2-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="e1dd2-249">전화를 건 번호에 따라 통화를 수신자의 홈 풀로 다시 라우팅하는 통화 및 미디어를 허용 하는 PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="e1dd2-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="e1dd2-250">통합 연락처 저장소 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e1dd2-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="e1dd2-251">통합 연락처 저장소 가상 트랜잭션은 Exchange에서 사용자를 대신 하 여 연락처를 검색 하는 비즈니스용 Skype 서버의 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="e1dd2-252">이 가상 트랜잭션을 사용하려면 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="e1dd2-253">Lyss-Exchange server to server authentication을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="e1dd2-254">테스트 사용자에 게 유효한 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="e1dd2-255">이러한 조건이 충족 되 면 다음 Windows PowerShell cmdlet을 실행 하 여 테스트 사용자의 연락처 목록을 Exchange로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="e1dd2-256">테스트 사용자 연락처 목록을 Exchange로 마이그레이션하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="e1dd2-257">마이그레이션 진행 상황을 모니터링 하기 위해-Setup 플래그 없이도 동일한 명령줄을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="e1dd2-258">마이그레이션이 완료 된 후이 명령줄은 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="e1dd2-259">XMPP 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e1dd2-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="e1dd2-260">XMPP (Extensible Messaging and 현재 상태 프로토콜) IM 가상 트랜잭션을 사용 하려면 하나 이상의 페더레이션 도메인을 사용 하 여 XMPP 기능을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="e1dd2-261">XMPP 가상 트랜잭션을 사용 하도록 설정 하려면 라우팅 가능한 XMPP 도메인에서 사용자 계정에 XmppTestReceiverMailAddress 매개 변수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="e1dd2-262">예:</span><span class="sxs-lookup"><span data-stu-id="e1dd2-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="e1dd2-263">이 예에서는 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅하기 위해 비즈니스용 Skype 서버 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="e1dd2-264">XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e1dd2-265">자세한 내용은 [XMPP 페더레이션 마이그레이션을](../migration/migrating-xmpp-federation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="e1dd2-266">VIS (동영상 Interop 서버) 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e1dd2-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="e1dd2-267">VIS (동영상 Interop 서버) 가상 트랜잭션을 사용 하려면 가상 트랜잭션 지원 파일 ([VISSTSupportPackage](https://www.microsoft.com/download/details.aspx?id=46921))을 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="e1dd2-268">VISSTSupportPackage을 설치 하려면 msi에 대 한 종속성 (시스템 요구 사항에 따라)이 이미 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="e1dd2-269">VISSTSupportPackage를 실행 하 여 단순 설치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="e1dd2-270">.Msi는 "%ProgramFiles%\VIS 가상 트랜잭션 지원 패키지" 경로의 모든 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="e1dd2-271">VIS 가상 트랜잭션을 실행 하는 방법에 대 한 자세한 내용은 [CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet에 대 한 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="e1dd2-272">가상 트랜잭션에 대 한 실행 빈도 변경</span><span class="sxs-lookup"><span data-stu-id="e1dd2-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="e1dd2-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dd2-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="e1dd2-274">기본적으로 구성 된 사용자가 15 분 마다 가상 트랜잭션이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="e1dd2-275">가상 트랜잭션은 사용자 집합 내에서 순차적으로 실행 되어 두 가상 트랜잭션이 서로 충돌 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="e1dd2-276">모든 가상 트랜잭션이 완료 될 때 까지의 시간을 제공 하기 위해 더 긴 간격이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="e1dd2-277">가상 트랜잭션을 더 자주 실행 하는 것이 바람직한 경우에는 지정 된 사용자 집합을 사용 하 여 실행 되는 가상 트랜잭션 수를 줄여야 하 여 테스트를 가끔씩 발생 하는 네트워크 지연에 대 한 일부 버퍼와 함께 원하는 시간 범위에서 완료할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="e1dd2-278">더 많은 가상 트랜잭션을 실행 하는 것이 바람직한 경우 추가 가상 트랜잭션을 실행할 사용자 집합을 더 많이 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="e1dd2-279">가상 트랜잭션을 실행 하는 빈도를 변경 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="e1dd2-280">System Center Operations Manager를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="e1dd2-281">제작 섹션을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-281">Click Authoring section.</span></span> <span data-ttu-id="e1dd2-282">규칙 섹션 (제작 중)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="e1dd2-283">규칙 섹션에서 이름이 "Main 종합 Transaction 러너 성능 수집 규칙" 인 규칙을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="e1dd2-284">규칙을 마우스 오른쪽 단추로 클릭 하 고 재정의를 선택한 다음 규칙 재정의를 선택 하 고, "클래스의 모든 개체: 풀 감시자"를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="e1dd2-285">속성 재정의 창에서 매개 변수 이름 "Frequency"를 선택 하 고 재정의 값을 원하는 항목으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="e1dd2-286">같은 창에서이 재정의를 적용 해야 하는 관리 팩을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="e1dd2-287">가상 트랜잭션에 고급 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="e1dd2-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="e1dd2-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dd2-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="e1dd2-289">가상 트랜잭션은 시스템에서 발생 하는 문제를 파악 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="e1dd2-290">예를 들어, 테스트-CsRegistration cmdlet은 사용자가 비즈니스용 Skype 서버에 등록 하는 데 어려움을 겪고 있음을 관리자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="e1dd2-291">그러나 실제 실패 원인을 확인 하려면 추가 정보가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="e1dd2-292">따라서 가상 트랜잭션은 다양 한 로깅을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="e1dd2-293">가상 트랜잭션이 undertakes 하는 각 활동에 대해 풍부한 로깅을 사용 하면 다음과 같은 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="e1dd2-294">활동이 시작 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="e1dd2-295">활동을 완료 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="e1dd2-296">수행 된 작업 (예: 회의 만들기, 참가 또는 탈퇴, 비즈니스용 Skype 서버에 로그인, 인스턴트 메시지 보내기)</span><span class="sxs-lookup"><span data-stu-id="e1dd2-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="e1dd2-297">활동 실행 시 생성된 정보, 자세한 정보, 경고 또는 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="e1dd2-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="e1dd2-298">SIP 등록 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="e1dd2-299">활동을 실행할 때 생성 되는 예외 레코드 또는 진단 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="e1dd2-300">활동을 실행 했을 때의 네트워크 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="e1dd2-301">이 정보는 가상 트랜잭션을 실행할 때마다 자동으로 생성 되지만 로그 파일에 자동으로 표시 되거나 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="e1dd2-302">가상 트랜잭션을 수동으로 실행 하는 경우에는 OutLoggerVariable 매개 변수를 사용 하 여 정보가 저장 될 Windows PowerShell 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="e1dd2-303">여기서는 두 가지 방법 중 하나를 사용 하 여 XML 또는 HTML 형식의 리치 로그에서 오류 메시지를 저장 및/또는 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="e1dd2-304">문제 해결 정보를 검색 하려면 OutLoggerVariable 매개 변수를 지정한 다음 선택한 변수 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="e1dd2-305">: 변수 이름 앞에 $ 문자를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="e1dd2-306">$RegistrationTest 아닌 RegistrationTest와 같은 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="e1dd2-307">이 명령을 실행 하면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="e1dd2-308">대상 Fqdn: atl-cs-001.litwareinc.com Result: 실패 한 대기 시간: 00:00:00 오류 메시지:이 컴퓨터에는 할당 된 인증서가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="e1dd2-309">진단:이 오류에 대 한 보다 자세한 정보는 여기에 표시 된 것 처럼 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="e1dd2-310">HTML 형식으로이 정보에 액세스 하려면 다음과 비슷한 명령을 사용 하 여 변수 RegistrationTest에 저장 된 정보를 HTML 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="e1dd2-311">또는 ToXML() 메서드를 사용하여 데이터를 XML 파일에 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="e1dd2-312">Windows Internet Explorer, Microsoft Visual Studio 또는 HTML/XML 파일을 열 수 있는 기타 응용 프로그램을 사용 하 여 이러한 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="e1dd2-313">System Center Operations Manager 내부에서 실행 되는 가상 트랜잭션은 오류에 대 한 이러한 로그 파일을 자동으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="e1dd2-314">비즈니스용 Skype 서버 PowerShell에서 가상 트랜잭션을 로드 하 고 실행할 수 있으려면 실행이 실패 하는 경우이 로그가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e1dd2-315">기본적으로 비즈니스용 Skype 서버는 공유 되지 않는 폴더에 로그 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="e1dd2-316">이러한 로그에 쉽게 액세스할 수 있도록 하려면이 폴더를 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="e1dd2-317">예: \\atl-litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="e1dd2-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
