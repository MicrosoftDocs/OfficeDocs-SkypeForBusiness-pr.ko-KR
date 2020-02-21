---
title: 'Lync Server 2013: 역방향 프록시를 통해 액세스 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d061daedcdfabf4636c78a3a6a8bbe601903a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="4c5be-102">Lync Server 2013에서 역방향 프록시를 통해 액세스 확인</span><span class="sxs-lookup"><span data-stu-id="4c5be-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c5be-103">_**마지막으로 수정 된 항목:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="4c5be-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="4c5be-p101">다음 절차를 수행하여 사용자가 역방향 프록시에 대한 정보에 액세스할 수 있는지 확인합니다. 액세스가 제대로 작동하려면 먼저 방화벽 구성과 DNS(Domain Name System) 구성을 완료해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="4c5be-106">인터넷을 통해 웹 사이트에 액세스할 수 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="4c5be-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="4c5be-107">웹 브라우저를 열고 **주소** 표시줄에 클라이언트에서 웹 회의용 주소록 파일과 웹 사이트에 액세스하는 데 사용하는 URL을 다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="4c5be-108">주소록 서버에는 externalwebfarmFQDN가 주소록 서비스를 호스트 하는 외부 **https://externalwebfarmFQDN/abs** 웹 서비스의 외부 FQDN과 유사한 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="4c5be-109">기본적으로 주소록 서버 폴더의 디렉터리 보안은 Windows 인증으로 구성되므로 사용자는 HTTP 챌린지를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="4c5be-110">회의의 경우 다음과 비슷한 URL을 입력 합니다. **https://externalwebfarmFQDN/meet** 여기서 externalwebfarmFQDN은 모임 콘텐츠를 호스트 하는 웹 팜의 외부 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="4c5be-111">이 URL은 회의에 대한 문제 해결 페이지를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="4c5be-112">또는 회의용 단순 URL이 올바르게 작동하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="4c5be-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="4c5be-113">전화 회의 조인의 간단한 URL 예https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c5be-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="4c5be-114">메일 그룹 확장의 경우 다음과 **https://externalwebfarmFQDN/GroupExpansion/service.svc**같은 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="4c5be-115">기본적으로 메일 그룹 확장 서비스의 디렉터리 보안은 Windows 인증으로 구성되므로 사용자는 HTTP 챌린지를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="4c5be-116">전화 접속의 경우 externalwebfarmFQDN가 전화 접속 회의에 대 한 전화 **https://externalwebfarmFQDN/dialin** 접속 페이지를 호스트 하는 웹 팜의 외부 FQDN 인 경우와 비슷한 단순 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="4c5be-117">사용자는 전화 접속 페이지로 이동되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="4c5be-118">또는 단순 URL 전화 접속 기능이 올바르게 작동하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="4c5be-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="4c5be-119">다음은 전화 접속에 대 한 간단한 URL 예입니다.https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c5be-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="4c5be-120">자동 검색 URL이 작동 하는지 확인 하려면를 입력 https://lyncdiscover합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="4c5be-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="4c5be-121">externaldomainFQDN.</span></span> <span data-ttu-id="4c5be-122">브라우저에 파일을 열지 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="4c5be-123">메모장을 선택 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-123">Select Notepad to open it.</span></span> <span data-ttu-id="4c5be-124">일반적인 응답은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5be-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

