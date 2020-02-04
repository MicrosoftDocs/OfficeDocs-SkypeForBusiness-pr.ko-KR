---
title: 'Lync Server 2013: 통합 연락처 저장소로 사용자 마이그레이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a57ea93af90176009fff43ed4dcca9f1880a658
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="37a8a-102">Lync Server 2013에서 통합 연락처 저장소로 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="37a8a-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a8a-103">_**마지막으로 수정한 주제:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="37a8a-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="37a8a-104">사용자의 연락처가 다음과 같이 자동으로 Exchange 2013 서버로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="37a8a-105">(으)로 지정 된 사용자 서비스 정책에 대 한 모든 권한이 True로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="37a8a-106">이 (가) Exchange 2013 사서함으로 프로 비전 되었으며 사서함에 한 번 이상 로그인 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="37a8a-107">Lync 2013 리치 클라이언트를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="37a8a-108">사용자가 Lync 2010 또는 이전 클라이언트를 사용 하 여 로그인 하거나 사용자가 Exchange 2013 서버에 연결 되어 있지 않은 경우 사용자 서비스 정책이 무시 되 고 사용자의 연락처가 Lync Server에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="37a8a-109">다음 방법 중 하나를 사용 하 여 사용자의 연락처가 마이그레이션 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="37a8a-110">클라이언트 컴퓨터에서 다음 레지스트리 키를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="37a8a-111">HKEY\_현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span><span class="sxs-lookup"><span data-stu-id="37a8a-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="37a8a-112">사용자의 연락처가 Exchange 2013에 저장 되어 있는 경우이 키에는 2165 값을 사용 하 여 InUCSMode 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="37a8a-113">**테스트 CsUnifiedContactStore** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="37a8a-114">Lync Server 관리 셸 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="37a8a-115">**테스트-CsUnifiedContactStore** 성공 하면 사용자의 연락처가 통일 된 대화 상대 저장소로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a8a-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

