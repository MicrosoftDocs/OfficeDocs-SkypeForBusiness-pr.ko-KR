---
title: 감시자 노드 테스트 사용자 및 구성 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="70849-102">Lync Server 2013에서 감시자 노드 테스트 사용자 및 구성 설정 구성</span><span class="sxs-lookup"><span data-stu-id="70849-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70849-103">_**마지막으로 수정한 주제:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="70849-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="70849-104">감시자 노드 역할을 하는 컴퓨터를 구성한 후에는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="70849-105">이러한 감시자 노드에서 사용할 테스트 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70849-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="70849-106">협상 인증 방법을 사용 하는 경우 [CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet을 사용 하 여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="70849-107">감시자 노드 구성 설정을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="70849-108">이 섹션에서는 다음에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-108">This section covers:</span></span>

  - <span data-ttu-id="70849-109">테스트 사용자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="70849-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="70849-110">기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="70849-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="70849-111">확장 된 테스트 구성</span><span class="sxs-lookup"><span data-stu-id="70849-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="70849-112">가상 트랜잭션 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="70849-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="70849-113">감시자 노드 구성 보기 및 테스트</span><span class="sxs-lookup"><span data-stu-id="70849-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="70849-114">테스트 사용자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="70849-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="70849-115">테스트 사용자는 실제 사용자를 나타낼 필요는 없지만 올바른 Active Directory 도메인 서비스 계정 이어야 합니다. 또한이 계정에는 Lync Server 2013을 사용할 수 있어야 하며, 유효한 SIP 주소가 있어야 하며, 테스트-CsPstnPeerToPeerCall 가상 트랜잭션을 사용 하려면 Enterprise Voice를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="70849-116">로 서버 인증 방법을 사용 하는 경우에는 이러한 계정이 존재 하 고 여기에 지정 된 대로 구성 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="70849-117">테스트 하려는 각 풀에 대해 최소 세 개의 테스트 사용자를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="70849-118">협상 인증 방법을 사용 하는 경우 **CsTestUserCredential** Cmdlet 및 Lync Server Management Shell을 사용 하 여 이러한 테스트 계정이 가상 트랜잭션과 함께 작동 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="70849-119">다음과 같은 명령을 실행 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="70849-120">이러한 명령은 세 개의 Active Directory 사용자 계정이 이미 생성 되었고 해당 계정이 Lync Server 2013에 대해 사용 하도록 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="70849-121">SIP 주소는 물론 사용자 이름 및 암호만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="70849-122">암호 집합을 포함 하지 않으면-CsTestUserCredential에서 해당 정보를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70849-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="70849-123">사용자 이름은 위에 표시 된 도메인 이름\\사용자 이름 형식을 사용 하 여 지정 하거나 사용자 name@domain 이름 형식을 사용 하 여 지정할 수 있습니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="70849-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="70849-124">테스트 사용자 자격 증명이 만들어졌는지 확인 하려면 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="70849-125">각 사용자에 대해 다음과 유사한 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70849-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="70849-126">기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="70849-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="70849-127">테스트 사용자를 만든 후 다음과 같은 명령을 사용 하 여 감시자 노드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="70849-128">이 명령은 기본 설정을 사용 하 고 기본적인 가상 트랜잭션 집합을 실행 하는 새 감시자 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70849-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="70849-129">또한 새 감시자 노드는 테스트 사용자 watcher1@litwareinc.com, watcher2@litwareinc.com 및 watcher3@litwareinc.com를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="70849-130">감시자 노드가 개인 서버 인증을 사용 하는 경우, Active Directory 및 Lync Server에 대해 사용할 수 있는 유효한 사용자 계정이 세 가지 테스트 계정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="70849-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="70849-131">감시자 노드가 협상 인증 방법을 사용 하는 경우 **Set-CsTestUserCredential** cmdlet을 사용 하 여 감시자 노드에 대해 이러한 사용자 계정도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="70849-132">확장 된 테스트 구성</span><span class="sxs-lookup"><span data-stu-id="70849-132">Configuring Extended Tests</span></span>

