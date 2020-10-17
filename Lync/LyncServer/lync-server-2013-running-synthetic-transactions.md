---
title: 'Lync Server 2013: 가상 트랜잭션 실행'
description: 'Lync Server 2013: 가상 트랜잭션을 실행 합니다.'
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
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569354"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="9bdc4-103">Lync Server 2013에서 가상 트랜잭션 실행</span><span class="sxs-lookup"><span data-stu-id="9bdc4-103">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bdc4-104">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="9bdc4-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="9bdc4-105">가상 트랜잭션은 일반적으로 두 가지 방식으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bdc4-105">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="9bdc4-106">Get-cshealthmonitoringconfiguration cmdlet을 사용 하 여 각 등록자 풀에 대해 테스트 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bdc4-106">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="9bdc4-107">이러한 테스트 사용자는 가상 트랜잭션과 함께 사용 하도록 미리 구성 된 사용자 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="9bdc4-107">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="9bdc4-108">일반적으로 테스트 계정이 며 실제 사용자에 게 속하는 계정이 아닙니다. 풀에 대해 구성 된 테스트 사용자를 사용 하 여 테스트에 포함 된 사용자 계정에 대 한 id를 지정 하지 않고도 해당 풀에 대해 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bdc4-108">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="9bdc4-109">또는 실제 사용자 계정을 사용 하 여 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bdc4-109">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="9bdc4-110">예를 들어 두 명의 사용자가 인스턴트 메시지를 교환할 수 없는 경우 테스트 계정 쌍 대신 이러한 두 사용자 계정을 사용 하 여 가상 트랜잭션을 실행 한 다음 문제를 진단 하 고 해결 해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bdc4-110">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="9bdc4-111">실제 사용자 계정을 사용 하 여 가상 트랜잭션을 수행 하기로 결정 한 경우 각 사용자에 대 한 로그온 이름과 암호를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bdc4-111">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9bdc4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bdc4-112">See Also</span></span>


[<span data-ttu-id="9bdc4-113">Lync Server 2013에서 감시자 노드 테스트 사용자 및 구성 설정 구성</span><span class="sxs-lookup"><span data-stu-id="9bdc4-113">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="9bdc4-114">Lync Server 2013의 가상 트랜잭션에 대 한 특별 설치 지침</span><span class="sxs-lookup"><span data-stu-id="9bdc4-114">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

