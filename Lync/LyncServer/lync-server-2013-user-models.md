---
title: 'Lync Server 2013: 사용자 모델'
description: 'Lync Server 2013: 사용자 모델'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15be3f4c002de6cfb9ade4f13d80aedb59d76a82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569764"
---
# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="b521a-103">Lync Server 2013의 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-103">User models in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b521a-104">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b521a-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b521a-105">여기에 설명 된 사용자 모델은 [사용자 모델을 사용 하 여 Lync Server 2013의 용량 계획](lync-server-2013-capacity-planning-using-the-user-models.md)에 설명 된 용량 계획 측정값 및 권장 사항에 대 한 토대를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-105">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="b521a-106">Lync Server 2013 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-106">Lync Server 2013 User Models</span></span>

<span data-ttu-id="b521a-107">다음 표에서는 Lync Server 2013의 등록, 연락처, IM (인스턴트 메시징) 및 현재 상태에 대 한 사용자 모델을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-107">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="b521a-108">환경 및 등록 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-108">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-109">범주</span><span class="sxs-lookup"><span data-stu-id="b521a-109">Category</span></span></th>
<th><span data-ttu-id="b521a-110">설명</span><span class="sxs-lookup"><span data-stu-id="b521a-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-111">배포 크기 및 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-111">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-112">모델링하는 대상은 대규모 배포로, 3개의 중앙 사이트와 사이트당 하나의 프런트 엔드 풀이 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-112">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-113">Active Directory 사용자의 비율(%)</span><span class="sxs-lookup"><span data-stu-id="b521a-113">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="b521a-114">조직의 모든 Active Directory 사용자 중 70%가 Lync Server에 대해 사용 된다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-114">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="b521a-115">이 사용 가능한 사용자의 80%가 매일 Lync Server에 로그온 되어 있습니다 (80% 동시).</span><span class="sxs-lookup"><span data-stu-id="b521a-115">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="b521a-116">동시 사용자 수는 이 섹션의 나머지 부분에 나오는 수치의 기본 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-116">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-117">Active Directory 변경 사항</span><span class="sxs-lookup"><span data-stu-id="b521a-117">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="b521a-118">총 사용자의 0.5%가 매주 Active Directory의 Lync에 대해 만들어지고 사용 하도록 설정 되어 있으며, 총 사용자의 0.5%는 Active Directory 및 각 주에 Lync에서 사용 하지 않도록 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-118">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="b521a-119">사용자의 5%는 매주 하나 이상의 Active Directory 특성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-119">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-120">Active Directory 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="b521a-120">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="b521a-p103">조직의 Active Directory 메일 그룹 수는 Active Directory에 있는 모든 사용자 수의 3배와 동일한 것으로 가정합니다. 메일 그룹의 크기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="b521a-123">64%: 2-30명의 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-123">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="b521a-124">13%: 31-50명의 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-124">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="b521a-125">10%: 51-100명의 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-125">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="b521a-126">13%: 101-500명의 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-126">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-127">VoIP(Voice over IP) 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-127">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="b521a-128">Lync Server 사용자의 60%는 UC (통합 통신)를 사용 하도록 설정 되어 있습니다 (즉, 전화 번호는 Lync Server에서 소유 함).</span><span class="sxs-lookup"><span data-stu-id="b521a-128">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-129">등록된 클라이언트 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-129">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-130">클라이언트의 65%는 Lync 및 Lync Phone Edition을 포함 하 여 Lync 2013 소프트웨어를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-130">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="b521a-131">이전 버전의 Lync에서 클라이언트 소프트웨어를 실행 하는 클라이언트의 30%</span><span class="sxs-lookup"><span data-stu-id="b521a-131">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="b521a-132">Lync Web App을 사용 하는 클라이언트의 5%</span><span class="sxs-lookup"><span data-stu-id="b521a-132">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="b521a-133">이동성을 사용 하도록 설정 하면 사용자의 40%가 이전에 설명한 다른 모든 등록 된 클라이언트 옵션과 동시에 모바일 기능을 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-133">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="b521a-134">이 경우 클라이언트의 다중 현재 상태 (MPOP) 비율은 1:1.9입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-134">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="b521a-135">모바일을 사용하지 않도록 설정하면 MPOP 비율이 1:1.5가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-135">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-136">원격 사용자 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-136">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-137">사용자의 70%는 내부에서 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-137">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="b521a-138">사용자의 30%는 에지 서버 및 디렉터를 통해 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-138">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-139">대화 상대 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-139">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-p105">사용자가 유지할 수 있는 최대 대화 상대 수는 1,000명입니다. 대화 상대 수가 1,000명인 사용자는 1% 미만입니다. 또한 25% 미만의 사용자는 대화 상대 수가 100명 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="b521a-p106">사용자의 대화 상대 중 평균 80명은 공용 클라우드를 통해 연결합니다. 이러한 사용자의 비율은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="b521a-p107">대화 상대의 50%는 조직 내에 있습니다. 이러한 사용자의 10%는 방화벽 외부에서 연결하는 원격 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="b521a-147">대화 상대의 40%는 공용 클라우드 사용자(예: AOL, Yahoo!, MSN, Google Talk 사용자)입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-147">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="b521a-148">대화 상대의 10%는 페더레이션 파트너의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-148">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="b521a-149">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-149">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b521a-150">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-150">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b521a-151">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="b521a-151">Messenger until the service shut down date.</span></span> <span data-ttu-id="b521a-152">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="b521a-152">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b521a-153">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-153">has been announced.</span></span> <span data-ttu-id="b521a-154">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b521a-154">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b521a-155">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-155">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b521a-156">메신저로.</span><span class="sxs-lookup"><span data-stu-id="b521a-156">Messenger.</span></span> <span data-ttu-id="b521a-157">이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-157">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="b521a-158">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-158">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b521a-159">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-159">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b521a-160">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-160">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="b521a-p111">사용자의 대화 상대 중 평균 50명은 공용 클라우드 연결을 사용하지 않습니다. 이러한 사용자의 비율은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="b521a-p112">대화 상대의 80%는 조직 내에 있습니다. 이러한 사용자의 10%는 방화벽 외부에서 연결하는 원격 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="b521a-165">대화 상대의 20%는 페더레이션 파트너의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-165">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="b521a-p113">각 사용자에게는 대화 상대 목록에 하나의 메일 그룹이 있습니다. 성능 테스트를 위해 메일 그룹은 항상 확장된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="b521a-168">25%의 사용자 대화 상대가 XMPP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-168">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-169">세션 시간</span><span class="sxs-lookup"><span data-stu-id="b521a-169">Session time</span></span></p></td>
<td><p><span data-ttu-id="b521a-p114">평균 사용자 로그온 세션은 12시간 동안 지속됩니다. 모든 사용자가 세션 시작 후 120분 이내에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="b521a-172">메신저 및 현재 상태 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-172">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-173">범주</span><span class="sxs-lookup"><span data-stu-id="b521a-173">Category</span></span></th>
<th><span data-ttu-id="b521a-174">설명</span><span class="sxs-lookup"><span data-stu-id="b521a-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-175">피어 투 피어 메신저 세션</span><span class="sxs-lookup"><span data-stu-id="b521a-175">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="b521a-176">각 사용자는 하루 평균 6개의 피어 투 피어 메신저 세션에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-176">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="b521a-177">세션당 메신저 메시지 수는 10개입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-177">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="b521a-178">각 메시지는 SIP 정보 메시지 두 개와 SIP 200 정상 메시지 2 개 (" &lt; 이름이 입력 됨"와 같은 상태 표시기의 경우)와 일치 합니다. &gt;</span><span class="sxs-lookup"><span data-stu-id="b521a-178">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-179">현재 상태 폴링</span><span class="sxs-lookup"><span data-stu-id="b521a-179">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="b521a-p115">전반적으로 현재 상태 폴링을 사용자당 1시간에 평균 60개 설문으로 가정합니다. 각 사용자에 대해 다음과 같은 평균을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="b521a-p116">사용자의 조직 탭(대화 상대 목록이 아님)에 있는 사용자의 현재 상태에 대해 하루에 하나의 설문. 사용자의 조직 탭에 있는 대화 상대가 아닌 사용자는 평균 15명입니다. 대화 상대 카드를 보는 작업은 하루에 두 번 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="b521a-185">사용자가 대화를 시작하기 위해 다른 사용자를 클릭할 때마다 하나의 현재 상태 설문(1시간에 평균 한 번)</span><span class="sxs-lookup"><span data-stu-id="b521a-185">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="b521a-p117">시간당 6번의 사용자 검색. 검색이 수행될 때마다 일괄 설문이 검색 결과 목록 내의 모든 사람에게 전송됩니다. 검색 결과의 평균 크기는 20으로 가정됩니다. 검색 결과가 화면에 유지되면 일괄 설문은 5분 간격으로 새로 고쳐집니다. 여기서는 시간당 두 번의 새로 고침이 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="b521a-190">사용자가 Outlook에서 전자 메일을 열거나 미리 볼 때 전자 메일의 받는 사람 및 참조 필드에 있는 사용자의 현재 상태 설문(1시간에 평균 5개의 전자 메일, 전자 메일당 4명의 사용자)</span><span class="sxs-lookup"><span data-stu-id="b521a-190">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-191">현재 상태 구독</span><span class="sxs-lookup"><span data-stu-id="b521a-191">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="b521a-p118">한 사용자가 다른 사용자를 대화 상대로 추가한 경우 첫 번째 사용자는 두 번째 사용자에 대한 5개 정보 범주를 <em>구독</em>할 수 있습니다. 이러한 정보 범주의 업데이트는 첫 번째 사용자에게 자동으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="b521a-194">각 클라이언트의 경우 단일 일괄 구독 요청이 전송되어 평균 대화 상대 40명의 현재 상태를 가져오고 추가적으로 40개의 대화를 통해 페더레이션 대화 상대의 현재 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-194">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="b521a-195">확장된 메일 그룹 구성원의 현재 상태는 폴링이 아닌 영구 현재 상태 구독을 통해 확인되고 각각 2시간마다 사용자당 1번의 확장으로 모델링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-195">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="b521a-p119"><em>단기 구독</em>은 사용자가 로그인하고 모든 사용자의 대화 상대에 대한 일괄 구독이 발생한 후 바로 로그오프한 경우에 발생합니다. 사용자당 1시간에 6번의 단기 구독, 즉 각 구독이 10분간 지속된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-198">현재 상태 게시</span><span class="sxs-lookup"><span data-stu-id="b521a-198">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="b521a-199">현재 상태는 사용자당 1시간에 평균 4회, 최대 6회까지 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-199">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-200">현재 상태 문서 크기</span><span class="sxs-lookup"><span data-stu-id="b521a-200">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="b521a-201">완전한 현재 상태 문서의 평균 크기는 4K, 최대 25K로 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-201">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b521a-202">다음 표에서는 주소록 사용에 대한 사용자 모델을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-202">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="b521a-203">주소록 사용 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-203">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-204">주소록 검색 모드</span><span class="sxs-lookup"><span data-stu-id="b521a-204">Address Book search mode</span></span></th>
<th><span data-ttu-id="b521a-205">Usage</span><span class="sxs-lookup"><span data-stu-id="b521a-205">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-206">주소록 웹 쿼리만(모든 쿼리는 주소록 웹 쿼리 서비스에 의해 수행됨)</span><span class="sxs-lookup"><span data-stu-id="b521a-206">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="b521a-207">사용자당 하루 4번의 접두어 쿼리</span><span class="sxs-lookup"><span data-stu-id="b521a-207">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="b521a-p120">사용자당 하루 60번의 정확한 검색 쿼리. 이 중 40%는 일괄 처리되고(쿼리당 평균 20명의 대화 상대), 나머지 60%는 단일 대화 상대에 대한 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="b521a-p121">사용자당 하루 25번의 사진 쿼리. 24번은 단일 사전에 대한 쿼리이고, 나머지 하나는 평균 20명의 대화 상대에 대한 일괄 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="b521a-213">사용자당 하루에 한 번의 전체 조직 검색 쿼리</span><span class="sxs-lookup"><span data-stu-id="b521a-213">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-p122">혼합 모드(주소록 파일과 사용된 웹 쿼리). 기본 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="b521a-216">두 가지 유형의 쿼리(사진 및 전체 조직 검색 쿼리)만 네트워크로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-216">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="b521a-p123">사용자당 하루 25번의 사진 쿼리. 24번은 단일 사전에 대한 쿼리이고, 나머지 하나는 평균 20명의 대화 상대에 대한 일괄 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="b521a-219">사용자당 하루에 한 번의 전체 조직 검색 쿼리</span><span class="sxs-lookup"><span data-stu-id="b521a-219">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b521a-220">다음 표에서는 회의 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-220">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="b521a-221">회의 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-221">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-222">범주</span><span class="sxs-lookup"><span data-stu-id="b521a-222">Category</span></span></th>
<th><span data-ttu-id="b521a-223">설명</span><span class="sxs-lookup"><span data-stu-id="b521a-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-224">예약 된 모임 및 &quot; 모임 시작 &quot; 모임</span><span class="sxs-lookup"><span data-stu-id="b521a-224">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="b521a-225">60%는 예약, 40%는 비예약</span><span class="sxs-lookup"><span data-stu-id="b521a-225">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="b521a-226">예약된 모임의 경우 80%는 회의(되풀이 회의)에 할당되고, 10%는 1회성 공개 모임, 8%는 1회성 익명 모임, 2%는 1회성 폐쇄형 모임으로 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-226">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-227">회의 클라이언트 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-227">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-228">예약 모임의 경우</span><span class="sxs-lookup"><span data-stu-id="b521a-228">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="b521a-229">65%의 회의 사용자가 Lync 2013을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-229">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="b521a-230">회의 사용자의 5%가 Microsoft Lync Web App을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-230">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="b521a-231">회의 사용자의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 및 Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-231">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="b521a-232">예약되지 않은 모임의 경우</span><span class="sxs-lookup"><span data-stu-id="b521a-232">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="b521a-233">70%의 회의 사용자가 Lync 2013을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-233">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="b521a-234">회의 사용자의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 및 Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-234">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-235">모임 동시성</span><span class="sxs-lookup"><span data-stu-id="b521a-235">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="b521a-p124">사용자의 5%가 근무 시간 중에 회의에 참가합니다. 따라서 80,000명 사용자 풀의 경우 최대 4,000명의 사용자가 동시에 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-238">모임 오디오 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-238">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-239">40%가 VoIP 오디오 및 전화 접속 회의 혼합(VoIP 사용자와 전화 접속 사용자의 비율 3:1)</span><span class="sxs-lookup"><span data-stu-id="b521a-239">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="b521a-240">35%가 VoIP 오디오만 사용</span><span class="sxs-lookup"><span data-stu-id="b521a-240">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="b521a-241">15%가 전화 접속 회의 오디오만 사용</span><span class="sxs-lookup"><span data-stu-id="b521a-241">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="b521a-242">10%가 오디오 사용 안 함(메신저 전용 회의, 사용자당 평균 5개의 메시지 전송)</span><span class="sxs-lookup"><span data-stu-id="b521a-242">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-243">회의의 미디어 혼합</span><span class="sxs-lookup"><span data-stu-id="b521a-243">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="b521a-244">회의의 75%가 웹 회의(오디오 + 다른 공동 작업 형식)</span><span class="sxs-lookup"><span data-stu-id="b521a-244">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="b521a-245">이러한 회의에 사용되는 다른 공동 작업 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-245">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b521a-246">한 회의에서 여러 공동 작업 방법을 사용할 수 있으므로 합계가 100%를 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-246">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="b521a-p125">50%가 응용 프로그램 공유 추가(한 사용자가 보내는 데이터는 초당 최대 1.1MB)</span><span class="sxs-lookup"><span data-stu-id="b521a-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="b521a-249">50%가 메신저 추가(사용자당 평균 2가지의 메신저)</span><span class="sxs-lookup"><span data-stu-id="b521a-249">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="b521a-p126">20%가 데이터 공동 작업 추가(PowerPoint 또는 화이트보드 추가). 이 경우 회의당 평균 2개의 PowerPoint 파일을 발표하고, 포함된 비디오가 없는 경우 평균 PowerPoint 파일 크기는 10MB, 포함된 비디오가 있으면 평균 30MB이며, 화이트보드당 평균 주석 수는 20개입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="b521a-p127">20%가 비디오 추가. 이들 가운데 70%는 여러 보기의 비디오를 사용하며 각 사용자는 2~3개의 비디오 스트림을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="b521a-254">15%가 공유 메모 추가</span><span class="sxs-lookup"><span data-stu-id="b521a-254">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-255">모임 참가자 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-255">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-256">50%는 인증된 내부 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-256">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="b521a-257">25%는 인증된 원격 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-257">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="b521a-258">15%는 익명 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-258">15% anonymous users.</span></span></p>
<p><span data-ttu-id="b521a-259">10%는 페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="b521a-259">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-260">모임 참가 분포</span><span class="sxs-lookup"><span data-stu-id="b521a-260">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="b521a-261">사용자는 처음 5분 이내에 모임에 참가하는 것으로 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-261">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b521a-262">일반 프런트 엔드 풀에서 Lync Server 2013에는 지원 되는 최대 모임 크기인 250 사용자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-262">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="b521a-263">각 풀은 한 번에 하나의 250명 규모 모임을 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-263">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="b521a-264">이 대규모 모임 중에 다른 소규모 회의를 호스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-264">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="b521a-265">추가적으로 이러한 모임을 호스팅하는 전용 풀을 설정하여 최대 1,000명의 사용자를 모임에 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-265">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="b521a-266">자세한 내용은 [Lync Server 2013의 대규모 모임 지원](lync-server-2013-support-for-large-meetings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b521a-266">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="b521a-267">회의가 시뮬레이션된 환경은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-267">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="b521a-268">85%의 회의에 4명의 참가자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-268">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="b521a-269">10%의 회의에 6명의 참가자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-269">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="b521a-270">5%의 회의에 11명의 참가자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-270">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="b521a-271">한 번의 대규모 회의에 250명의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-271">One large conference of 250 users.</span></span>

