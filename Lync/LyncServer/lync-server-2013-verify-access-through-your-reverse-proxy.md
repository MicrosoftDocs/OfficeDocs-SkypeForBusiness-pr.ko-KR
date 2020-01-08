---
title: 'Lync Server 2013: 역방향 프록시를 통해 액세스 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="108aa-102">Lync Server 2013에서 역방향 프록시를 통해 액세스 확인</span><span class="sxs-lookup"><span data-stu-id="108aa-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="108aa-103">_**마지막으로 수정한 주제:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="108aa-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="108aa-104">사용자가 리버스 프록시의 정보에 액세스할 수 있는지 확인 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="108aa-105">액세스가 올바르게 작동 하려면 방화벽 구성 및 DNS (Domain Name System) 구성을 완료 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="108aa-106">인터넷을 통해 웹 사이트에 액세스할 수 있는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="108aa-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="108aa-107">웹 브라우저를 열고 다음과 같이 클라이언트에서 주소록 파일과 회의 웹 사이트에 액세스 하는 데 사용 하는 **주소** 표시줄에 url을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="108aa-108">주소록 서버의 경우 다음과 유사한 URL을 입력 합니다. **https://externalwebfarmFQDN/abs** 여기서 ExternalwebfarmFQDN는 주소록 서비스를 호스팅하는 외부 웹 서비스의 외부 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="108aa-109">주소록 서버 폴더의 디렉터리 보안이 기본적으로 Windows 인증으로 구성 되어 있으므로 사용자에 게 HTTP 챌린지를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="108aa-110">회의의 경우 다음과 유사한 URL을 입력 합니다. **https://externalwebfarmFQDN/meet** 여기서 externalwebfarmFQDN는 모임 콘텐츠를 호스트 하는 웹 팜의 외부 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="108aa-111">이 URL에는 회의 문제 해결 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="108aa-112">또는 회의에 대 한 간단한 URL이 올바르게 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="108aa-113">예를 들어 컨퍼런스 조인의 간단한 URL은https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="108aa-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="108aa-114">메일 그룹 확장의 경우 다음과 **https://externalwebfarmFQDN/GroupExpansion/service.svc**유사한 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="108aa-115">메일 그룹 확장 서비스의 디렉터리 보안이 기본적으로 Windows 인증으로 구성 되어 있으므로 사용자에 게 HTTP 챌린지를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="108aa-116">전화 접속의 경우 다음과 **https://externalwebfarmFQDN/dialin** 유사한 간단한 URL을 입력 합니다. 여기서 externalwebfarmFQDN는 전화 접속 회의를 위한 전화 접속 페이지를 호스트 하는 웹 팜의 외부 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="108aa-117">사용자는 전화 접속 페이지로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="108aa-118">또는 간단한 URL 전화 접속 기능이 올바르게 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="108aa-119">예를 들어, 전화 접속의 간단한 URLhttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="108aa-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="108aa-120">자동 검색 URL이 작동 하는지 확인 하려면를 입력 https://lyncdiscover합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="108aa-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="108aa-121">externaldomainFQDN.</span></span> <span data-ttu-id="108aa-122">브라우저에 파일을 열 것인지 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="108aa-123">메모장을 선택 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-123">Select Notepad to open it.</span></span> <span data-ttu-id="108aa-124">일반적인 응답은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="108aa-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

