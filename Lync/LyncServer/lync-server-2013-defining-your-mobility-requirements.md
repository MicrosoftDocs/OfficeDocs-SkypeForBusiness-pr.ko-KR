---
title: 'Lync Server 2013: 모바일 기능 요구 사항 정의'
description: 'Lync Server 2013: 모바일 기능 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbc1a443946f0c879397f41628cfe788b428ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545544"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="360e8-103">Lync Server 2013에 대 한 모바일 기능 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="360e8-103">Defining your mobility requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="360e8-104">_**마지막으로 수정 된 항목:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="360e8-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="360e8-105">Lync Server 2013 모바일 기능에 대 한 계획 단계 중에 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트를 사용 하는 경우에는 배포 단계를 결정 하는 결정을 내려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-105">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="360e8-106">고려해 야 할 결정 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-106">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="360e8-107">**Lync 모바일 클라이언트에 대해 자동 검색을 사용할지 여부**</span><span class="sxs-lookup"><span data-stu-id="360e8-107">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="360e8-108">자동 검색을 지원 하려면 새 내부 및 외부 DNS (Domain Name System) 레코드를 만들고, 프런트 엔드 서버, 디렉터 및 역방향 프록시의 인증서에 주체 대체 이름을 추가 하 고, 역방향 프록시의 기존 게시 규칙을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-108">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="360e8-109">자세한 내용은 [Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="360e8-109">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="360e8-110">자동 검색을 사용 하면 사용자가 모바일 장치 설정에 Url을 입력 하지 않고도 회사 네트워크 내부 또는 외부의 어디에서 든 지 Lync Server 2013 웹 서비스를 자동으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-110">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="360e8-111">자동 검색 대신 수동 설정을 사용 하는 경우 모바일 사용자가 모바일 장치에서 다음 Url을 수동으로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-111">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="360e8-112">\<ExtPoolFQDN\>외부 액세스용 Https://https://</span><span class="sxs-lookup"><span data-stu-id="360e8-112">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="360e8-113">\<IntPoolFQDN\>내부 액세스용 Https:///AutoDiscover/autodiscoverservice/Root</span><span class="sxs-lookup"><span data-stu-id="360e8-113">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="360e8-p102">자동 검색은 사용하는 것이 좋습니다. 수동 설정은 주로 문제 해결 시에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="360e8-116">**자동 검색을 지원하기로 결정하는 경우 각 SIP 도메인의 주체 대체 이름으로 역방향 프록시의 인증서를 업데이트할지 여부**</span><span class="sxs-lookup"><span data-stu-id="360e8-116">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="360e8-117">SIP 도메인이 여러 개인 경우 역방향 프록시에서 공용 인증서를 업데이트하려면 비용이 매우 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-117">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="360e8-118">이러한 경우에는 초기 자동 검색 서비스 요청이 포트 443에서 HTTPS를 사용 하는 대신 포트 80에서 HTTP를 사용 하도록 자동 복구를 구현 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-118">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="360e8-119">그러나 권장 되는 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-119">However, this is not the recommended approach.</span></span> <span data-ttu-id="360e8-120">이 대체 방법을 선택 하는 경우 역방향 프록시에서 인증서를 업데이트할 필요가 없지만 포트 80의 HTTP에 대 한 웹 게시 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-120">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="360e8-121">자세한 내용은 [Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="360e8-121">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="360e8-122">**Lync 모바일 클라이언트를 지원할 위치(회사 네트워크 내부와 외부에서 모두 지원/회사 네트워크 내부에서만 지원)**</span><span class="sxs-lookup"><span data-stu-id="360e8-122">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="360e8-p104">모바일 클라이언트를 네트워크 내부와 외부에서 모두 지원하는 경우 모바일 장치가 어디서나 모바일 기능에 액세스할 수 있습니다. 기본 구성에서는 회사 네트워크 내부와 외부에서 모두 클라이언트가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="360e8-125">기본 구성을 사용 하면 모바일 클라이언트 트래픽이 외부 사이트를 통과 하 게 되지만 모바일 클라이언트 트래픽이 내부 회사 네트워크로 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-125">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="360e8-126">내부 네트워크에 대 한 트래픽을 제한 하면 사용자가 네트워크 내부에 있을 때만 모바일 장치에서 Lync 모바일 응용 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-126">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="360e8-127">Mcx mobility service 및 Lync 2010 Mobile을 사용 하 여 모바일 기능을 지 원하는 배포의 경우, **Set-CsMcxConfiguration** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-127">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="360e8-128">내부 전용으로 모바일 기능을 설정 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-128">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="360e8-129">지 수에는 추가 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-129">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="360e8-130">(C)는 동등한 내부 전용 구성을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-130">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="360e8-131">Lync Server 2013 &nbsp; 프런트 엔드 서버 또는 프런트 엔드 풀을 사용 하는 경우 Lync <STRONG>you do not have</STRONG> Server 2010 &nbsp; 프런트 엔드 서버 또는 프런트 엔드 풀이 없으면 <STRONG>쿠키 기반 지 속성에 대 한 요구 사항은 없습니다</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="360e8-131">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="360e8-132">Lync Server 2010 &nbsp; 프런트 엔드 서버 또는 프런트 엔드 풀을 유지 해야 하는 경우에는 쿠키 기반 지 속성에 대해 동일한 규칙이 여전히 Lync server 2010에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-132">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="360e8-133">**Apple iOS 장치 및 Windows Phone에 대해 푸시 알림을 지원할지 여부**</span><span class="sxs-lookup"><span data-stu-id="360e8-133">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="360e8-134">푸시 알림을 지원하는 경우 지원되는 Apple iOS 장치 및 Windows Phone에서는 모바일 응용 프로그램이 비활성 상태일 때 발생하는 이벤트의 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-134">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="360e8-135">Edge 서버가 Lync Online 데이터 센터에 있는 클라우드 기반 Lync Server 푸시 알림 서비스와의 페더레이션 관계를 갖도록 구성 하 고, cmdlet을 실행 하 여 푸시 알림을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-135">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="360e8-136">Wi-Fi 네트워크를 통해 푸시 알림을 지원 하 고, 모바일 장치 공급자의 3G 또는 데이터 네트워크에 대 한 푸시 알림을 지 원하는 경우에는 엔터프라이즈 Wi-Fi 네트워크에서 포트 5223 아웃 바운드를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-136">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="360e8-137">Wi-Fi만 사용하는 모바일 장치와 실내 수신 상태가 좋지 않은 모바일 장치에 한해 Wi-Fi 네트워크를 통해 푸시 알림을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-137">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="360e8-138">열기 포트 TCP 5223는 Lync 2010 모바일 클라이언트를 실행 하는 Apple 장치를 지 원하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-138">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="360e8-139">푸시 알림을 지원 하지 않으면 Apple 모바일 장치 및 Windows phone 사용자는 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트 (예: 인스턴트 메시지 초대 또는 부재 중 메시지)를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-139">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="360e8-140">Apple 장치에서의 Lync 2013 모바일 클라이언트에는 푸시 알림이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-140">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="360e8-141">Windows Phone의 Lync 2013 모바일 클라이언트는 푸시 알림을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-141">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="360e8-142">푸시 알림 및 푸시 알림 클리어 링 계획은 Lync 2013 모바일 클라이언트를 실행할 수 없는 Windows Phone 및 Apple 장치의 Lync Mobile에 대해서도 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-142">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="360e8-143">**모든 사용자에 게 모바일 기능에 대 한 액세스를 원하십니까? 아니면 이러한 기능에 대 한 액세스 권한이 있는 사용자를 지정할 수 있도록 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="360e8-143">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="360e8-144">이 표에서는 Lync Server 2013에서 사용자가 사용할 수 있는 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-144">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="360e8-145">기본값은 직장에서 전화 걸기, VoIP (Voice over IP) 허용 및 모바일 기능을 사용 하도록 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-145">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="360e8-146">사용 가능한 옵션의 전체 집합은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-146">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="360e8-147">Feature/Parameter Name/Scope (Policy 매개 변수 이름이 같을 수 없음)</span><span class="sxs-lookup"><span data-stu-id="360e8-147">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="360e8-148">설명</span><span class="sxs-lookup"><span data-stu-id="360e8-148">Description</span></span></th>
    <th><span data-ttu-id="360e8-149">도입</span><span class="sxs-lookup"><span data-stu-id="360e8-149">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="360e8-150">모바일 기능 사용</span><span class="sxs-lookup"><span data-stu-id="360e8-150">Enable Mobility</span></span></p>
    <p><span data-ttu-id="360e8-151">매개 변수 이름: <code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="360e8-151">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="360e8-152">범위: 전역/사이트/사용자</span><span class="sxs-lookup"><span data-stu-id="360e8-152">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="360e8-153">관리 설정 Lync Mobile이 설치 된 지정 된 범위에서 사용자를 제어 하기 위해 정책이 False로 설정 되어 있으면 사용자가 클라이언트에 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-153">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="360e8-154">기본 설정은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-154">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="360e8-155">Lync Server 2010 용 누적 업데이트: 11 월 2011</span><span class="sxs-lookup"><span data-stu-id="360e8-155">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="360e8-156">외부 음성 사용</span><span class="sxs-lookup"><span data-stu-id="360e8-156">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="360e8-157">매개 변수 이름: <code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="360e8-157">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="360e8-158">범위: 전역/사이트/사용자</span><span class="sxs-lookup"><span data-stu-id="360e8-158">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="360e8-159">사용자가 휴대폰을 통해 전화를 사용 하는 기능을 제어 하는 기능이 지원 되는 기능인 회사 번호를 사용 하 여 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-159">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="360e8-160">False로 설정 하면 사용자가 모바일 장치에서 회사 번호를 사용 하 여 전화를 걸거나 받을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-160">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="360e8-161">기본 설정은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-161">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="360e8-162">Lync Server 2010 용 누적 업데이트: 11 월 2011</span><span class="sxs-lookup"><span data-stu-id="360e8-162">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="360e8-163">IP 오디오 및 비디오 사용</span><span class="sxs-lookup"><span data-stu-id="360e8-163">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="360e8-164">매개 변수 이름: <code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="360e8-164">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="360e8-165">범위: 전역/사이트/사용자</span><span class="sxs-lookup"><span data-stu-id="360e8-165">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="360e8-166">사용자가 VoIP를 사용 하 여 모바일 장치에서 음성 또는 비디오 통화를 만들거나 수신할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-166">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="360e8-167">False로 설정 하면 사용자가 장치에서 VoIP 또는 비디오 통화를 만들거나 받을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-167">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="360e8-168">기본 설정은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-168">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="360e8-169">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="360e8-169">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="360e8-170">IP 오디오에 WiFi 필요</span><span class="sxs-lookup"><span data-stu-id="360e8-170">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="360e8-171">매개 변수 이름: <code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="360e8-171">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="360e8-172">범위: 전역/사이트/사용자</span><span class="sxs-lookup"><span data-stu-id="360e8-172">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="360e8-173">이 설정은 클라이언트가 셀룰러 데이터 네트워크가 아닌 WiFi에서 VoIP를 통해 전화를 걸고 받아야 하는지 여부를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-173">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="360e8-174">True로 설정 하면 사용자가 WiFi 네트워크에 연결 된 경우에만 VoIP 통화를 설정 하 고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-174">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="360e8-175">기본 설정은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-175">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="360e8-176">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="360e8-176">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="360e8-177">IP 비디오에 WiFi 필요</span><span class="sxs-lookup"><span data-stu-id="360e8-177">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="360e8-178">매개 변수 이름: <code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="360e8-178">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="360e8-179">범위: 전역/사이트/사용자</span><span class="sxs-lookup"><span data-stu-id="360e8-179">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="360e8-180">이 설정은 클라이언트가 셀룰러 데이터 네트워크 대신 Wi-Fi에서 비디오 통화를 설정 하 고 수신 해야 하는지 여부를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-180">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="360e8-181">True로 설정 된 경우 사용자는 Wi-Fi 네트워크에 연결 된 경우에만 비디오 통화를 설정 하 고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-181">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="360e8-182">기본 설정은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-182">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="360e8-183">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="360e8-183">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="360e8-184">구성할 수 있는 정책 설정에 대 한 설명과 정책을 관리 하는 방법에 대 한 자세한 내용은 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) 및 [Remove-get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="360e8-184">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="360e8-185">**Enterprise Voice를 사용할 수 있도록 설정되지 않은 사용자가 클릭하여 참가를 사용하여 회의에 참가하도록 할지 여부**</span><span class="sxs-lookup"><span data-stu-id="360e8-185">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="360e8-186">모바일 기능 및 회사번호로 전화 기능에 액세스할 수 있는 사용자는 Enterprise Voice를 사용할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-186">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="360e8-187">그러나 Enterprise Voice를 사용 하도록 설정 되지 않은 사용자는 해당 모바일 장치에 대 한 적절 한 음성 정책이 할당 되어 있는 경우 해당 링크를 클릭 하 여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-187">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="360e8-188">이러한 사용자에 게 특정 음성 정책을 할당 하거나 해당 정책에 적용 되는 글로벌 정책 또는 사이트 수준 정책이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-188">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="360e8-189">지정 하는 음성 정책에는 사용자가 회의에 참가 하기 위해 전화를 걸 수 있는 영역을 정의 하는 PSTN (공중 전화망) 사용 레코드 및 경로가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-189">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="360e8-190">음성 정책, PSTN 사용 레코드 및 경로를 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 음성 정책, pstn 사용 레코드 및 음성 경로 구성을](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="360e8-190">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="360e8-191">모바일 장치에서 링크를 클릭 하면 Lync Server 2013에서 아웃 바운드 호출을 수행 하므로 클릭 하 여 참가 하려는 모바일 사용자에 게는 관련 PSTN 사용 레코드 및 음성 경로와 함께 음성 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="360e8-191">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="360e8-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="360e8-192">See Also</span></span>


[<span data-ttu-id="360e8-193">Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="360e8-193">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="360e8-194">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="360e8-194">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

