---
title: 'Lync Server 2013: 통합 메시징 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da109ebb48ff483d117f41297749386b8f0462f8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526755"
---
# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="f65fc-102">통합 메시징 및 Lync Server 2013의 기능</span><span class="sxs-lookup"><span data-stu-id="f65fc-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f65fc-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f65fc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f65fc-104">Lync Server 2013, Enterprise Voice는 Exchange UM (통합 메시징) 인프라를 사용 하 여 전화 응답, 통화 알림, 음성 액세스 (음성 메일 포함) 및 자동 전화 교환 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="f65fc-105">전화 응답</span><span class="sxs-lookup"><span data-stu-id="f65fc-105">Call Answering</span></span>

<span data-ttu-id="f65fc-106">전화 응답은 호출이 응답 하지 않거나 다른 사용자를 대신 하 여 음성 메시지를 받는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="f65fc-107">여기에는 개인 인사말 재생, 메시지 녹음 및 Exchange 사서함 서버에 저장 된 사용자의 사서함으로 배달 대기 중인 메시지 전송 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="f65fc-p102">발신자가 남긴 메시지는 사용자의 받은 편지함으로 라우팅됩니다. 발신자가 메시지를 남기지 않으면 부재 중 전화 알림이 사용자의 사서함에 저장됩니다. 그러면 사용자는 Microsoft Outlook 메시징 및 공동 작업 클라이언트, Outlook Web Access, Exchange ActiveSync 기술 또는 Outlook Voice Access를 사용하여 받은 편지함에 액세스할 수 있습니다. 통화의 제목과 우선 순위는 전자 메일과 유사한 방식으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="f65fc-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="f65fc-112">Outlook Voice Access</span></span>

<span data-ttu-id="f65fc-113">Outlook Voice Access를 사용하면 Enterprise Voice 사용자가 음성 메일에 액세스할 수 있을 뿐 아니라 전화 통신 인터페이스의 전자 메일, 일정 및 연락처를 포함하는 Exchange 받은 편지함에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="f65fc-114">구독자 액세스 번호는 Exchange UM 관리자가 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="f65fc-115">자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="f65fc-115">Auto Attendant</span></span>

<span data-ttu-id="f65fc-116">자동 전화 교환은 외부 사용자가 회사 대표자에 게 전화를 걸 수 있는 전화 번호를 구성 하는 데 사용할 수 있는 Exchange UM 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="f65fc-117">특히 이 기능은 외부 발신자가 메뉴 시스템을 탐색하는 데 도움이 되는 일련의 음성 안내 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="f65fc-118">사용 가능한 옵션 목록은 Exchange um 관리자가 Exchange UM 서버에서 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="f65fc-119">팩스 서비스</span><span class="sxs-lookup"><span data-stu-id="f65fc-119">Fax Services</span></span>

<span data-ttu-id="f65fc-120">Exchange UM에는 사용자가 Exchange 사서함에서 수신 팩스를 받을 수 있도록 하는 팩스 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="f65fc-121">자세한 내용은 Microsoft Exchange Server 설명서의 "통합 메시징"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652) .</span><span class="sxs-lookup"><span data-stu-id="f65fc-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f65fc-122">Exchange UM 서버에서 제공 하는 팩스 서비스는 Microsoft Exchange Server 2010, Exchange 2010 최신 서비스 팩 또는 Exchange 2013과 통합 된 Lync Server 배포에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f65fc-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

