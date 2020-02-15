---
title: 'Lync Server 2013: 다른 응용 프로그램에서 Lync 시작'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22f5e365e47ae7b6a41cd6e917b87718e07ac9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="442d1-102">다른 응용 프로그램에서 Lync 시작</span><span class="sxs-lookup"><span data-stu-id="442d1-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="442d1-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="442d1-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="442d1-104">명령줄 매개 변수를 사용 하 여 Lync 2013을 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="442d1-105">예를 들어 사용자가 다른 응용 프로그램에서 전화 번호를 클릭 하면 응용 프로그램은 Lync 2013 인스턴스를 시작 하 고 해당 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="442d1-106">Lync 2013에서 단체 회의를 위해 세미콜론으로 구분 된 연락처 이름 목록을 인식할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="442d1-107">Lync 2013을 시작할 때 자동으로 로그인 하도록 구성한 경우 명령줄 매개 변수를 사용 하 여 Lync 2013을 시작 하면 Lync 주 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="442d1-108">Lync가 시작 시에 자동으로 로그인하도록 구성되지 않은 경우에는 로그인 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="442d1-109">다음 표에는 사용 가능한 매개 변수가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="442d1-110">Lync 2013 명령줄 매개 변수</span><span class="sxs-lookup"><span data-stu-id="442d1-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="442d1-111">Extension</span><span class="sxs-lookup"><span data-stu-id="442d1-111">Extension</span></span></th>
<th><span data-ttu-id="442d1-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="442d1-112">Format of Data</span></span></th>
<th><span data-ttu-id="442d1-113">동작은</span><span class="sxs-lookup"><span data-stu-id="442d1-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="442d1-114">tel</span><span class="sxs-lookup"><span data-stu-id="442d1-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="442d1-115">tel URI</span><span class="sxs-lookup"><span data-stu-id="442d1-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="442d1-116">음성 통화용 대화 창을 열지만 지정된 번호로 전화를 걸지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="442d1-117">callto</span><span class="sxs-lookup"><span data-stu-id="442d1-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="442d1-118">tel:, sip: 또는 입력 가능한 tel URI</span><span class="sxs-lookup"><span data-stu-id="442d1-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="442d1-119">음성 통화용 대화 창을 열지만 지정된 번호로 전화를 걸지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="442d1-120">호흡</span><span class="sxs-lookup"><span data-stu-id="442d1-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="442d1-121">SIP URI</span><span class="sxs-lookup"><span data-stu-id="442d1-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="442d1-122">참가자 목록에 지정된 SIP URI(Uniform Resource Identifier)가 포함된 대화 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="442d1-123">Sip</span><span class="sxs-lookup"><span data-stu-id="442d1-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="442d1-124">SIP URI</span><span class="sxs-lookup"><span data-stu-id="442d1-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="442d1-125">Lync 2013이 TLS (전송 계층 보안) 프로토콜을 사용 하도록 구성 된 경우 sip:과 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="442d1-126">TLS를 사용하지 않는 경우에는 더욱 높은 보안 수준이 필요함을 사용자에게 알리는 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="442d1-127">회의</span><span class="sxs-lookup"><span data-stu-id="442d1-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="442d1-128">참가할 회의의 SIP URI</span><span class="sxs-lookup"><span data-stu-id="442d1-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="442d1-p104">자체 URI의 경우 포커스를 인스턴스화하고 명단 전용 보기를 표시합니다. 그렇지 않은 경우에는 명단 보기를 표시하되 INVITE를 보내지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="442d1-131">메시징을</span><span class="sxs-lookup"><span data-stu-id="442d1-131">im:</span></span></p></td>
<td><p><span data-ttu-id="442d1-132">SIP URI</span><span class="sxs-lookup"><span data-stu-id="442d1-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="442d1-133">SIP URI가 포함된 IM(인스턴트 메시징) 전용 대화 창을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="442d1-134">구분 기호 없이 꺾쇠 괄호 () 안쪽에&lt;&gt;지정 된 여러 SIP uri를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="442d1-135">다음 표에는 이러한 명령줄 매개 변수의 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="442d1-136">명령줄 매개 변수 예제</span><span class="sxs-lookup"><span data-stu-id="442d1-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="442d1-137">Instance</span><span class="sxs-lookup"><span data-stu-id="442d1-137">Instance</span></span></th>
<th><span data-ttu-id="442d1-138">결과</span><span class="sxs-lookup"><span data-stu-id="442d1-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="442d1-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="442d1-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="442d1-140">+14255550101이 포함된 전화 전용 보기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="442d1-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="442d1-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="442d1-142">+14255550101이 포함된 전화 전용 보기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="442d1-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="442d1-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="442d1-144">kazuto@litwareinc.com이 포함된 전화 전용 보기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="442d1-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="442d1-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="442d1-146">kazuto@litwareinc.com이 포함된 대화 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="442d1-147">회의: sip:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="442d1-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="442d1-148">대화 창을 열고 모임 오디오 가입 옵션을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="442d1-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

