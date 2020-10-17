---
title: 'Lync Server 2013: Lync Server 2013 제어판 문제 해결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535935"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="2818c-102">Lync Server 2013 제어판 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2818c-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2818c-103">_**마지막으로 수정 된 항목:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="2818c-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="2818c-104">이 항목에서는 Lync Server 2013 제어판에 대 한 액세스 문제를 해결 하는 데 도움이 되는 정보 및 절차를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="2818c-105">인터넷 브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2818c-105">Internet Browser Requirements</span></span>

<span data-ttu-id="2818c-106">Lync Server Control Panel을 사용 하려면 Microsoft Silverlight browser 플러그 인 버전 4.0.50524.0 또는 최신 버전이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="2818c-107">Silverlight가 설치 되어 있지 않거나 이전 버전이 설치 되어 있는 경우 메시지의 지침에 따라 필요한 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2818c-108">Lync Server 제어판의 기타 소프트웨어 요구 사항은 Lync Server 제어판과 기타 모든 Lync Server 2013 관리 도구를 설치할 수 있는 운영 체제와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="2818c-109">자세한 내용은 지원 가능성 설명서의 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013에서 서버 및 도구 운영 체제 지원을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2818c-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="2818c-110">인터넷 브라우저가 보안 고려 사항으로 인해 Silverlight 설치를 차단 하는 경우 Lync Server 제어판을 여는 URL (Uniform Resource Locator)을 신뢰할 수 있는 사이트 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="2818c-111">Internet Explorer 보안 설정에서 **ActiveX 컨트롤 및 플러그인 실행**이 **사용**으로 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="2818c-112">자세한 내용은를 참조 [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) 하세요.</span><span class="sxs-lookup"><span data-stu-id="2818c-112">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="2818c-113">또한 브라우저가 SSL 3.0을 사용하도록 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="2818c-p104">인터넷 브라우저가 프록시 서버를 사용하도록 구성된 경우 자동으로 내부 사이트로 검색된 사이트에 대해 프록시 서버를 바이패스하도록 브라우저가 구성되었는지 확인합니다. 또는 프록시 서버 구성 설정에서 해당 주소를 브라우저의 예외 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="2818c-116">관리 액세스 URL에 대한 DNS 레코드 및 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2818c-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="2818c-117">Lync Server 제어판에 액세스 하기 위한 단순 URL을 구성한 경우에는이 관리 액세스 URL을 사용 하는 데 필요한 정적 DNS (Domain Name System) 호스트 (A) 리소스 레코드 및 인증서도 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="2818c-118">언제 든 지 기본 URL을 변경 하는 경우 변경 내용이 적절 한 DNS 레코드 및 인증서에 반영 되 고 각 디렉터 및 프런트 엔드 서버에서 *사용 하도록 설정 된 컴퓨터* 를 실행 하 여 변경 내용을 등록 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="2818c-119">자세한 내용은 계획 설명서에서 다음 항목들을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2818c-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="2818c-120">Lync Server 2013의 단순 Url 계획</span><span class="sxs-lookup"><span data-stu-id="2818c-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="2818c-121">Lync Server 2013의 단순 Url에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2818c-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="2818c-122">Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2818c-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="2818c-123">관리 액세스 URL을 구성 하는 단계별 절차에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 단순 Url 편집 또는 구성을](lync-server-2013-edit-or-configure-simple-urls.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2818c-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="2818c-124">IIS(인터넷 정보 서비스) 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2818c-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="2818c-125">Lync Server 제어판은 IIS (인터넷 정보 서비스)가 필요한 Lync Server 2013의 구성 요소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="2818c-126">특히 HTTP 리디렉션 및 Windows 인증 기능이 사용하도록 설정되었고 W3SVC(World Wide Web Publishing Service)가 실행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="2818c-127">World Wide Publishing Service(Windows Service) 종속성</span><span class="sxs-lookup"><span data-stu-id="2818c-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="2818c-128">World Wide Web Publishing 서비스가 중지 되 면 Lync Server 제어판에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="2818c-129">Windows Services MMC(Microsoft Management Console)를 사용하여 서비스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="2818c-130">**World Wide Web Publishing Service를 시작하려면**</span><span class="sxs-lookup"><span data-stu-id="2818c-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="2818c-131">World Wide Web Publishing 서비스가 IIS (인터넷 정보 서비스)의 일부로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="2818c-132">**시작**, **관리 도구**, **서비스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="2818c-133">**World Wide Web Publishing Service**를 마우스 오른쪽 단추로 클릭한 후 **시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="2818c-134">응용 프로그램 풀 모드</span><span class="sxs-lookup"><span data-stu-id="2818c-134">Application Pool Mode</span></span>

<span data-ttu-id="2818c-135">CsManagementAppPool 응용 프로그램 풀에서 네트워크 서비스 계정을 프로세스 모델 ID로 사용하도록 IIS를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="2818c-136">사용자 권한 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="2818c-136">User Rights and Permissions</span></span>

<span data-ttu-id="2818c-137">CsAdministrator 그룹의 구성원 인 도메인 계정을 사용 하거나 사용자 권한 및 사용 권한을 위임한 계정을 사용 하 여 Lync Server 제어판에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="2818c-138">로컬 컴퓨터 계정을 사용 하 여 Lync Server 제어판에 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="2818c-139">RBAC (역할 기반 액세스 제어)를 통해 관리 작업을 위임 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2818c-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="2818c-140">단순 URL을 사용 하 여 Lync Server 제어판에 액세스 하는 경우 웹 서버가 RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹에 추가 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2818c-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2818c-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2818c-141">See Also</span></span>


[<span data-ttu-id="2818c-142">Lync Server 2013 관리 도구</span><span class="sxs-lookup"><span data-stu-id="2818c-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

