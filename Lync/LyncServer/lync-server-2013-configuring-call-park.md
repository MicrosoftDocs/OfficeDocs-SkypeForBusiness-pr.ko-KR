---
title: 'Lync Server 2013: 통화 대기 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e2a1c6ef9da447688ea1ca7d0308afc0b4ab9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="a44e7-102">Lync Server 2013에서 통화 대기 구성</span><span class="sxs-lookup"><span data-stu-id="a44e7-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a44e7-103">_**마지막으로 수정한 주제:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="a44e7-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="a44e7-104">통화 대기-엔터프라이즈 음성 사용자는 전화를 걸 수 있으며, 나중에 모든 전화기에서 내부 번호 (통화 공원 *회전*이라고 함)로 전화를 걸어 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="a44e7-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="a44e7-105">통화 대기를 사용 하는 구성 요소는 엔터프라이즈 음성을 구축할 때 프런트 엔드 서버 또는 Standard Edition 서버에서 자동으로 설치 되 고 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44e7-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a44e7-106">그러나 사용자에 게 전화를 걸 수 있으려면 먼저 통화 대기를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44e7-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="a44e7-107">이 섹션에서는 통화 공원 구성 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44e7-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a44e7-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a44e7-108">In This Section</span></span>

  - [<span data-ttu-id="a44e7-109">Lync Server 2013의 통화 대기 구성 필수 구성 요소 및 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="a44e7-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="a44e7-110">Lync Server 2013의 통화 공원 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="a44e7-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="a44e7-111">Lync Server 2013에서 통화 대기 번호 테이블 구성</span><span class="sxs-lookup"><span data-stu-id="a44e7-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="a44e7-112">Lync Server 2013에서 통화 공원 설정 구성</span><span class="sxs-lookup"><span data-stu-id="a44e7-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="a44e7-113">Lync Server 2013에서 통화 공원 음악을 보류할 때 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a44e7-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="a44e7-114">Lync Server 2013에서 사용자 용 통화 공원 사용</span><span class="sxs-lookup"><span data-stu-id="a44e7-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="a44e7-115">Lync Server 2013에서 통화 공원에 대 한 정규화 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="a44e7-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="a44e7-116">) Lync Server 2013에서 통화 공원 배포 확인</span><span class="sxs-lookup"><span data-stu-id="a44e7-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

