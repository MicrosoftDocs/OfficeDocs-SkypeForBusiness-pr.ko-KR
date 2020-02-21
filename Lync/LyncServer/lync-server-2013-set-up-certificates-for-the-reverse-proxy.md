---
title: 'Lync Server 2013: 역방향 프록시에 대 한 인증서 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c7a4e6ede9afe8d521d8dea3bd9350801588b90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="71b85-102">Lync Server 2013에서 역방향 프록시에 대 한 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="71b85-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71b85-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="71b85-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="71b85-p101">각 역방향 프록시 서버에는 수신 서비스에서 사용할 웹 서버 인증서가 필요합니다. 웹 서버 인증서는 공용 CA(인증 기간)에서 발급되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b85-p101">Each reverse proxy server requires a web server certificate for use by the listening service. The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="71b85-106">이 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="71b85-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="71b85-107">역방향 프록시에 대해 웹 서비스 인증서를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="71b85-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="71b85-108">웹 서비스 인증서 설정 등을 비롯한 역방향 프록시가 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b85-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="71b85-109">에 지 서버 배포를 시작 하기 전에이 작업을 수행 하지 않은 경우에는 [Lync Server 2013에 대 한 역방향 프록시 서버 설정](lync-server-2013-setting-up-reverse-proxy-servers.md) 의 절차를 사용 하 여 요청을 만들고 웹 서비스 인증서를 설치한 다음 각 웹 게시 규칙을 만들고 인증서를 사용 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b85-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