<span data-ttu-id="b521a-272">다음 표에서는 전화 접속 사용자가 포함된 회의에 대한 사용자 모델의 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-272">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="b521a-273">전화 접속 회의 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-273">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-274">범주</span><span class="sxs-lookup"><span data-stu-id="b521a-274">Category</span></span></th>
<th><span data-ttu-id="b521a-275">설명</span><span class="sxs-lookup"><span data-stu-id="b521a-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-276">인증 됨/익명</span><span class="sxs-lookup"><span data-stu-id="b521a-276">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="b521a-p129">70%의 발신자가 익명으로 참가하고 기록된 이름을 묻는 프롬프트가 나타납니다. 30%는 인증된 사용자로 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-279">통화 시간 및 대기 음악</span><span class="sxs-lookup"><span data-stu-id="b521a-279">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="b521a-280">대기 음악을 제외한 평균 통화 시간: 50초.</span><span class="sxs-lookup"><span data-stu-id="b521a-280">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="b521a-281">전화 접속 사용자의 50%에게 평균 5분간 대기 음악 재생</span><span class="sxs-lookup"><span data-stu-id="b521a-281">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b521a-282">DTMF(Dual-tone Mtifrequency)</span><span class="sxs-lookup"><span data-stu-id="b521a-282">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="b521a-p130">전화 접속 전용 회의의 15%에 전화 리더가 있습니다. 또한 전화 접속 사용자가 포함된 혼합형 회의의 10%에도 전화 리더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="b521a-285">전화 리더의 20%는 회의당 두 가지 DTMF 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-285">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-286">알림 언어</span><span class="sxs-lookup"><span data-stu-id="b521a-286">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="b521a-287">알림 언어로 영어를 사용하여 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-287">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b521a-288">다음 표에서는 회의 대기실 사용자 모델에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-288">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="b521a-289">회의 대기실 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-289">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-290">범주</span><span class="sxs-lookup"><span data-stu-id="b521a-290">Category</span></span></th>
<th><span data-ttu-id="b521a-291">설명</span><span class="sxs-lookup"><span data-stu-id="b521a-291">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-292">대기실의 사용자 수</span><span class="sxs-lookup"><span data-stu-id="b521a-292">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="b521a-293">전화 접속 사용자의 5%와 다른 사용자의 25%가 대기실로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-293">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-294">대기실에서 입장</span><span class="sxs-lookup"><span data-stu-id="b521a-294">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="b521a-295">시뮬레이션에서 클라이언트의 시간이 초과되기 전에 발표자가 모든 사용자의 입장을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-295">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b521a-296">다음 표에서는 다른 피어 투 피어 세션 사용자 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-296">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="b521a-297">피어 투 피어 세션 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-297">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-298">범주</span><span class="sxs-lookup"><span data-stu-id="b521a-298">Category</span></span></th>
<th><span data-ttu-id="b521a-299">설명</span><span class="sxs-lookup"><span data-stu-id="b521a-299">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-300">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="b521a-300">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="b521a-301">각 사용자는 한 달에 5번 피어 투 피어 응용 프로그램 공유 세션에 참가합니다(하루 평균 0.25세션).</span><span class="sxs-lookup"><span data-stu-id="b521a-301">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-302">파일 전송</span><span class="sxs-lookup"><span data-stu-id="b521a-302">File transfer</span></span></p></td>
<td><p><span data-ttu-id="b521a-p131">각 사용자는 한 달에 한 번 메신저 세션의 일부로 피어 투 피어 파일 전송 세션에 참가합니다(하루 평균 0.05 세션). 세션에서 전송되는 평균 파일 크기는 1MB입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b521a-305">다음 표에서는 정책에 대한 사용자 모델을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-305">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="b521a-306">정책 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="b521a-306">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b521a-307">범주</span><span class="sxs-lookup"><span data-stu-id="b521a-307">Category</span></span></th>
<th><span data-ttu-id="b521a-308">설명</span><span class="sxs-lookup"><span data-stu-id="b521a-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b521a-309">회의, 현재 상태 및 보관 정책</span><span class="sxs-lookup"><span data-stu-id="b521a-309">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="b521a-310">1개의 전역 정책, 10개의 태그 전화 회의 정책, 4개의 보관 정책 및 10개의 태그 현재 상태 정책이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-310">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b521a-311">음성 정책</span><span class="sxs-lookup"><span data-stu-id="b521a-311">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="b521a-312">사이트당 1개의 전역 정책과 2개의 태그 정책이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-312">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="b521a-313">100%의 사이트에 사이트 정책이 있고 30%의 사용자에게 사용자별 정책이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-313">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="b521a-314">사이트당 하나의 다이얼 플랜 및 사이트당 두 개의 경로가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-314">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="b521a-315">사용량이 많은 시간</span><span class="sxs-lookup"><span data-stu-id="b521a-315">Busy Hour</span></span>

