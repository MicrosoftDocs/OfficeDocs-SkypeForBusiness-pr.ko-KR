---
title: 'Lync Server 2013: Lync Online 고객과의 통신 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dffbb5d8a0e49e19c0fa5487a4af05b7e7f0155
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="41113-102">Lync Server 2013에서 Lync Online 고객과의 통신 확인</span><span class="sxs-lookup"><span data-stu-id="41113-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41113-103">_**마지막으로 수정 된 항목:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="41113-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="41113-104">조직의 Lync 사용자가 Microsoft Lync Online 2010 고객의 사용자와 통신할 수 있도록 하려면 다음 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41113-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="41113-105">모든 필수 구성 요소가 충족되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41113-105">Met all prerequisites.</span></span> <span data-ttu-id="41113-106">여기에는 내부 및 에지 서버 배포, 조직의 페더레이션 지원 설정 및 사용자 계정 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="41113-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="41113-107">자세한 내용은 [Lync Server 2013에서 Lync Online 고객과의 페더레이션을 위한 필수 구성 요소](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41113-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="41113-108">내부 배포에서 도메인 액세스 지원을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="41113-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="41113-109">여기에는 호스트 공급자 항목을 만들고 Lync Online 고객의 도메인에서 액세스를 허용 하도록 배포를 구성 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41113-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="41113-110">자세한 내용은 [Lync Server 2013에서 Lync Online 도메인에 대 한 페더레이션 지원 구성을](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41113-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="41113-111">페더레이션을 지원하도록 사용자 계정을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="41113-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="41113-112">자세한 내용은 [Lync Server 2013에서 Lync Online 고객과의 페더레이션을 위한 사용자 액세스 구성](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41113-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="41113-113">이러한 모든 단계를 완료 하 고 Lync Online 2010 고객의 관리자가 모든 온라인 서비스 구성을 완료 하 여 조직과의 페더레이션을 지원 하려면 내부에서 통신을 테스트 하 여 통신을 확인 합니다. 조직의 사용자 및 Lync Online 고객의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="41113-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="41113-114">통신이 실패할 경우 문제를 해결 하기 위해에 지 서버에서 로깅 도구를 사용 하 여 로그 및 추적 파일을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="41113-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="41113-115">로깅 도구를 사용 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41113-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="41113-116">로깅 도구에 대 한 자세한 내용은 TechNet 라이브러리에서 Lync Server 2010 로깅 도구 설명서를 참조 하십시오 [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span><span class="sxs-lookup"><span data-stu-id="41113-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

