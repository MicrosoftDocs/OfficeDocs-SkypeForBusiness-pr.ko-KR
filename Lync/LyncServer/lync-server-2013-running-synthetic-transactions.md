---
title: 'Lync Server 2013: 가상 트랜잭션 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b77593ea062f83352592ebe32dbb81b99c1a9613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="c87e8-102">Lync Server 2013에서 가상 트랜잭션 실행</span><span class="sxs-lookup"><span data-stu-id="c87e8-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c87e8-103">_**마지막으로 수정한 주제:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="c87e8-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="c87e8-104">가상 트랜잭션은 일반적으로 두 가지 방법으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87e8-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="c87e8-105">CsHealthMonitoringConfiguration cmdlet을 사용 하 여 각 등록자 풀에 대 한 테스트 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87e8-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="c87e8-106">이러한 테스트 사용자는 가상 트랜잭션과 함께 사용 하도록 미리 구성한 사용자 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="c87e8-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="c87e8-107">일반적으로 이러한 계정은 테스트 계정이 며 실제 사용자에 속하는 계정이 아닙니다. 풀에 대해 구성 된 테스트 사용자는 테스트에 관련 된 사용자 계정에 대 한 id를 지정 하 고 해당 자격 증명을 제공할 필요 없이 해당 풀에 대해 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87e8-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="c87e8-108">또는 실제 사용자 계정을 사용 하 여 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87e8-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="c87e8-109">예를 들어 두 명의 사용자가 인스턴트 메시지를 교환할 수 없는 경우 테스트 계정 쌍이 아닌 두 개의 사용자 계정을 사용 하 여 가상 트랜잭션을 실행 한 다음 문제를 진단 하 고 해결 해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87e8-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="c87e8-110">실제 사용자 계정을 사용 하 여 가상 트랜잭션을 수행 하기로 결정 한 경우 각 사용자에 대 한 로그온 이름과 암호를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87e8-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c87e8-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c87e8-111">See Also</span></span>


[<span data-ttu-id="c87e8-112">Lync Server 2013에서 감시자 노드 테스트 사용자 및 구성 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c87e8-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="c87e8-113">Lync Server 2013의 종합 거래에 대 한 특별 한 설정 지침</span><span class="sxs-lookup"><span data-stu-id="c87e8-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