<span data-ttu-id="b521a-p133">피어 투 피어 세션의 경우 BHCA(Busy Hour Call Attempts)를 사용하여 최대 부하를 계산합니다. 이 음성 산업 용어는 하루 총 통화의 50%가 20% 시간 내에 완료되는 것으로 가정합니다. 이는 다음 수식을 통해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="b521a-319">성능 테스트를 통해 하루 1.6시간 이상의 사용량이 많은 시간에 VoIP와 다른 피어 투 피어 세션을 실행하여 사용량이 많은 시간을 시뮬레이션했습니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-319">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="b521a-p134">회의 최대 부하는 하루 8시간 동안 이루어지는 모든 회의의 75%가 4시간의 피크 시간 동안 발생하는 것으로 가정합니다. 이러한 피크 시간의 부하는 평균 회의 부하의 1.5배입니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="b521a-322">Enterprise Voice to PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="b521a-322">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="b521a-323">Enterprise Voice 통화에는 다음과 같은 가정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-323">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="b521a-324">사용자의 50%가 Enterprise Voice를 사용 하도록 설정 되었으며, 이러한 사용자의 60%는 PSTN 통화에 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-324">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="b521a-p135">PSTN 통화를 사용하는 개별 사용자는 사용량이 많은 시간에 4번의 PSTN 통화를 하고 각 통화는 3분간 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="b521a-327">PSTN 음성 통화의 65%가 미디어 바이패스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-327">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="b521a-328">이동성</span><span class="sxs-lookup"><span data-stu-id="b521a-328">Mobility</span></span>

