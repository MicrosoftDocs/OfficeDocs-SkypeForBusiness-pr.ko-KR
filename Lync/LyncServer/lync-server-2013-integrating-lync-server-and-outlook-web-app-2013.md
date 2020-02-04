---
title: 'Lync Server 2013: Lync Server 및 Outlook Web App 2013 통합'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="66e20-102">Microsoft Lync Server 2013 및 Microsoft Outlook Web App 2013 통합</span><span class="sxs-lookup"><span data-stu-id="66e20-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e20-103">_**마지막으로 수정한 주제:** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="66e20-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="66e20-104">Microsoft Outlook 2013와 통합 하는 것 외에 microsoft Lync Server 2013는 Microsoft Outlook Web App 2013과 완벽 하 게 통합 될 수 있습니다. 그 외에, Outlook Web App에 인스턴트 메시징 및 현재 상태를 추가 하 고 Outlook Web App과 Microsoft Lync 2013 간에 통합 된 연락처 목록을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="66e20-105">Lync Server 2013 및 Outlook Web App을 통합 하려면 먼저 Microsoft Exchange Server 2013 백 엔드 서버에 통합 커뮤니케이션 관리 API 4.0 런타임이 설치 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="66e20-106">다음 레지스트리 값이 있는지 검색 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="66e20-107">HKEY\_로컬\_컴퓨터\\시스템\\CurrentControlSet\\서비스\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="66e20-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="66e20-108">ImplementationDLLPath는 파일에 대 한 폴더 위치 (예를 들어, Web.config. dll)를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="66e20-109">그렇지 않은 경우 또는 레지스트리 값이 없는 경우 Microsoft 다운로드 센터에서 앱 MA 런타임 설치 프로그램을 다운로드 하 여 설치 해야 <http://www.microsoft.com/en-us/download/details.aspx?id=34992>합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <http://www.microsoft.com/en-us/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="66e20-110">웹 페이지 런타임을 설치 하는 방법에 대 한 정보는 동일한 페이지에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="66e20-111">**이전 버전과의 호환성**</span><span class="sxs-lookup"><span data-stu-id="66e20-111">**Backward Compatibility**</span></span>

