---
title: Skype 모임 앱 최소 네트워크 요구 사항
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '요약: Microsoft 365 또는 Office 365를 사용하지 않는 조직에서 호스팅하는 모임에 액세스해야 하는 조직에 대한 정보입니다.'
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816308"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="ea516-103">Skype 모임 앱 최소 네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea516-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="ea516-104">**요약:**  Microsoft 365 또는 Office 365를 사용하지 않는 조직에서 호스팅하는 모임에 액세스해야 하는 조직에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ea516-104">**Summary:**  Information for organizations who don't use Microsoft 365 or Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="ea516-105">이 문서는 이러한 앱의 사용자를 위한 것이 아니며,</span><span class="sxs-lookup"><span data-stu-id="ea516-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="ea516-106">사용자가 비즈니스용 Skype Online에서 호스트되는 모임에 Skype 모임 앱을 사용할 수 있도록 허용하기 위해 Microsoft 365 또는 Office 365를 사용하지 않는 조직의 네트워크 관리자는 아래에 언급된 FQDNS, IP 및 포트를 허용하거나 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea516-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Microsoft 365 or Office 365 should allow or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="ea516-107">Skype 모임 앱 연결 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea516-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="ea516-108">여기에 나열된 정보는 Office [365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)및 IP 주소 범위의 하위 집합으로, 보다 깊이를 제공하며 항상 최신 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea516-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="ea516-109">앱</span><span class="sxs-lookup"><span data-stu-id="ea516-109">App</span></span> |<span data-ttu-id="ea516-110">대상 FQDNS</span><span class="sxs-lookup"><span data-stu-id="ea516-110">Destination FQDNs</span></span>  |<span data-ttu-id="ea516-111">IP 주소</span><span class="sxs-lookup"><span data-stu-id="ea516-111">IP Addresses</span></span>  |<span data-ttu-id="ea516-112">포트</span><span class="sxs-lookup"><span data-stu-id="ea516-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="ea516-113">**Skype 모임 앱**</span><span class="sxs-lookup"><span data-stu-id="ea516-113">**Skype Meetings App**</span></span> | <span data-ttu-id="ea516-114">\*.lync.com</span><span class="sxs-lookup"><span data-stu-id="ea516-114">\*.lync.com</span></span> <br/><span data-ttu-id="ea516-115">\*.infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="ea516-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="ea516-116">\*.pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ea516-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="ea516-117">\*.sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="ea516-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="ea516-118">\*.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="ea516-118">\*.msecnd.net</span></span><br/><span data-ttu-id="ea516-119">\*<span></span>broadcast .officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="ea516-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="ea516-120">\*powerpoint <span></span> .officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="ea516-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="ea516-121">\*.office.live.com</span><span class="sxs-lookup"><span data-stu-id="ea516-121">\*.office.live.com</span></span><br/><span data-ttu-id="ea516-122">\*.cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="ea516-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="ea516-123">\*.s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ea516-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="ea516-124">이러한 IP 주소는 자주 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea516-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="ea516-125">Office [IP 범위뿐만](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 아니라 비즈니스용 Skype [IP 범위도 참조](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="ea516-125">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="ea516-126">TCP: 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="ea516-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="ea516-127">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="ea516-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="ea516-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="ea516-128">**Teams**</span></span>    | <span data-ttu-id="ea516-129">\*<span></span>.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ea516-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="ea516-130">\*<span></span>.skype.com</span><span class="sxs-lookup"><span data-stu-id="ea516-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="ea516-131">이러한 IP 주소는 자주 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea516-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="ea516-132">Office [IP 범위뿐만](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 아니라 비즈니스용 Skype [IP 범위도 참조](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="ea516-132">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="ea516-133">TCP: 443</span><span class="sxs-lookup"><span data-stu-id="ea516-133">TCP:  443</span></span> <br/> <span data-ttu-id="ea516-134">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="ea516-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="ea516-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea516-135">See also</span></span>
<span data-ttu-id="ea516-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="ea516-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="ea516-137">모임 클라이언트 계획(Web App 및 모임 앱)</span><span class="sxs-lookup"><span data-stu-id="ea516-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="ea516-138">비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="ea516-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="ea516-139">Skype 모임 앱에 대해 지원되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="ea516-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
