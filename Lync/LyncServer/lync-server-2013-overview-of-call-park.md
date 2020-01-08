---
title: 'Lync Server 2013: 통화 공원 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d6f6b8f0f6a91e75071c7d103cf4bff3b4be1f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="65adc-102">Lync Server 2013의 통화 공원 개요</span><span class="sxs-lookup"><span data-stu-id="65adc-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65adc-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="65adc-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="65adc-104">Lync Server 2013 통화 공원 응용 프로그램을 통해 엔터프라이즈 음성 사용자는 다음 중 하나를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="65adc-105">통화를 대기 상태로 설정한 다음 같은 휴대폰 또는 다른 전화기에서 통화를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="65adc-106">통화를 대기 또는 일반 영역 (예: 영업부 또는 공통 지역 전화국에 거주 하는 영업 부서나 웨어하우스로)으로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="65adc-107">통화를 대기 상태로 전환 하 고 다른 통화를 위해 원래 응답 전화를 무료로 유지 하세요.</span><span class="sxs-lookup"><span data-stu-id="65adc-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="65adc-108">사용자가 통화를 전환 하는 경우 Lync Server는 전화를 걸거나 시간 초과 될 때까지 통화를 대기 하는 *회전*이라고 하는 임시 번호로 통화를 전송 합니다. Lync Server는 통화를 파킹 한 사용자에 게 궤도를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="65adc-109">파킹 된 통화를 검색 하기 위해 사용자는 궤도 번호로 전화를 걸거나 대화 창에서 궤도 링크 또는 단추를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="65adc-110">통화를 파킹 한 사용자는 다른 사용자에 게 궤도 번호를 전달 하는 메신저 대화 (인스턴트 메시징) 또는 페이징 시스템 등의 외부 메커니즘을 사용 하 여 전화를 받도록 다른 사람에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="65adc-111">통화를 파킹 한 사용자는 통화가 검색 될 때 알림을 받도록 대화 창을 열어 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="65adc-112">궤도 범위는 전역적으로 고유 하므로 라우팅이 적절 하 게 구성 된 경우 Lync Server 사이트 또는 PBX 휴대폰에서 전화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="65adc-113">구성 가능한 시간 내에 호출이 검색 되지 않는 경우에는 통화가 대기 하는 사용자에 게 다시 전화가 울립니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="65adc-114">해당 사용자가 ringback에 응답 하지 않는 경우 통화는 교환원 (예: 구성 된 경우)과 같은 대체 대상으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="65adc-115">통화가 1 ~ 10 번 전송 되기 전에 다시 울릴 횟수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="65adc-116">통화에 대 한 답이 없는 경우 통화의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="65adc-117">통화가 검색 되거나 연결이 끊어지면 궤도가 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="65adc-118">통화 공원를 배포 하는 경우 파킹 통화에 대 한 내선 번호 범위를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="65adc-119">이러한 확장은 사용자 또는 휴대폰을 할당 하지 않은 가상 확장 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="65adc-120">그런 다음 내선 번호 범위를 사용 하 여 통화 공원 표를 구성 하 고 각 범위를 처리 하는 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="65adc-121">각 프런트 엔드 풀에는 풀에서 파킹 된 통화를 관리 하는 데 사용 되는 해당 백 엔드 서버에 대 한 통화 공원 테이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="65adc-122">궤도 범위 목록은 중앙 관리 저장소에 저장 되며 대상 풀로 orbits를 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="65adc-123">통화 공원 응용 프로그램을 배포 하 고 구성 하는 각 Lync Server 풀은 하나 이상의 궤도 범위를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="65adc-124">궤도 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="65adc-125">또한 시간이 초과 되는 경우 통화가 리디렉션되는 위치, 휴대 중에는 전화의 상대방이 음악을 듣게 되는지 등 다른 통화 대기 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="65adc-126">통화 대기 중에 음악 파일을 재생 하도록 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65adc-127">통화 공원에 대 한 사용자 지정 음악 저장 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="65adc-128">통화 공원에 대해 업로드 한 사용자 지정 음악 보관 파일의 별도의 백업 복사본을 항상 보관 하세요.</span><span class="sxs-lookup"><span data-stu-id="65adc-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="65adc-129">통화 공원 응용 프로그램은 엔터프라이즈 음성의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="65adc-130">엔터프라이즈 음성을 배포 하는 경우 통화 공원 응용 프로그램이 자동으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="65adc-131">통화 대기를 사용 하기 전에 엔터프라이즈 음성 관리자가 음성 정책을 통해 사용자에 게이를 구성 하 고 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65adc-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

