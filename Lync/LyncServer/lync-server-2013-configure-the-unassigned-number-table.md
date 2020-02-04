---
title: 'Lync Server 2013: 지정되지 않은 번호 테이블 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="2dce5-102">Lync Server 2013에서 지정되지 않은 번호 테이블 구성</span><span class="sxs-lookup"><span data-stu-id="2dce5-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dce5-103">_**마지막으로 수정한 주제:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="2dce5-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="2dce5-104">Lync Server 2013에서 조직에 대해 유효 하지만 사용자 또는 휴대폰에 할당 되지 않은 전화 번호로 들어오는 호출에 대해 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="2dce5-105">발신자는 메시지를 듣거나 다른 대상 또는 둘 다에 게 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="2dce5-106">할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-106">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="2dce5-107">조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-107">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="2dce5-108">할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-108">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="2dce5-109">할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-109">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="2dce5-110">표에 할당 되지 않은 확장명을 포함 하는 경우 특정 숫자에 대해 발생 하는 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-110">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="2dce5-111">예를 들어 고객 서비스 데스크에 대 한 내선 번호를 변경 하는 경우에는 테이블에 이전의 고객 서비스 번호가 포함 된 다음 새 번호를 제공 하는 공지 사항에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-111">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2dce5-112">할당 되지 않은 번호 테이블을 구성 하기 전에 시스템에 이미 공지가 정의 되어 있거나 UM (Exchange 통합 메시징) 자동 전화 교환이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="2dce5-113">다른 사용자가 지정 되지 않은 번호를 호출 하는 경우, Lync Server는 지정 되지 않은 번호 표를 위에서 아래로 검색 하 고 첫 번째 일치 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="2dce5-114">따라서 표의 마지막 범위에 대해 마지막 수단으로 수행 하려는 작업을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dce5-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2dce5-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2dce5-115">In This Section</span></span>

<span data-ttu-id="2dce5-116">Lync [server 2013에서 할당 되지 않은 번호 범위 만들기 또는 수정](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [lync server 2013에서 알림 만들기](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="2dce5-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

