---
title: 'Lync Server 2013: 사용자 모델'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8185fc2fdb92f907eb013349b8a202df2b7b62bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="23554-102">Lync Server 2013의 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23554-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="23554-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="23554-104">여기에 설명 된 사용자 모델은 [사용자 모델을 사용 하 여 Lync Server 2013의 용량 계획](lync-server-2013-capacity-planning-using-the-user-models.md)에 설명 된 용량 계획 측정값 및 권장 사항에 대 한 기반을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="23554-105">Lync Server 2013 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="23554-106">다음 표에서는 Lync Server 2013의 등록, 연락처, 인스턴트 메시징 (IM) 및 현재 상태에 대 한 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="23554-107">환경 및 등록 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-108">범주만</span><span class="sxs-lookup"><span data-stu-id="23554-108">Category</span></span></th>
<th><span data-ttu-id="23554-109">설명</span><span class="sxs-lookup"><span data-stu-id="23554-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-110">배포 크기 및 배포</span><span class="sxs-lookup"><span data-stu-id="23554-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-111">사이트 당 하나의 프런트 엔드 풀을 사용 하 여 세 개의 중앙 사이트를 사용 하는 대규모 배포를 모델링 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-112">Active Directory 사용자의 백분율</span><span class="sxs-lookup"><span data-stu-id="23554-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="23554-113">조직의 모든 Active Directory 사용자의 70%가 Lync Server에 대해 사용 하도록 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="23554-114">이 사용 가능한 사용자의 80%가 하루 종일 Lync Server에 로그온 되어 있습니다 (80% 병행성).</span><span class="sxs-lookup"><span data-stu-id="23554-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="23554-115">동시 사용자는이 섹션의 나머지 부분에 있는 숫자를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-116">Active Directory 변경 내용</span><span class="sxs-lookup"><span data-stu-id="23554-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="23554-117">모든 사용자의 0.5%가 매주 Active Directory에서 Lync에 만들어지고 사용 하도록 설정 되었고, 모든 사용자의 0.5%는 Active Directory 및 매 주마다 Lync에서 사용 하지 않도록 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="23554-118">사용자의 5%는 매주 1 개 이상의 Active Directory 특성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-119">Active Directory 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="23554-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="23554-120">조직의 Active Directory 메일 그룹 수가 Active Directory의 모든 사용자 수의 3 배가 되는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-120">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory.</span></span> <span data-ttu-id="23554-121">메일 그룹의 크기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-121">The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="23554-122">64%에 2-30 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="23554-123">13%에 31-50 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="23554-124">10%에 51-100 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="23554-125">13%에 101-500 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-126">VoIP (Voice over IP) 사용자</span><span class="sxs-lookup"><span data-stu-id="23554-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="23554-127">Lync Server 사용자의 60%는 통합 커뮤니케이션 (UC)에 사용할 수 있습니다 (즉, 전화 번호는 Lync Server에서 소유).</span><span class="sxs-lookup"><span data-stu-id="23554-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-128">등록 된 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="23554-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-129">클라이언트의 65%는 Lync 및 Lync Phone 버전을 포함 하 여 Lync 2013 소프트웨어를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="23554-130">이전 버전의 Lync에서 클라이언트 소프트웨어를 실행 하는 클라이언트의 30%</span><span class="sxs-lookup"><span data-stu-id="23554-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="23554-131">Lync Web App을 사용 하는 클라이언트의 5%</span><span class="sxs-lookup"><span data-stu-id="23554-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="23554-132">이동성을 사용 하도록 설정한 경우 사용자의 40%가 이전에 인용 된 다른 클라이언트 옵션과 동시에 이동성을 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="23554-133">이 경우 클라이언트는 MPOP (다중 시점) 비율이 1:1.9입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="23554-134">이동성을 사용 하지 않도록 설정한 경우 MPOP 비율은 1:1.5입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-135">원격 사용자 배포</span><span class="sxs-lookup"><span data-stu-id="23554-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-136">내부적으로 연결 하는 사용자의 70%입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="23554-137">Edge 서버 및 디렉터를 통해 연결 되는 사용자의 30%</span><span class="sxs-lookup"><span data-stu-id="23554-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-138">연락처 배포</span><span class="sxs-lookup"><span data-stu-id="23554-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-139">사용자에 게 표시 되는 최대 연락처 수는 1000입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-139">The maximum number of contacts a user has is 1,000.</span></span> <span data-ttu-id="23554-140">1% 미만의 사용자가 1000 연락처를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-140">Less than 1% of users have 1,000 contacts.</span></span> <span data-ttu-id="23554-141">사용자 중 25% 미만의 연락처가 100 개 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-141">Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="23554-142">공용 클라우드 연결이 있는 사용자에 대 한 80 연락처의 평균입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-142">Average of 80 contacts for users with public cloud connectivity.</span></span> <span data-ttu-id="23554-143">다음 사용자:</span><span class="sxs-lookup"><span data-stu-id="23554-143">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="23554-144">50%의 연락처가 조직 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-144">50% of the contacts are within the organization.</span></span> <span data-ttu-id="23554-145">이러한 사용자의 10%는 원격 사용자로 방화벽 외부에서 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-145">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="23554-146">연락처의 40%는 공용 클라우드 사용자 (AOL, Yahoo!, MSN 또는 Google 대화 사용자 등)입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="23554-147">연락처의 10%는 페더레이션 파트너에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="23554-148">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="23554-149">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="23554-150">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="23554-151">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="23554-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="23554-152">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-152">has been announced.</span></span> <span data-ttu-id="23554-153">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23554-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="23554-154">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="23554-155">받으려면.</span><span class="sxs-lookup"><span data-stu-id="23554-155">Messenger.</span></span> <span data-ttu-id="23554-156">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="23554-157">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="23554-158">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="23554-159">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="23554-160">공용 클라우드 연결이 없는 사용자에 대 한 50 연락처의 평균입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-160">Average of 50 contacts for users without public cloud connectivity.</span></span> <span data-ttu-id="23554-161">다음 사용자:</span><span class="sxs-lookup"><span data-stu-id="23554-161">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="23554-162">80%의 연락처가 조직 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-162">80% of the contacts are within the organization.</span></span> <span data-ttu-id="23554-163">이러한 사용자의 10%는 원격 사용자로 방화벽 외부에서 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-163">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="23554-164">페더레이션 파트너는 연락처의 20%를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="23554-165">각 사용자의 연락처 목록에는 1 개의 메일 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-165">Each user has 1 distribution group in their contact list.</span></span> <span data-ttu-id="23554-166">성능 테스트를 위해 메일 그룹이 항상 확장 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-166">For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="23554-167">사용자의 연락처 중 25%는 XMPP를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-168">세션 시간</span><span class="sxs-lookup"><span data-stu-id="23554-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="23554-169">평균 사용자 로그온 세션은 12 시간 동안 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-169">The average user logon session lasts 12 hours.</span></span> <span data-ttu-id="23554-170">모든 사용자가 세션 시작 시 120 분 내에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-170">All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="23554-171">IM 및 현재 상태 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-172">범주만</span><span class="sxs-lookup"><span data-stu-id="23554-172">Category</span></span></th>
<th><span data-ttu-id="23554-173">설명</span><span class="sxs-lookup"><span data-stu-id="23554-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-174">피어 투 피어 IM 세션</span><span class="sxs-lookup"><span data-stu-id="23554-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="23554-175">각 사용자는 하루에 6 개의 피어 투 피어 IM 세션 평균을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="23554-176">세션 당 10 개의 인스턴트 메시지.</span><span class="sxs-lookup"><span data-stu-id="23554-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="23554-177">각 메시지는 두 개의 SIP 정보 메시지와 ""&lt;이름&gt; 입력 "과 같은 상태 표시기 용 2 sip 200 OK 메시지와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-178">현재 상태 폴링</span><span class="sxs-lookup"><span data-stu-id="23554-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="23554-179">전반적으로 시간 당 사용자 당 평균 60 폴링에 대 한 현재 상태 폴링을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-179">Overall, we assume presence polling at an average of 60 polls per user per hour.</span></span> <span data-ttu-id="23554-180">각 사용자에 대해 다음 평균을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-180">For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="23554-181">사용자의 조직 탭에 있는 사용자의 하루에 한 번의 폴링 (대화 상대 목록 제외)</span><span class="sxs-lookup"><span data-stu-id="23554-181">One poll per day of the presence of users in the user’s organization tab (but not Contacts list).</span></span> <span data-ttu-id="23554-182">사용자의 조직 탭에 있는 연락처가 아닌 평균 수는 사용자 15 명입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-182">Average number of non-contacts in the user’s organization tab is 15 users.</span></span> <span data-ttu-id="23554-183">1 일에 두 개의 대화 상대 카드 보기 작업</span><span class="sxs-lookup"><span data-stu-id="23554-183">Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="23554-184">사용자가 다른 사용자를 클릭 하 여 대화를 시작할 때마다 한 번의 현재 상태 폴링으로 시간 당 한 번씩 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="23554-185">시간 당 6 명의 사용자 검색.</span><span class="sxs-lookup"><span data-stu-id="23554-185">Six user searches per hour.</span></span> <span data-ttu-id="23554-186">검색을 수행할 때마다 검색 결과 목록의 모든 사용자에 대해 일괄 처리 폴링이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-186">Every time a search is performed, a batch poll is sent for everyone in the search result list.</span></span> <span data-ttu-id="23554-187">검색 결과의 평균 크기는 20으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-187">We assume the average size of search results is 20.</span></span> <span data-ttu-id="23554-188">검색 결과가 화면에 남아 있는 경우 일괄 처리 설문은 5 분 마다 새로 고쳐집니다. 이번에는 시간 당 두 가지 그러한 새로 고침이 있을 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-188">If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="23554-189">사용자가 Outlook에서 전자 메일을 열거나 미리 볼 때 전자 메일의 받는 사람: 및 CC: 필드에 사용자가 있는 경우와 전자 메일 당 최대 4 명의 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-190">현재 상태 구독</span><span class="sxs-lookup"><span data-stu-id="23554-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="23554-191">사용자 중 한 명에 게 연락처를 추가 하는 경우 첫 번째 사용자는 두 번째 사용자에 대 한 다섯 가지 범주의 정보를 <em>구독</em> 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-191">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user.</span></span> <span data-ttu-id="23554-192">이러한 범주의 정보에 대 한 업데이트는 자동으로 첫 번째 사용자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-192">Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="23554-193">각 클라이언트에 대해 단일 일괄 처리 요청을 전송 하 여 평균 40 연락처의 현재 상태를 얻고 추가 40 대화 상자를 사용 하 여 페더레이션 대화 상대에 대 한 상태를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="23554-194">확장 된 메일 그룹의 구성원에 대 한 현재 상태는 폴링이 아닌 영구 현재 상태 구독을 통해 검색 되며 각 2 시간 동안 사용자 당 하나의 확장으로 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="23554-195"><em>짧은</em> 플랜 사용자가 로그인 하면 모든 사용자의 연락처에 대 한 일괄 구독이 있는 경우 사용자가 곧 로그 오프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-195"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off.</span></span> <span data-ttu-id="23554-196">각 구독이 10 분 후에 시간 당 6 개의 짧은 구독이 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-196">We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-197">현재 상태 게시</span><span class="sxs-lookup"><span data-stu-id="23554-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="23554-198">현재 상태는 시간당 사용자 당 최대 4 개의 출판물에 게시 됩니다 (시간당 사용자 당 최고 6 개).</span><span class="sxs-lookup"><span data-stu-id="23554-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-199">현재 상태 문서 크기</span><span class="sxs-lookup"><span data-stu-id="23554-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="23554-200">전체 현재 상태 문서의 평균 크기는 최대 25K의 4K로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23554-201">다음 표에서는 주소록 사용에 대 한 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="23554-202">주소록 사용 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-203">주소록 검색 모드</span><span class="sxs-lookup"><span data-stu-id="23554-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="23554-204">용도</span><span class="sxs-lookup"><span data-stu-id="23554-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-205">주소록 웹 쿼리 전용 (주소록 웹 쿼리 서비스를 통해 수행 되는 모든 쿼리)</span><span class="sxs-lookup"><span data-stu-id="23554-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="23554-206">일일 사용자 당 4 개의 접두 번호 쿼리.</span><span class="sxs-lookup"><span data-stu-id="23554-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="23554-207">60 사용자 당 정확한 검색 쿼리.</span><span class="sxs-lookup"><span data-stu-id="23554-207">60 exact search queries per user per day.</span></span> <span data-ttu-id="23554-208">쿼리 당 평균 20 개의 연락처가 있는 일괄 처리 된 40%가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-208">40% of those are batched, with an average of 20 contacts per query.</span></span> <span data-ttu-id="23554-209">쿼리의 다른 60%는 단일 연락처에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-209">The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="23554-210">일일 사용자 당 25 개의 사진 쿼리.</span><span class="sxs-lookup"><span data-stu-id="23554-210">25 photo queries per user per day.</span></span> <span data-ttu-id="23554-211">24는 단일 사진에 대 한 것이 고, 다른 하나는 평균 20 개의 연락처를 포함 하는 일괄 처리 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-211">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="23554-212">일일 사용자 당 총 조직 검색 쿼리 1 개.</span><span class="sxs-lookup"><span data-stu-id="23554-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-213">주소록 파일과 웹 쿼리를 모두 사용 하는 혼합 모드</span><span class="sxs-lookup"><span data-stu-id="23554-213">Mixed mode, both address book file and web queries used.</span></span> <span data-ttu-id="23554-214">기본 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-214">This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="23554-215">두 가지 유형의 쿼리만 네트워크, 사진 및 총 조직 검색 쿼리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="23554-216">일일 사용자 당 25 개의 사진 쿼리.</span><span class="sxs-lookup"><span data-stu-id="23554-216">25 photo queries per user per day.</span></span> <span data-ttu-id="23554-217">24는 단일 사진에 대 한 것이 고, 다른 하나는 평균 20 개의 연락처를 포함 하는 일괄 처리 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-217">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="23554-218">일일 사용자 당 총 조직 검색 쿼리 1 개.</span><span class="sxs-lookup"><span data-stu-id="23554-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23554-219">다음 표에서는 회의 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="23554-220">회의 모델</span><span class="sxs-lookup"><span data-stu-id="23554-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-221">범주만</span><span class="sxs-lookup"><span data-stu-id="23554-221">Category</span></span></th>
<th><span data-ttu-id="23554-222">설명</span><span class="sxs-lookup"><span data-stu-id="23554-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-223">예약 된 모임 &quot;과 모임&quot; 시작 모임 비교</span><span class="sxs-lookup"><span data-stu-id="23554-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="23554-224">60%의 예정, 40%가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="23554-225">예약 된 모임의 경우 80%에 회의 회의가 있는 것으로 간주 됩니다. 10%는 일회성 열려 있는 모임입니다. 8%는 일회성 익명 모임이 며 2%는 일회성으로 닫힌 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-226">회의 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="23554-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-227">예약 된 모임의 경우:</span><span class="sxs-lookup"><span data-stu-id="23554-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="23554-228">회의 사용자의 65%는 Lync 2013를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="23554-229">회의 사용자의 5%는 Microsoft Lync Web App을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="23554-230">회의의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="23554-231">예정 되지 않은 모임의 경우:</span><span class="sxs-lookup"><span data-stu-id="23554-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="23554-232">회의 사용자의 70%는 Lync 2013를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="23554-233">회의의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-234">모임 동시성</span><span class="sxs-lookup"><span data-stu-id="23554-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="23554-235">사용자의 5%는 근무 시간 동안 회의에 참여 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-235">5% of users will be in conferences during working hours.</span></span> <span data-ttu-id="23554-236">따라서 8만 사용자 풀에서 4000 사용자는 언제 든 지 회의에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-236">Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-237">모임 오디오 배포</span><span class="sxs-lookup"><span data-stu-id="23554-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-238">40% 혼합 VoIP 오디오 및 전화 접속 회의, 그리고 전화 접속 사용자를 위한 VoIP 사용자의 3:1 비율.</span><span class="sxs-lookup"><span data-stu-id="23554-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="23554-239">35% VoIP 오디오만.</span><span class="sxs-lookup"><span data-stu-id="23554-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="23554-240">15% 전화 접속 회의 오디오만</span><span class="sxs-lookup"><span data-stu-id="23554-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="23554-241">10% 오디오 없음 (IM 전용 회의, 사용자 당 평균 5 개의 메시지가 전송 됨).</span><span class="sxs-lookup"><span data-stu-id="23554-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-242">회의를 위한 미디어 조합</span><span class="sxs-lookup"><span data-stu-id="23554-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="23554-243">회의의 75%는 오디오와 다른 공동 작업 형식을 포함 하는 웹 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="23554-244">이러한 컨퍼런스에 대 한 다른 공동 작업 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="23554-245">이러한 수치는 하나의 회의에 여러 공동 작업 방법이 있을 수 있으므로 100% 이상을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="23554-246">50% 응용 프로그램 공유 추가</span><span class="sxs-lookup"><span data-stu-id="23554-246">50% add application sharing.</span></span> <span data-ttu-id="23554-247">한 명의 사용자가 초당 최대 1.1 MB의 데이터를 전송 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-247">We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="23554-248">50% 인스턴트 메시지 추가 (사용자 당 평균 2 개의 메시지)</span><span class="sxs-lookup"><span data-stu-id="23554-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="23554-249">20% 이러한 데이터 공동 작업 (예: PowerPoint 또는 화이트 보드 포함)을 추가 하면 각 회의에 대해 표시 되는 평균 2 개의 PowerPoint 파일, 최대 PowerPoint 파일 크기: 10 MB (임베디드 비디오 제외) 또는 30mb (포함 된 비디오 사용)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-249">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video).</span></span> <span data-ttu-id="23554-250">화이트 보드 당 평균 20 개의 주석</span><span class="sxs-lookup"><span data-stu-id="23554-250">Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="23554-251">20% 영상 추가.</span><span class="sxs-lookup"><span data-stu-id="23554-251">20% add video.</span></span> <span data-ttu-id="23554-252">이러한 사용자 중 70%는 각 사용자가 2-3 비디오 스트림을 수신 하는 multiview 비디오에 대해 회의에 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-252">Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="23554-253">15% 공유 메모 추가</span><span class="sxs-lookup"><span data-stu-id="23554-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-254">모임 참가자 배포</span><span class="sxs-lookup"><span data-stu-id="23554-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-255">50% 내부 인증 된 사용자</span><span class="sxs-lookup"><span data-stu-id="23554-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="23554-256">인증 된 사용자 인 25% 원격 액세스</span><span class="sxs-lookup"><span data-stu-id="23554-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="23554-257">15% 익명 사용자.</span><span class="sxs-lookup"><span data-stu-id="23554-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="23554-258">10% 페더레이션 사용자.</span><span class="sxs-lookup"><span data-stu-id="23554-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-259">모임 참가 배포</span><span class="sxs-lookup"><span data-stu-id="23554-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="23554-260">사용자는 처음 5 분 내에 모임에 참가 하는 것으로 시뮬레이션 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23554-261">일반 프런트 엔드 풀에서 Lync Server 2013에는 지원 되는 최대 모임 크기 (250 사용자)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="23554-262">각 풀은 한 번에 1 250 사용자 모임을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="23554-263">이 대규모 모임이 진행 되는 동안에는 풀이 다른 작은 회의를 호스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="23554-264">또한이 모임을 호스팅하도록 전용 풀을 설정 하 여 최대 1000 사용자의 모임을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="23554-265">자세한 내용은 [Lync Server 2013의 대규모 모임 지원을](lync-server-2013-support-for-large-meetings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23554-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="23554-266">회의는 다음과 같이 시뮬레이트할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="23554-267">회의의 85%는 참가자가 네 명 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="23554-268">회의의 10%는 참가자가 6 명 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="23554-269">회의의 5%는 참가자가 11 명 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="23554-270">250 사용자 1 명으로 이루어진 대용량 회의.</span><span class="sxs-lookup"><span data-stu-id="23554-270">One large conference of 250 users.</span></span>

<span data-ttu-id="23554-271">다음 표에서는 전화 접속 사용자와 관련 된 사용자 모델에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="23554-272">전화 접속 회의 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-273">범주만</span><span class="sxs-lookup"><span data-stu-id="23554-273">Category</span></span></th>
<th><span data-ttu-id="23554-274">설명</span><span class="sxs-lookup"><span data-stu-id="23554-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-275">인증 됨/익명</span><span class="sxs-lookup"><span data-stu-id="23554-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="23554-276">발신자의 70%는 익명으로 참가 하 고 기록 된 이름을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-276">70% of callers join as anonymous and are prompted for a recorded name.</span></span> <span data-ttu-id="23554-277">인증 된 사용자로 30% 참가.</span><span class="sxs-lookup"><span data-stu-id="23554-277">30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-278">통화 시간 및 음악 보류</span><span class="sxs-lookup"><span data-stu-id="23554-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="23554-279">음악을 보유 하지 않은 평균 통화 시간: 50 초.</span><span class="sxs-lookup"><span data-stu-id="23554-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="23554-280">통화 사용자의 50%는 평균적으로 5 분 동안 대기 음악을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23554-281">Multifrequency (DTMF)</span><span class="sxs-lookup"><span data-stu-id="23554-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="23554-282">전화 접속 인 회의의 15%는 전화 선도 지역에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-282">15% of conferences that are dial-in only have phone leaders.</span></span> <span data-ttu-id="23554-283">전화 접속 사용자를 포함 하는 혼합 컨퍼런스 10%에도 전화 리더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-283">10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="23554-284">전화 리더의 20%는 각 회의에 대해 DTMF 명령 2 개를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-285">알림 언어</span><span class="sxs-lookup"><span data-stu-id="23554-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="23554-286">시뮬레이션에서는 영어를 공지 사항 언어로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23554-287">다음 표에서는 컨퍼런스 로비 사용자 모델에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="23554-288">컨퍼런스 대기실 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-289">범주만</span><span class="sxs-lookup"><span data-stu-id="23554-289">Category</span></span></th>
<th><span data-ttu-id="23554-290">설명</span><span class="sxs-lookup"><span data-stu-id="23554-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-291">대기실에 있는 사용자 수</span><span class="sxs-lookup"><span data-stu-id="23554-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="23554-292">전화 접속 사용자의 5%는 대기실에서 진행 되며, 다른 사용자의 25%는 대기실를 통해 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-293">대기실에서 Admitting</span><span class="sxs-lookup"><span data-stu-id="23554-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="23554-294">시뮬레이션에서 클라이언트 제한 시간 전에 발표자가 모든 사용자를 허가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23554-295">다음 표에서는 다른 피어 투 피어 세션의 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="23554-296">피어 투 피어 세션 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-297">범주만</span><span class="sxs-lookup"><span data-stu-id="23554-297">Category</span></span></th>
<th><span data-ttu-id="23554-298">설명</span><span class="sxs-lookup"><span data-stu-id="23554-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-299">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="23554-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="23554-300">각 사용자는 일일 5 개 피어 투 피어 응용 프로그램 공유 세션에 참여 합니다 (일별 평균 0.25 세션).</span><span class="sxs-lookup"><span data-stu-id="23554-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-301">파일 전송</span><span class="sxs-lookup"><span data-stu-id="23554-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="23554-302">각 사용자는 하루에 평균 0.05 세션에 대해 1 개월 피어 투 피어 파일 전송 세션 (IM 세션의 일부로)에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-302">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day.</span></span> <span data-ttu-id="23554-303">전송 되는 평균 세션 파일 크기는 1mb입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-303">The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23554-304">다음 표에서는 정책에 대 한 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="23554-305">정책 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="23554-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23554-306">범주만</span><span class="sxs-lookup"><span data-stu-id="23554-306">Category</span></span></th>
<th><span data-ttu-id="23554-307">설명</span><span class="sxs-lookup"><span data-stu-id="23554-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23554-308">회의, 현재 상태 및 보관 정책</span><span class="sxs-lookup"><span data-stu-id="23554-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="23554-309">글로벌 정책, 10 개의 태그 회의 정책, 보관 정책 4 개, 태그 현재 상태 정책 1 개가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23554-310">음성 정책</span><span class="sxs-lookup"><span data-stu-id="23554-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="23554-311">사이트 마다 하나의 글로벌 정책 및 2 개의 태그 정책이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="23554-312">사이트의 100%에는 사이트 정책이 있으며 사용자의 30%에는 사용자 별 정책이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="23554-313">사이트별로 하나의 다이얼 플랜을 만들고 각 사이트에는 두 개의 경로를 계획 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="23554-314">통화 시간</span><span class="sxs-lookup"><span data-stu-id="23554-314">Busy Hour</span></span>

<span data-ttu-id="23554-315">피어 투 피어 세션의 경우 사용량이 많은 시간 (BHCA)을 사용 하 여 최대 로드가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-315">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA).</span></span> <span data-ttu-id="23554-316">이 음성 산업 약관은 하루 종일 통화의 50%가 20% 동안 완료 된다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-316">This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time.</span></span> <span data-ttu-id="23554-317">다음 수식을 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-317">It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="23554-318">일일 최소 1.6 시간 동안 바쁜 시간에 VoIP 및 기타 피어 투 피어 세션을 실행 하 여 시간을 시뮬레이션 한 성능 테스트.</span><span class="sxs-lookup"><span data-stu-id="23554-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="23554-319">회의 최고 로드는 하루에 모든 컨퍼런스의 75%가 최대 4 시간 동안 발생 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-319">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours.</span></span> <span data-ttu-id="23554-320">이러한 피크 시간은 평균 회의 부하의 1.5 배입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-320">Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="23554-321">엔터프라이즈 음성 ~ PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="23554-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="23554-322">엔터프라이즈 음성 통화에는 다음과 같은 가정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="23554-323">사용자의 50%가 엔터프라이즈 음성에 대해 사용 하도록 설정 되어 있으며 이러한 사용자의 60%는 PSTN 통화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23554-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="23554-324">PSTN 통화에 대해 사용 하도록 설정 된 이러한 각 사용자는 바쁜 시간 동안 4 개의 PSTN 통화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-324">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour.</span></span> <span data-ttu-id="23554-325">각 통화 기간은 3 분입니다.</span><span class="sxs-lookup"><span data-stu-id="23554-325">Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="23554-326">이 PSTN 음성 통화의 65%는 미디어 바이패스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="23554-327">이동성</span><span class="sxs-lookup"><span data-stu-id="23554-327">Mobility</span></span>

<span data-ttu-id="23554-328">등록 된 사용자의 40%는 이동성을 사용할 수 있는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-328">40% of registered users are assumed to be enabled for Mobility.</span></span> <span data-ttu-id="23554-329">이동성을 사용 하는 각 사용자에 대해 모바일 클라이언트의 활동은 해당 사용자에 대 한 다른 MPOP 인스턴스를 추가 하는 것으로 간주 되며,이는 이동성 클라이언트가 다른 클라이언트 유형으로 서만 사용할 수 있는 것으로 서, 회의 조작의 예외입니다. 회의에 참여 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23554-329">For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="23554-330">영구 채팅</span><span class="sxs-lookup"><span data-stu-id="23554-330">Persistent Chat</span></span>

<span data-ttu-id="23554-331">등록 된 사용자 중 25%가 영구 채팅 세션에 포함 되는 경우 다음 특성을 사용 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="23554-332">사용자 당 평균 1.5 채팅 채팅방</span><span class="sxs-lookup"><span data-stu-id="23554-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="23554-333">각 채팅방은 평균 10 명의 사용자를 대상으로 하 여 시간당 12 회 폴링 요청을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="23554-334">응답 그룹 및 통화 공원</span><span class="sxs-lookup"><span data-stu-id="23554-334">Response Group and Call Park</span></span>

<span data-ttu-id="23554-335">등록 된 사용자의 0.15%가 응답 그룹에 속해 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-335">We assume that 0.15% of registered users belong to response groups.</span></span> <span data-ttu-id="23554-336">사용자의 0.02%가 지정 된 시점에 대기 중인 통화를 보유 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23554-336">We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

