---
title: 'Lync Server 2013: 지정 되지 않은 번호로 전화 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14229f4550773c8b75460cca544da2298129f518
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="d29d2-102">Lync Server 2013에서 할당 되지 않은 번호에 대 한 통화 관리</span><span class="sxs-lookup"><span data-stu-id="d29d2-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d29d2-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d29d2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d29d2-104">Lync Server를 사용 하 여 조직에서 전화 건 번호를 사용할 수 있지만 사용자 또는 전화에 게 할당 되지 않은 수신 전화 통화에 대 한 처리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d29d2-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="d29d2-105">알림 응용 프로그램을 사용 하 여 이러한 통화를 미리 결정 된 대상 (전화 번호, SIP URI 또는 음성 메일)으로 전송 하거나 오디오 알림을 재생 하거나 두 가지 모두를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d29d2-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="d29d2-106">또한 이러한 통화를 Exchange UM 자동 전화 교환 전화 번호로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d29d2-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="d29d2-107">발신자가 번호를 잘못 눌러 통화 중 신호를 듣게 되거나 SIP 클라이언트가 오류 메시지를 수신하는 경우를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d29d2-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="d29d2-p102">이 섹션에서는 할당되지 않은 전화 번호로 걸린 전화를 처리하기 위해 할당되지 않은 번호 범위를 관리하는 방법에 대해 설명합니다. 또한 중단 시 알림 기능을 사용하려는 경우 재해 복구 시 알림을 관리하는 방법에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d29d2-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d29d2-110">중단 시 할당되지 않은 번호 처리를 사용하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d29d2-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d29d2-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d29d2-111">In This Section</span></span>

  - [<span data-ttu-id="d29d2-112">Lync Server 2013에서 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="d29d2-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="d29d2-113">Lync Server 2013에서 할당 되지 않은 전화 번호 구성</span><span class="sxs-lookup"><span data-stu-id="d29d2-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="d29d2-114">Lync Server 2013에서 재해 복구 시 알림 관리</span><span class="sxs-lookup"><span data-stu-id="d29d2-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

