---
title: 'Lync Server 2013: 지정 하지 않은 번호로의 통화 관리'
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
ms.openlocfilehash: 571bddf8de62d7b22ac23a3b00de740030a2f7ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="d56d5-102">Lync Server 2013에서 할당 되지 않은 번호로의 통화 관리</span><span class="sxs-lookup"><span data-stu-id="d56d5-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d56d5-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d56d5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d56d5-104">전화 거는 번호가 조직에 대해 유효 하지만 사용자 또는 전화기에 할당 되지 않은 경우 Lync Server를 사용 하 여 수신 전화 통화 처리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56d5-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="d56d5-105">알림 응용 프로그램을 사용 하 여 이러한 통화를 미리 지정 된 대상 (전화 번호, SIP URI 또는 음성 메일)으로 전송 하거나 오디오 알림 또는 두 가지 모두를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56d5-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="d56d5-106">이러한 통화를 Exchange UM 자동 전화 교환 전화 번호로 양도할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56d5-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="d56d5-107">이러한 방법 중 하나를 사용 하 여 할당 되지 않은 번호로 전화를 처리 하면 호출자가 전화를 건 후 통화 중 발신음을 듣게 하거나 SIP 클라이언트에 오류 메시지가 표시 되는 상황을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56d5-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="d56d5-108">이 섹션에서는 지정 하지 않은 번호 범위를 관리 하 여 할당 되지 않은 전화 번호로 전화를 처리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56d5-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="d56d5-109">또한이 섹션에서는 장애 복구 중에이 기능을 사용할 수 있는 경우에 대 한 알림을 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56d5-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d56d5-110">중단 중에 할당 되지 않은 번호 처리를 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d56d5-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d56d5-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d56d5-111">In This Section</span></span>

  - [<span data-ttu-id="d56d5-112">Lync Server 2013에서 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="d56d5-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="d56d5-113">Lync Server 2013에서 할당 되지 않은 전화 번호 구성</span><span class="sxs-lookup"><span data-stu-id="d56d5-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="d56d5-114">Lync Server 2013에서 재해 복구 시 알림 관리</span><span class="sxs-lookup"><span data-stu-id="d56d5-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

