---
title: 'Lync Server 2013: 원격 통화 제어 및 전화 번호 정규화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86de318cb1e72fce8fb6f42ff7698db5974034fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="d8c5c-102">Lync Server 2013의 원격 통화 제어 및 전화 번호 정규화</span><span class="sxs-lookup"><span data-stu-id="d8c5c-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c5c-103">_**마지막으로 수정한 주제:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="d8c5c-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="d8c5c-104">Lync 클라이언트는 ABS (주소록 서비스) 파일 다운로드의 일부로 전화 번호 정규화 규칙을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="d8c5c-105">원격 통화 제어 시나리오에서 주소록 서비스 전화 번호 정규화 규칙은 수신 및 발신 원격 통화 제어 호출 모두에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="d8c5c-106">원격 통화 제어 기능을 사용 하는 사용자에 게 걸려오는 통화를 하려면 먼저 SIP/CSTA 게이트웨이 또는 개인 분기 교환 (PBX)을 통해 발신자의 전화 번호가 E. \ 164 형식으로 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="d8c5c-107">Lync Server 2013이 게이트웨이에서 전화를 받으면 호출 수신자의 Microsoft Office Outlook 연락처 목록에 있는 정규화 된 번호 또는 호출자의 전화 번호에 저장 된 GAL (전체 주소 목록)에서 RNL (역 번호 조회)를 수행 합니다. 주소록 서비스.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="d8c5c-108">역 번호 조회가 일치 하는 항목을 찾으면 들어오는 호출 알림에서 발신자를 이름으로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="d8c5c-109">보내는 원격 통화 제어 통화의 경우 Lync는 통화를 SIP/CSTA 게이트웨이로 라우팅하기 전에 전화 번호에 주소록 서비스 전화 번호 정규화 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="d8c5c-110">원격 통화 제어에 대 한 전화 번호 정규화 규칙을 만드는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="d8c5c-111">전화 번호 정규화 규칙 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d8c5c-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="d8c5c-112">이전에 원격 통화 제어에 대해 사용 하도록 설정 된 사용자를 마이그레이션하는 경우 마이그레이션 설명서에서 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="d8c5c-113">Lync Server 2010의 경우 마이그레이션 설명서에서 [주소록 마이그레이션을](migrate-address-book.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="d8c5c-114">통신 서버 2007 R2의 경우 마이그레이션 설명서에서 [주소록 마이그레이션을](migrate-address-book_1.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

