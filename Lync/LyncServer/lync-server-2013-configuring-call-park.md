---
title: 'Lync Server 2013: 통화 대기 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2932053e8224b751c124c80152c097d9da82e517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="e0638-102">Lync Server 2013에서 통화 대기 구성</span><span class="sxs-lookup"><span data-stu-id="e0638-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0638-103">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="e0638-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="e0638-104">통화 대기를 사용 하면 Enterprise Voice 사용자가 전화 통화를 한 전화기로 전환한 다음 나중에 전화로 전화 걸기 (통화 대기 *궤도*라고 함)를 모든 전화기에서 검색 하 여 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0638-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="e0638-105">통화 대기를 사용 하는 구성 요소는 Enterprise Voice를 배포할 때 자동으로 설치 되 고 프런트 엔드 서버 또는 Standard Edition 서버에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0638-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e0638-106">그러나 사용자에 게 통화 대기를 사용 하려면 먼저 전화 대기를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0638-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="e0638-107">이 섹션에서는 통화 대기를 구성 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0638-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0638-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e0638-108">In This Section</span></span>

  - [<span data-ttu-id="e0638-109">Lync Server 2013의 통화 대기 구성 선행 조건 및 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="e0638-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="e0638-110">Lync Server 2013의 통화 대기 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="e0638-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="e0638-111">Lync Server 2013의 통화 대기 궤도 테이블 구성</span><span class="sxs-lookup"><span data-stu-id="e0638-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="e0638-112">Lync Server 2013의 통화 대기 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e0638-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="e0638-113">Lync Server 2013에서 통화 대기 음악 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e0638-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="e0638-114">Lync Server 2013의 사용자에 대해 통화 대기를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e0638-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="e0638-115">Lync Server 2013의 통화 대기에 대 한 정규화 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="e0638-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="e0638-116">반드시 Lync Server 2013의 통화 대기 배포 확인</span><span class="sxs-lookup"><span data-stu-id="e0638-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

