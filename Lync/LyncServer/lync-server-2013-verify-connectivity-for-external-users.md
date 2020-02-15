---
title: 'Lync Server 2013: 외부 사용자에 대 한 연결 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14d3dbc74119ff4f5669776dafce8a7cc2dee21a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="2e6b7-102">Lync Server 2013에서 외부 사용자에 대 한 연결 확인</span><span class="sxs-lookup"><span data-stu-id="2e6b7-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e6b7-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2e6b7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2e6b7-104">외부 사용자의 연결 유효성을 검사하려면 액세스 에지 서비스에 대해 사용자로부터 서버 및 포트로의 연결을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="2e6b7-105">구성을 확인 하 고, 외부 사용자 액세스에 필요한 시나리오에 대해 올바른 메시지를 보내고 받을 수 있는 기능을 구성 하는 데 유용한 리소스로는 원격 연결 분석기 사이트 (<http://www.testocsconnectivity.com>)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="2e6b7-106">이 사이트는 Microsoft 지원 서비스에 의해 관리 및 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="2e6b7-107">원격 연결 분석기에 연결하려면 브라우저에서 웹 사이트를 열고 지침에 따라 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="2e6b7-108">외부 사용자 및 외부 액세스 연결 테스트</span><span class="sxs-lookup"><span data-stu-id="2e6b7-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="2e6b7-109">외부 사용자 액세스 테스트에는 다음 중 일부 또는 모든 항목을 비롯하여 조직에서 지원하는 각 외부 사용자 유형이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="2e6b7-110">하나 이상의 페더레이션 도메인, 테스트 IM, 현재 상태, A/V 및 데스크톱 공유에 속한 사용자</span><span class="sxs-lookup"><span data-stu-id="2e6b7-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="2e6b7-111">조직에서 지원하며 구축이 완료된 각 공용 IM 서비스 공급자의 사용자</span><span class="sxs-lookup"><span data-stu-id="2e6b7-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="2e6b7-112">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="2e6b7-112">Anonymous users.</span></span>

  - <span data-ttu-id="2e6b7-113">Lync에 원격으로 로그인했으나 VPN을 사용하지는 않는 조직 내의 사용자</span><span class="sxs-lookup"><span data-stu-id="2e6b7-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="2e6b7-114">이러한 테스트에서는 에지 서버에 대해 다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="2e6b7-115">네트워크 외부의 텔넷 클라이언트를 사용하여 필요한 포트를 수신 대기하는지 여부</span><span class="sxs-lookup"><span data-stu-id="2e6b7-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="2e6b7-116">예: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="2e6b7-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="2e6b7-117">배포에 따라 에지 서버 또는 에지 서버 풀에서 사용 중인 포트에 대해 위의 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="2e6b7-118">정확한 외부 DNS 확인을 수행하는지 여부</span><span class="sxs-lookup"><span data-stu-id="2e6b7-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="2e6b7-p102">네트워크 외부에서 에지 또는 에지 풀의 각 FQDN에 대해 네트워크 ping을 수행합니다. ping이 실패해도 IP 주소는 표시되므로 지정한 주소와 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6b7-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

