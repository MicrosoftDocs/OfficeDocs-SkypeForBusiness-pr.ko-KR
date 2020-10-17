---
title: 'Lync Server 2013: Lync Windows 스토어 앱 요구 사항'
description: 'Lync Server 2013: Lync Windows 스토어 앱 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17e8705a55625bcf0ad099ead1000a82c994d867
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566504"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="777cf-103">Lync Server 2013에 대 한 lync Windows 스토어 앱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="777cf-103">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="777cf-104">_**마지막으로 수정 된 항목:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="777cf-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="777cf-105">Lync Server의 온-프레미스 배포를 사용 하는 조직은 Lync Windows 스토어 앱을 지원 하기 위해 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-105">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="777cf-106">Lync Server 2010의 경우 Lync Server 2010에 대 한 누적 업데이트: 2 월 2012 (사용 가능한 경우 <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) 이상에서 모든 서버에 대해 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-106">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="777cf-107">사용자가 모임에 참가할 수 있도록 설정 하려면 서버에서 Lync Server 2010 10 월 2012 (사용 가능한 경우 <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp , 2737915</A>)에 대 한 누적 업데이트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-107">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="777cf-108">서버에서 자동 검색, Lync Web App 및 웹 티켓 서비스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-108">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="777cf-109">프런트 엔드 서버 또는 프런트 엔드 풀에서 인증서 인증을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-109">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="777cf-110">프런트 엔드 서버 또는 프런트 엔드 풀의 사용자 등록 프로세스를 등록자 라고 합니다. 자세한 내용은 [Create 등록자 구성 설정에서 Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="777cf-110">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="777cf-111">자동 검색 서비스에 대 한 CNAME (DNS 별칭) 리소스 레코드를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-111">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="777cf-112">Lync server에 발급 된 인증서에 대 한 CRL (인증서 해지 목록)이 LDAP 리소스 대신 HTTP 리소스를 가리키는지 확인 하는 것은 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-112">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="777cf-113">그러나 클라이언트 컴퓨터에 최신 Windows 업데이트가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-113">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="777cf-114">Lync server 관련 HTTP 트래픽을 허용 하도록 엔터프라이즈의 HTTP 프록시를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-114">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="777cf-115">필요한 경우 자동 검색, Lync Web App 및 WebTicket 서비스에 대 한 예외를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-115">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="777cf-116">클라이언트에서 Windows 8.1 및 최신 버전의 Lync Windows 스토어 앱을 설치 하 여 여러 도메인을 사용 하는 경우 일반적으로 발생 하는 로그인 문제 (예: SIP URI가 **userA@domainZ.com** 되지만에 지 서버는 **sip.domainX.com**)를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-116">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="777cf-117">조직에서 Lync Online 또는 Microsoft 365을 구독 하 고 사용자의 도메인 이름을 사용 하는 경우 Lync 서버의 자동 검색을 위해 네트워크를 설정 하기 위한 몇 가지 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-117">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="777cf-118">네트워크 구성 요구 사항은 Lync Windows 스토어 앱 및 Lync for 모바일 장치에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="777cf-118">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="777cf-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="777cf-119">See Also</span></span>


[<span data-ttu-id="777cf-120">Lync Server 2013에서 Lync Windows 스토어 앱 배포</span><span class="sxs-lookup"><span data-stu-id="777cf-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