<span data-ttu-id="b521a-p136">40%의 등록된 사용자에게 모바일 기능이 허용되는 것으로 가정합니다. 모바일 기능을 사용하는 각 사용자의 경우 모바일 클라이언트의 작업이 해당 사용자의 다른 MPOP 인스턴스의 작업에 추가됩니다. 단, 모바일 클라이언트가 회의 상호 작용을 위해 회의 참가에 사용되는 또 다른 유형의 클라이언트인 경우는 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="b521a-331">영구 채팅</span><span class="sxs-lookup"><span data-stu-id="b521a-331">Persistent Chat</span></span>

<span data-ttu-id="b521a-332">등록된 사용자의 25%가 다음과 같은 특징으로 영구 채팅 세션에 연관된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-332">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="b521a-333">사용자당 평균 1.5개의 채팅방</span><span class="sxs-lookup"><span data-stu-id="b521a-333">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="b521a-334">각 채팅방에는 시간당 평균 10명의 사용자를 대상으로 하는 12개의 설문 조사 요청이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-334">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="b521a-335">응답 그룹 및 통화 대기</span><span class="sxs-lookup"><span data-stu-id="b521a-335">Response Group and Call Park</span></span>

<span data-ttu-id="b521a-p137">등록된 사용자의 0.15%가 응답 그룹에 속하고, 등록된 사용자의 0.02%가 지정한 시점에 통화 대기 상태인 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b521a-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

