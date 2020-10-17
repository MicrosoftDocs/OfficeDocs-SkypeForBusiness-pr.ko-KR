---
title: 'Lync Server 2013: 지정 되지 않은 전화 번호 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd933ac87addf4a2094009e9f437c29437d882a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520235"
---
# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="7f894-102">Lync Server 2013에서 할당 되지 않은 전화 번호 구성</span><span class="sxs-lookup"><span data-stu-id="7f894-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f894-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7f894-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7f894-104">Lync Server를 사용 하 여 조직에 적합 하지만 사용자 또는 전화에 할당 되지 않은 전화 번호로 들어오는 호출에 대해 수행할 작업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f894-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="7f894-105">이러한 전화에 대한 처리를 구성하려면 할당되지 않은 번호 테이블을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f894-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="7f894-106">이 표를 사용 하 여 알림 응용 프로그램 또는 Exchange UM 서버에 대 한 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f894-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="7f894-p102">할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다. 할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다. 할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다. 테이블에 할당되지 않은 내선 번호를 포함하면 특정 번호에 대해 발생하는 동작을 조정할 수 있습니다. 예를 들어 고객 서비스 센터의 내선 번호를 변경하려면 테이블에 기존의 고객 서비스 센터 번호를 포함하고 새 번호를 제공하는 알림에 이 번호를 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f894-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f894-113">할당 되지 않은 번호 테이블을 구성 하기 전에 하나 이상의 알림이 정의 되어 있거나 Exchange UM 자동 전화 교환이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f894-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="7f894-114">알림을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-an-announcement.md">Create a 공고 in a Lync Server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f894-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="7f894-115">Exchange UM 설정을 구성 했는지 확인 하려면 <STRONG>get-help</STRONG> cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f894-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="7f894-116">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f894-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f894-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7f894-117">In This Section</span></span>

  - [<span data-ttu-id="7f894-118">Lync Server 2013에서 할당 되지 않은 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="7f894-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="7f894-119">Lync Server 2013에서 할당 되지 않은 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="7f894-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

