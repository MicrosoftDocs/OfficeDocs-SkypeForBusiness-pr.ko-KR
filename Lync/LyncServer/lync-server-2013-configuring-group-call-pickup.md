---
title: 'Lync Server 2013: 그룹 통화 픽업 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d7f82d976d3e6e2594cecafe5634edfe0b52841
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="a5341-102">Lync Server 2013에서 그룹 통화 픽업 구성</span><span class="sxs-lookup"><span data-stu-id="a5341-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5341-103">_**마지막으로 수정한 주제:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="a5341-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="a5341-104">Lync Server의 누적 업데이트 2013:2013 2 월에는 그룹 통화 픽업 Pickup가 새로운 엔터프라이즈 음성 기능으로 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5341-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="a5341-105">그룹 통화 픽업 사용자는 통화 픽업 그룹 번호로 전화를 걸어 다른 사용자에 게 연결 되는 통화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5341-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="a5341-106">그룹 통화 픽업이 사용 하는 구성 요소는 엔터프라이즈 음성을 구축할 때 프런트 엔드 서버 또는 Standard Edition 서버에서 자동으로 설치 되 고 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5341-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a5341-107">그러나 사용자가 그룹 통화 픽업 연결을 사용할 수 있으려면 먼저 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5341-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="a5341-108">이 섹션에서는 그룹 통화 픽업 구성 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5341-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5341-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a5341-109">In This Section</span></span>

[<span data-ttu-id="a5341-110">Lync Server 2013의 그룹 통화 픽업 구성 선행 조건 및 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="a5341-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="a5341-111">Lync Server 2013의 그룹 통화 픽업 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="a5341-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="a5341-112">Lync Server 2013에서 SEFAUtil 도구 배포</span><span class="sxs-lookup"><span data-stu-id="a5341-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="a5341-113">Lync Server 2013에서 통화 픽업 그룹 번호 구성</span><span class="sxs-lookup"><span data-stu-id="a5341-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="a5341-114">Lync Server 2013에서 사용자의 그룹 통화 픽업 기능을 사용 하도록 설정 하 고 그룹 번호 지정</span><span class="sxs-lookup"><span data-stu-id="a5341-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="a5341-115">Lync Server 2013에서 사용자에 게 그룹 통화 픽업 배정 전달</span><span class="sxs-lookup"><span data-stu-id="a5341-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="a5341-116">) Lync Server 2013에서 그룹 통화 픽업 배포 확인</span><span class="sxs-lookup"><span data-stu-id="a5341-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

