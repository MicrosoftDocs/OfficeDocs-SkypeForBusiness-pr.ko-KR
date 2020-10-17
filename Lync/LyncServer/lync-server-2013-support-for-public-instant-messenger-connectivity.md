---
title: 공용 인스턴트 메신저 연결에 대 한 Lync Server 2013 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ad9f5083d336fdf90e415d627fe448d02e4db29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519425"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="88e7d-102">Lync Server 2013의 공용 인스턴트 메신저 연결 지원</span><span class="sxs-lookup"><span data-stu-id="88e7d-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e7d-103">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="88e7d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="88e7d-104">공용 인스턴트 메신저 연결 지원</span><span class="sxs-lookup"><span data-stu-id="88e7d-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="88e7d-105">이 문서에서는 공용 IM 연결 (PIC) 지원에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="88e7d-106">PIC는 조직의 lync 사용자가 Lync 클라이언트 및 id를 통해 특정 공용 IM (인스턴트 메시징) 서비스 사용자와 연결할 수 있도록 허용 하는 Microsoft Lync의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="88e7d-107">최종 사용자는 해당 조항에 따라 고객, 파트너 및 공급 업체와의 연결을 통해 혜택을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="88e7d-108">Lync의 제어, 준수 및 보관 기능을 유지 하는 동시에 단일 실시간 통신 클라이언트를 지 원하는 것이 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="88e7d-109">5 [월 2013에 공개적으로 제공](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)되는 Lync-Skype 연결에서는 MSN/Windows LIVE, AOL 및 Yahoo에 연결 하기 위해 처음에 Lync/Office communications SERVER (OCS)/Live Communications SERVER (LCS)를 설정 하는 이전 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-109">Lync-Skype connectivity, [publicly available in May 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="88e7d-110">Lync-Skype 연결에 대 한 자세한 내용은 [Lync-Skype 연결](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="88e7d-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="88e7d-111">Windows Live, AOL 및 Yahoo와의 페더레이션은 각각 수명 종료에 대 한 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="88e7d-112">이 페이지에서는 각 서비스의 상태를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="88e7d-113">PIC를 사용 하려면 고객이 각 공용 IM 서비스 공급자에 대해 서비스를 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="88e7d-114">이 작업을 수행 하는 방법에 대 한 요구 사항 및 세부 정보는 IM 서비스 공급자 및 고객의 기본 라이선스 프로그램에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="88e7d-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="88e7d-115">Windows Live Messenger</span></span>

<span data-ttu-id="88e7d-116">Microsoft는 Windows Live Messenger 및 Skype를 함께 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="88e7d-117">2013 년 4 월에 메신저 사용자는 로그인 시 Skype로 마이그레이션 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="88e7d-118">Messenger와의 페더레이션을 사용 하는 Lync 고객은 해당 연락처를 Skype로 업데이트 한 후에도 해당 연락처와 계속 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="88e7d-119">Lync 관리자 또는 Lync 최종 사용자는 서비스 연속성을 유지 관리 하기 위해 수행 해야 하는 것은 없으며 Lync 내에서이 기능을 관리 하는 것은 Messenger와의 통신에 대 한 것과 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="88e7d-120">메신저 사용자가 Microsoft 계정을 사용 하 여 Skype에 로그인 하는 경우 (예: Messenger에 사용 되는 것과 동일한 자격 증명) 모든 Messenger 연락처 (페더레이션 Lync 대화 상대 포함)를 Skype로 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="88e7d-121">이러한 연락처에 대해 Skype 및 Lync 간의 현재 상태 공유 및 인스턴트 메시징을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="88e7d-122">Lync-Skype 연결-이제 모든 Lync 고객은 연락처 추가, 현재 상태 공유, 인스턴트 메시징 및 Lync 및 Skype 사용자 간의 음성 통화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="88e7d-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="88e7d-123">Yahoo\!</span></span> <span data-ttu-id="88e7d-124">및 AOL 인스턴트 메신저</span><span class="sxs-lookup"><span data-stu-id="88e7d-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="88e7d-125">Yahoo와의 페더레이션\!</span><span class="sxs-lookup"><span data-stu-id="88e7d-125">Federation with Yahoo\!</span></span> <span data-ttu-id="88e7d-126">그리고 AOL은 Lync (및 Office Communications Server)의 고객을 위한 수명 종료에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="88e7d-127">이러한 각 서비스를 제공 하는 Microsoft의 기능은 Yahoo에서 지원 됩니다.\!</span><span class="sxs-lookup"><span data-stu-id="88e7d-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="88e7d-128">이에 대 한 기본 규약 및 AOL은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="88e7d-129">두 Yahoo에 대해\!</span><span class="sxs-lookup"><span data-stu-id="88e7d-129">For both Yahoo\!</span></span> <span data-ttu-id="88e7d-130">또한 서비스는 6 월 2014까지 계속 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="88e7d-131">**Yahoo** -서비스는 6 월 2014까지 계속 되며, 고객은 Microsoft LYNC 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 사용 하 여 라이선스를 계속 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="88e7d-132">9 월 1 일, 2012, PIC USL을 더 이상 신규 또는 갱신 계약에 대 한 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="88e7d-133">이 날짜 이전에 라이선스를 구입한 고객은 계속 Yahoo에 페더레이션 할 수 있습니다.\!</span><span class="sxs-lookup"><span data-stu-id="88e7d-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="88e7d-134">이전 서비스 종료 날짜 또는 라이선스 만료까지</span><span class="sxs-lookup"><span data-stu-id="88e7d-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="88e7d-135">Lync 팀 블로그에서 [알림을](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="88e7d-135"> Read [the announcement](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="88e7d-136">7 월 30 일 이후에 확장 되는 계약에 PIC 라이선스가 있는 고객은 2014 년 6 월 30 2014 일 이후 경과 된 기간에 대 한 납입 금액에 비례하여 학점을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="88e7d-137">**AOL** -6 월 30 일, 2014, LYNC의 IM 연결 ("PIC") 서비스를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="88e7d-138">서비스가 종료 될 때 중단을 제한 하기 위해 추가 고객 도메인의 프로 비전을 단종 했습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="88e7d-139">2014 년 6 월 30 일까 지, 고객은 모든 작업을 수행 하 여 페더레이션 통신을 계속 지원할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="88e7d-140">이 날짜를 초과 하거나, 다른 도메인을 구축 하려는 고객의 경우에는 AOL에서 직접 대체 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="88e7d-141">AOL의 새로운 서비스에 대 한 자세한 내용은 [AIM를 사용한 직접 페더레이션 설정](http://aimenterprise.aol.com/pic.php)    (AOL.com에서 새 페이지 열기)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="88e7d-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="88e7d-142">공용 IM 공급자 요약</span><span class="sxs-lookup"><span data-stu-id="88e7d-142">Public IM Provider Summary</span></span>

<span data-ttu-id="88e7d-143">다음 표에서는 공용 IM 서비스 공급자, Lync의 페더레이션 기능 및 라이선스 요구 사항에 대 한 요약 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88e7d-144">공용 IM 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="88e7d-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="88e7d-145">페더레이션 기능</span><span class="sxs-lookup"><span data-stu-id="88e7d-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="88e7d-146">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="88e7d-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88e7d-147">스카이프</span><span class="sxs-lookup"><span data-stu-id="88e7d-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="88e7d-148">IM, 현재 상태, 오디오</span><span class="sxs-lookup"><span data-stu-id="88e7d-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="88e7d-149">Lync Server 클라이언트 액세스 라이선스, Lync Online 계획 1/2/3</span><span class="sxs-lookup"><span data-stu-id="88e7d-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e7d-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="88e7d-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="88e7d-151">IM, 현재 상태, 오디오/비디오</span><span class="sxs-lookup"><span data-stu-id="88e7d-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="88e7d-152">Lync Server 클라이언트 액세스 라이선스 (WLM이 시장에 해당 되는 경우에만 지원 됨)</span><span class="sxs-lookup"><span data-stu-id="88e7d-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e7d-153">AOL</span><span class="sxs-lookup"><span data-stu-id="88e7d-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="88e7d-154">IM, 현재 상태</span><span class="sxs-lookup"><span data-stu-id="88e7d-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="88e7d-155">Lync Server 클라이언트 액세스 라이선스; 기존 고객이 6 월 2014까지 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e7d-156">!</span><span class="sxs-lookup"><span data-stu-id="88e7d-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="88e7d-157">IM, 현재 상태</span><span class="sxs-lookup"><span data-stu-id="88e7d-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="88e7d-158">Lync Server 클라이언트 액세스 라이선스 외에도 추가 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="88e7d-159">9 월 2012 일에 해당 하는 경우, PIC USL은 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="88e7d-160">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="88e7d-161">서비스가 종료 될 때까지 Messenger는 6 월 30 일 2014입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