<span data-ttu-id="70849-133">공개 전환 전화 네트워크 연결을 확인 하는 PSTN 테스트 (공공 전환 전화 네트워크)를 사용 하도록 설정 하려는 경우 감시자 노드를 설정할 때 몇 가지 추가 구성을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="70849-134">먼저 테스트 사용자를 PSTN 테스트 형식과 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="70849-135">이렇게 하려면 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="70849-136">이 명령의 결과는 변수에 저장 되어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="70849-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="70849-137">이 예제에서는이 변수를 $pstnTest 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="70849-138">이 시점에서 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 변수 $pstnTest에 저장 된 테스트 유형을 Lync Server 2013 풀에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="70849-139">예를 들어 다음 명령을 실행 하면 풀 atl-cs-001.litwareinc.com에 대 한 새 감시자 노드 구성이 만들어지고 이전에 만든 세 개의 테스트 사용자가 추가 되며 PSTN 테스트 형식도 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70849-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="70849-140">Lync Server core 파일과 감시자 노드 컴퓨터에 RTCLocal 데이터베이스를 설치 하지 않은 경우 앞의 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="70849-141">여러 음성 정책을 테스트 하려면 **새 CsExtendedTest** cmdlet을 사용 하 여 각 정책에 대 한 확장 테스트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="70849-142">이 테스트에 할당 된 사용자는 원하는 음성 정책으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="70849-143">그런 다음 확장 테스트는 다음과 유사한 명령을 사용 하 여 **CsWatcherNodeConfiguration** cmdlet에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70849-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="70849-144">테스트 매개 변수를 사용 하지 않고 New-CsWatcherNodeConfiguration가 호출 되는 경우,이는 기본 가상 트랜잭션 (및 지정 된 확장 된 가상 트랜잭션)만 새 감시자 노드에 대해 설정 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="70849-145">이것은 감시자 노드가 다음 구성 요소를 테스트 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="70849-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="70849-146">등록</span><span class="sxs-lookup"><span data-stu-id="70849-146">Registration</span></span>

  - <span data-ttu-id="70849-147">메신저</span><span class="sxs-lookup"><span data-stu-id="70849-147">IM</span></span>

  - <span data-ttu-id="70849-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="70849-148">GroupIM</span></span>

  - <span data-ttu-id="70849-149">P2PAV (피어 투 피어 오디오/비디오 세션)</span><span class="sxs-lookup"><span data-stu-id="70849-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="70849-150">AvConference (오디오/회의)</span><span class="sxs-lookup"><span data-stu-id="70849-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="70849-151">현재 상태</span><span class="sxs-lookup"><span data-stu-id="70849-151">Presence</span></span>

  - <span data-ttu-id="70849-152">ABS (주소록 서비스)</span><span class="sxs-lookup"><span data-stu-id="70849-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="70849-153">ABWQ (주소록 웹 서비스)</span><span class="sxs-lookup"><span data-stu-id="70849-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="70849-154">PSTN (PSTN 게이트웨이 통화, 확장 테스트로 지정 됨)</span><span class="sxs-lookup"><span data-stu-id="70849-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="70849-155">기본적으로 PSTN은 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="70849-156">이 경우 명령은 ExtendedTests 매개 변수를 사용 하 여 PSTN을 사용할 수 있기 때문에 테스트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="70849-157">이는 또한 다음 구성 요소가 기본적으로 테스트 되지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="70849-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="70849-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="70849-159">MCXP2PIM (모바일 장치 인스턴트 메시지)</span><span class="sxs-lookup"><span data-stu-id="70849-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="70849-160">ExumConnectivity (Exchange 통합 메시징)</span><span class="sxs-lookup"><span data-stu-id="70849-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="70849-161">JoinLauncher 관리자</span><span class="sxs-lookup"><span data-stu-id="70849-161">JoinLauncher</span></span>

  - <span data-ttu-id="70849-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="70849-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="70849-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="70849-163">DataConference</span></span>

  - <span data-ttu-id="70849-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="70849-164">XmppIM</span></span>

  - <span data-ttu-id="70849-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="70849-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="70849-166">가상 트랜잭션 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="70849-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="70849-167">감시자 노드가 구성 되 면 **Set-CsWatcherNodeConfiguration** cmdlet을 사용 하 여 노드에서 가상 트랜잭션을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="70849-168">예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가 하려면 Add 메서드와 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="70849-169">여러 테스트는 쉼표를 사용 하 여 테스트 이름을 구분 하 여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="70849-170">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="70849-171">이러한 테스트 중 하나 이상 (예: DataConference)이 감시자 노드에서 이미 사용 하도록 설정 된 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="70849-172">이 경우 다음과 같은 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70849-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="70849-173">이 오류가 발생 하면 변경 내용이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="70849-174">중복 테스트가 제거 되 면 명령을 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="70849-175">감시자 노드에서 가상 트랜잭션을 제거 하려면 Add 메서드 대신 Remove 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="70849-176">예를 들어이 명령은 감시자 노드에서 ABWQ 테스트를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="70849-177">Replace 메서드를 사용 하 여 현재 사용 가능한 모든 테스트를 하나 이상의 새 테스트로 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="70849-178">예를 들어, 감시자 노드만 IM 테스트를 실행 하려면 다음 명령을 사용 하 여이를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="70849-179">앞의 명령을 실행 하는 경우 IM을 제외한 지정 된 감시자 노드의 모든 가상 트랜잭션을 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70849-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="70849-180">감시자 노드 구성 보기 및 테스트</span><span class="sxs-lookup"><span data-stu-id="70849-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="70849-181">감시자 노드에 할당 된 테스트를 보려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="70849-182">앞의 명령은 노드에 할당 된 가상 트랜잭션에 따라 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="70849-183">가상 트랜잭션을 알파벳순으로 보려면 다음 명령을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="70849-184">Get-CsWatcherNodeConfiguration – Id "atl-cs-001.litwareinc.com" | 선택-개체-ExpandProperty 테스트 | 정렬 개체</span><span class="sxs-lookup"><span data-stu-id="70849-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="70849-185">감시자 노드가 만들어졌는지 확인 하려면 Lync Server 관리 셸 내에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="70849-186">다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70849-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="70849-187">감시자 노드가 올바르게 구성 되었는지 확인 하려면 Lync Server 관리 셸 내에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="70849-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="70849-188">앞의 명령은 배포에서 각 감시자 노드를 테스트 하 고 다음과 같은 정보를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70849-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="70849-189">필수 등록자 역할이 설치 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="70849-190">CsWatcherNodeConfiguration을 (를) 실행할 때 필요한 레지스트리 키가 생성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="70849-191">서버에서 올바른 버전의 Lync Server를 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="70849-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="70849-192">포트가 올바르게 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="70849-193">지정 된 테스트 사용자에 게 필요한 자격 증명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70849-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

