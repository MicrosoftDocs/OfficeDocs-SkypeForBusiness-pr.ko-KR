---
title: Skype 모임 앱 최소 네트워크 요구 사항
ms.author: v-lanac
author: lanachin
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
description: '요약: Office 365를 사용 하지 않고 조직에서 호스팅하는 모임에 액세스 해야 하는 조직에 대 한 정보입니다.'
ms.openlocfilehash: 162d05f9786f02258afa080e630c85d4b513db4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033192"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="8d582-103">Skype 모임 앱 최소 네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d582-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="8d582-104">**요약:**  Office 365를 사용 하지 않고 조직에서 호스팅하는 모임에 액세스 해야 하는 조직에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8d582-104">**Summary:**  Information for organizations who don't use Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="8d582-105">이 문서는 이러한 앱의 사용자를 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8d582-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="8d582-106">사용자가 Skype 모임 앱을 사용 하 여 비즈니스용 Skype Online에서 호스트 되는 모임에 참가할 수 있도록 허용 하려면 Office 365을 사용 하지 않는 조직의 네트워크 관리자에 게 허용 목록 하거나, 아래에 설명 된 Fqdn, Ip 및 포트를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d582-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Office 365 should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="8d582-107">Skype 모임 앱 연결 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d582-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="8d582-108">여기에 나열 된 정보는 보다 깊이를 제공 하 고 항상 최신 상태로 유지 되는 [Office 365 url 및 IP 주소 범위의](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="8d582-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="8d582-109">앱</span><span class="sxs-lookup"><span data-stu-id="8d582-109">App</span></span> |<span data-ttu-id="8d582-110">대상 Fqdn</span><span class="sxs-lookup"><span data-stu-id="8d582-110">Destination FQDNs</span></span>  |<span data-ttu-id="8d582-111">IP 주소</span><span class="sxs-lookup"><span data-stu-id="8d582-111">IP Addresses</span></span>  |<span data-ttu-id="8d582-112">포트</span><span class="sxs-lookup"><span data-stu-id="8d582-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="8d582-113">**Skype 모임 앱**</span><span class="sxs-lookup"><span data-stu-id="8d582-113">**Skype Meetings App**</span></span> | <span data-ttu-id="8d582-114">\*. lync.com</span><span class="sxs-lookup"><span data-stu-id="8d582-114">\*.lync.com</span></span> <br/><span data-ttu-id="8d582-115">\*. infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d582-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="8d582-116">\*. pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8d582-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="8d582-117">\*. sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="8d582-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="8d582-118">\*. msecnd.net</span><span class="sxs-lookup"><span data-stu-id="8d582-118">\*.msecnd.net</span></span><br/><span data-ttu-id="8d582-119">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="8d582-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="8d582-120">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="8d582-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="8d582-121">\*. office.live.com</span><span class="sxs-lookup"><span data-stu-id="8d582-121">\*.office.live.com</span></span><br/><span data-ttu-id="8d582-122">\*. cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="8d582-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="8d582-123">\* s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8d582-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="8d582-124">이러한 IP 주소는 자주 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d582-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="8d582-125">[OFFICE Ip 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) 는 물론 [비즈니스용 Skype IP 범위](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d582-125">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="8d582-126">TCP: 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="8d582-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="8d582-127">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="8d582-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="8d582-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="8d582-128">**Teams**</span></span>    | <span data-ttu-id="8d582-129">\*<span></span>. microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8d582-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="8d582-130">\*<span></span>. skype.com</span><span class="sxs-lookup"><span data-stu-id="8d582-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="8d582-131">이러한 IP 주소는 자주 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d582-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="8d582-132">[OFFICE Ip 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) 는 물론 [비즈니스용 Skype IP 범위](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d582-132">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="8d582-133">TCP: 443</span><span class="sxs-lookup"><span data-stu-id="8d582-133">TCP:  443</span></span> <br/> <span data-ttu-id="8d582-134">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="8d582-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="8d582-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d582-135">See also</span></span>
<span data-ttu-id="8d582-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="8d582-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="8d582-137">모임 클라이언트 계획 (웹 앱 및 모임 앱)</span><span class="sxs-lookup"><span data-stu-id="8d582-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="8d582-138">비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="8d582-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="8d582-139">Skype 모임 앱에 대해 지원 되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="8d582-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