<span data-ttu-id="66e20-112">Lync Server 2013는 통합 메시징 및 Outlook Web App의 Microsoft Exchange Server 2010 버전과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="66e20-113">자세한 내용은 온-프레미스 Exchange UM 배포 문서를 참조 하 여 Lync Server 2010에서 [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)음성 메일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="66e20-114">Exchange 2010와 통합 하는 경우 통합 된 연락처 저장소와 Lync에서 Exchange 보관 등의 Lync Server 관련 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="66e20-115">Microsoft Lync 2013는 Exchange 2010 및 Outlook 2010과 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="66e20-116">그러나이 경우에도 Lync 2013 사용자는 통합 된 연락처 저장소와 고해상도 사진 등의 새로운 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="66e20-117">이러한 새로운 접근 권한 값에는 Lync Server 2013 및 Exchange 2013이 모두 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="66e20-118">**Outlook Web App에 대 한 신뢰할 수 있는 응용 프로그램 풀 만들기**</span><span class="sxs-lookup"><span data-stu-id="66e20-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="66e20-119">Microsoft Exchange 통합 메시징 호출 라우터 서비스와 Microsoft Exchange 통합 메시징 서비스를 동일한 컴퓨터에 설치한 경우 Outlook Web App에 대해 신뢰할 수 있는 응용 프로그램 풀을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="66e20-120">(해당 서버가 SipName UM 다이얼 플랜을 호스트 하 고 있다고 가정 합니다.) 단일 컴퓨터를 사용 하 여 이러한 서비스를 모두 호스트 하는 경우 **Outlook Web App에서 인스턴트 메시지를 사용 하도록 설정**하는이 문서의 섹션으로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="66e20-121">Lync Server 2013는 SipName UM 다이얼 플랜을 호스트 하는 Exchange 서버를 자동 검색 하도록 할 수 있습니다. 이러한 서버는 Lync Server 알려진 서버 목록에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="66e20-122">신뢰할 수 있는 응용 프로그램 풀을 만들고이 서버를 알려진 서버 목록에 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="66e20-123">실제로 이렇게 하면 Outlook Web App 통합이 작동을 중지 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66e20-124">이는 Lync Server 토폴로지에서 같은 컴퓨터에 대 한 두 개의 항목, 즉 autodiscovered 항목 및 수동으로 추가 된 항목을 사용 하는 것 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="66e20-125">문제를 해결 하 고 Outlook Web App이 다시 작동 하 게 하려면 Windows PowerShell을 사용 하 여 서버에 대 한 신뢰할 수 있는 풀 및 신뢰할 수 있는 응용 프로그램 항목을 제거 하세요.</span><span class="sxs-lookup"><span data-stu-id="66e20-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="66e20-126">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">remove-CsTrustedApplicationPool</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">remove-CsTrustedApplication</A> cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66e20-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="66e20-127">이러한 두 서비스가 별도의 컴퓨터에서 실행 되는 경우 통합 커뮤니케이션 관리 API 4.0 런타임이 설치 되어 있는지 확인 한 후에는 Lync Server 신뢰할 수 있는 응용 프로그램 풀과 연결 된 신뢰할 수 있는 응용 프로그램을 만들어야 합니다. Outlook Web App 그러면 서버를 알려진 서버 목록에 추가 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="66e20-128">이렇게 하려면 먼저 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="66e20-129">앞의 명령에서 atl-owa-001.litwareinc.com은 Outlook Web App 풀의 정규화 된 도메인 이름입니다. Outlook Web App에 대 한 액세스를 제공 하는 인증서의 주체 이름 및 SAN (주체 대체 이름) 필드에 표시 되는 이름과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="66e20-130">마찬가지로 atl-cs-001.litwareinc.com는 새 신뢰할 수 있는 응용 프로그램 풀을 호스팅하는 Lync Server 2013 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="66e20-131">참고로, 지정 된 사이트 Redmond는 Lync Server 사이트의 SiteID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="66e20-132">SiteID는 사이트의 DisplayName과 같을 필요는 없습니다. Lync 서버 관리 셸에서 다음 명령을 실행 하 여 Lync Server 사이트의 SiteIDs 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="66e20-133">신뢰할 수 있는 응용 프로그램 풀을 만든 후 다음과 같은 명령을 사용 하 여 Outlook Web App 용 포트 및 응용 프로그램 Id를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="66e20-134">앞의 명령에서 ApplicationID는 신뢰할 수 있는 응용 프로그램을 구분 하는 데 사용 되는 편리한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-134">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications.</span></span> <span data-ttu-id="66e20-135">ApplicationID는 공백이 나 허용 되지 않는 문자가 포함 되지 않은 텍스트 문자열일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-135">The ApplicationID can be any text string that does not include blank spaces or other prohibited characters.</span></span> <span data-ttu-id="66e20-136">유효한 식별자를 만들려면 ApplicationId를 지정할 때 문자와 숫자만 사용 하는 것이 좋습니다. Port 매개 변수에 할당 되는 값은 관리자의 재량으로 남아 있습니다 (사용 가능한 모든 네트워크 포트가 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="66e20-136">(To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="66e20-137">신뢰할 수 있는 응용 프로그램을 만든 후 다음 명령을 실행 하 여 Lync Server 토폴로지의 변경 내용을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="66e20-138">Exchange 클라이언트 액세스 및 사서함 서버도 모든 SIP Uri 다이얼 플랜에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="66e20-139">그러면 서버는 Lync Server 용 ExUmRouting topology를 사용 하 여 신뢰할 수 있는 SIP 피어로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="66e20-140">**Outlook Web App에서 인스턴트 메시지 사용**</span><span class="sxs-lookup"><span data-stu-id="66e20-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="66e20-141">Lync Server가 올바르게 구성 되 면 Outlook Web App 구성을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="66e20-142">해당 프로세스의 첫 번째 단계는 프런트 엔드 서버의 모든 Outlook Web App 가상 디렉터리에서 인스턴트 메시지를 사용 하도록 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="66e20-143">백 엔드 서버의 가상 디렉터리에 대해 인스턴트 메시지를 사용 하도록 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="66e20-144">사실 백 엔드 서버에서 인스턴트 메시지를 사용 하지 않는 것이 좋습니다. Exchange 관리 셸에서 다음 명령을 실행 하 여 클라이언트 액세스 서버에서 인스턴트 메시지를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="66e20-145">Outlook Web App을 설치 하면 기본적으로 인스턴트 메시지를 사용할 수 있습니다. 즉, InstantMessagingEnabled 속성이 True로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-145">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="66e20-146">그러나 인스턴트 메시지 형식을 OCS로 설정 하려면 앞의 명령을 계속 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-146">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="66e20-147">기본적으로 InstantMessagingType는 없음으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-147">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="66e20-148">다음 두 줄을 Outlook Web App web.config 파일에 추가 해야 합니다 (이 파일은\\일반적으로 C: 폴더에 있습니다 (\\Microsoft\\Exchange Server\\V15\\clientaccess\\Owa).</span><span class="sxs-lookup"><span data-stu-id="66e20-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="66e20-149">이러한 두 줄은 web.config 파일의 \<AppSettings\> 노드 아래에 추가 되어야 하며, Outlook Web App이 설치 된 백 엔드 서버 에서만이 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="66e20-150">앞의 예제에서 IMCertificateThumbprint의 값은 백 엔드 서버에 설치 된 Exchange 2013 인증서의 지문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="66e20-151">Exchange 관리 셸에서 다음 명령을 실행 하 여 해당 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="66e20-152">또한 IMServerName에 할당 된 값이 Outlook Web App에 대해 신뢰할 수 있는 응용 프로그램 풀을 만든 Lync Server 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="66e20-153">Outlook Web App에 사용 하는 인증서는 Lync Server에서 신뢰 하는 인증서 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="66e20-154">Lync Server와 Exchange에서 모두 인증서를 신뢰할 수 있는지 확인 하는 한 가지 방법은 내부 인증 기관을 사용 하 여 사서함 서버에서 인증서를 만든 후 해당 서버 FQDN이 주체 이름에 사용 되 고이 FQDN이 t e에 표시 되도록 하는 것입니다. 인증서 대체 이름 필드</span><span class="sxs-lookup"><span data-stu-id="66e20-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="66e20-155">인증서를 만든 후에는 백엔드 서버로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="66e20-156">결과적으로 동일한 인증서가 Exchange 통합 메시징과 Lync Server 간의 두 가지 목적으로 통신 하는 데 사용 됩니다. and, 2) Outlook Web App과 Lync 서버 간의 통합.</span><span class="sxs-lookup"><span data-stu-id="66e20-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="66e20-157">Web.config 파일을 업데이트 한 후에는 Outlook Web App 풀을 재생 하기 위해 Exchange 백 엔드 서버에서 다음 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="66e20-158">재활용 작업에 성공 하면 Exchange 관리 셸에서 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="66e20-159">**Outlook Web App 사서함 정책 구성**</span><span class="sxs-lookup"><span data-stu-id="66e20-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="66e20-160">이 시점에서 다음 명령을 사용 하 여 적절 한 Outlook Web App 사서함 정책 (또는 정책)에서 인스턴트 메시지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-160">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="66e20-161">예를 들어 사서함 서버 중 하나에서이 명령을 실행 하 여 기본 정책에서 인스턴트 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-161">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="66e20-162">이 명령은 모든 Outlook Web App 사서함 정책에 대해 인스턴트 메시지를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="66e20-163">사서함 정책을 사용 하도록 설정한 후에는 해당 정책에서 관리 하는 모든 사용자가 Lync Server와 Outlook Web App 간에 완전 한 통합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="66e20-164">사용자에 게 Exchange 2013 사서함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="66e20-165">사용자가 Lync Server 2013에 대해 사용 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="66e20-166">사용자에 게 유효한 SIP 프록시 주소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="66e20-167">**Outlook Web App에서 인스턴트 메시지를 사용 하지 않도록 설정**</span><span class="sxs-lookup"><span data-stu-id="66e20-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="66e20-168">앞에서 설명한 대로 Outlook Web App에서 인스턴트 메시지는 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="66e20-169">즉, Outlook Web App을 Lync Server와 통합 하지 않으면 사용자가 Outlook Web App에 로그온 할 때마다 빈 현재 상태 아이콘과 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="66e20-170">이 문제를 방지 하려면 다음 Exchange 관리 셸 명령을 사용 하 여 Outlook web App에서 인스턴트 메시지를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="66e20-171">**Outlook Web App과 통합 확인**</span><span class="sxs-lookup"><span data-stu-id="66e20-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="66e20-172">인스턴트 메시지와 현재 상태가 Outlook Web App과 통합 되었는지 확인 하려면 Outlook Web App 2013에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="66e20-173">화면 오른쪽 위 모서리에 Exchange 표시 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="66e20-174">사용자 이름 옆에 현재 상태를 나타내는 녹색 아이콘이 있는 경우, 예를 들어 Lync Server 및 Outlook Web App이 성공적으로 통합 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="66e20-175">Outlook Web App에 초기 로그온 한 후 이벤트 ID 112 (및 원본 MSExchange OWA)를 사용 하는 이벤트가 사서함 서버의 이벤트 로그에 기록 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="66e20-176">이 이벤트는 메신저 끝점 관리자가 성공적으로 초기화 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="66e20-177">인스턴트 메시지를 사용할 수 없는 경우\\사서함 서버에서 C: Program files\\폴더에서 로그 파일을 찾습니다. Microsoft\\Exchange server\\V15\\로깅\\OWA\\InstantMessaging.</span><span class="sxs-lookup"><span data-stu-id="66e20-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="66e20-178">통합이 실패 했음을 나타내는 로깅 또는 InstantMessaging 폴더가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="66e20-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="66e20-179">이 경우 Lync Server에서 SIPStack 추적 (모든 수준 및 모든 플래그)을 사용 하 여 통합에 실패 한 이유를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e20-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

