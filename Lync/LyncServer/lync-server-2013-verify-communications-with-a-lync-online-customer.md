---
title: 'Lync Server 2013: Lync Online 고객과의 통신 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6707139535ab30909f74b1a3fa51cce24374d09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="172cc-102">Lync Server 2013에서 Lync Online 고객과 통신을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="172cc-103">_**마지막으로 수정한 주제:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="172cc-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="172cc-104">조직의 Lync 사용자가 Microsoft Lync Online 2010 고객의 사용자와 통신할 수 있도록 하려면 다음 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="172cc-105">모든 필수 조건을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-105">Met all prerequisites.</span></span> <span data-ttu-id="172cc-106">여기에는 내부 및 경계 서버 배포, 조직에 대 한 페더레이션 지원 설정, 사용자 계정 설정 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="172cc-107">자세한 내용은 [Lync Online 고객과 페더레이션 서버 2013에서 필수 구성 요소](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="172cc-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="172cc-108">내부 배포에서 도메인 액세스 지원을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="172cc-109">여기에는 호스트 공급자 항목 만들기 및 Lync Online 고객의 도메인에서 액세스할 수 있도록 배포를 구성 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="172cc-110">자세한 내용은 [Lync Server 2013에서 Lync Online 도메인에 대 한 페더레이션 지원 구성을](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="172cc-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="172cc-111">페더레이션을 지원 하도록 사용자 계정을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="172cc-112">자세한 내용은 [2013 Lync Online 고객과의 페더레이션에 대 한 사용자 액세스 구성](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="172cc-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="172cc-113">이러한 모든 단계를 완료 하 고 Lync Online 2010 고객의 관리자가 조직과의 페더레이션을 지원 하기 위해 온라인 서비스의 모든 구성을 완료 한 후 내부와 통신을 테스트 하 여 통신을 확인 합니다. 조직의 사용자 및 Lync Online 고객의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="172cc-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="172cc-114">통신에 실패 한 경우에는 Edge 서버의 로깅 도구를 사용 하 여 문제를 해결 하기 위해 로그 및 추적 파일을 캡처 하세요.</span><span class="sxs-lookup"><span data-stu-id="172cc-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="172cc-115">로깅 도구를 사용 하는 방법에 대 한 자세한 내용은 운영 설명서에서 [Lync Server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="172cc-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="172cc-116">로깅 도구에 대 한 자세한 내용은 TechNet 라이브러리에서 Lync Server 2010 로깅 도구 설명서를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span><span class="sxs-lookup"><span data-stu-id="172cc-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

