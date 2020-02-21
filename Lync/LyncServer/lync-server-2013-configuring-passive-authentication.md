---
title: 'Lync Server 2013: 수동 인증 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96c2c94bde12e6b8b77060a82f1990b673421de9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="eb00a-102">Lync Server 2013 수동 인증 구성</span><span class="sxs-lookup"><span data-stu-id="eb00a-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb00a-103">_**마지막으로 수정 된 항목:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="eb00a-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="eb00a-104">다음 섹션에서는 수동 인증을 지원 하기 위해 6 월 2013 인 Lync Server 2013을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="eb00a-105">2 단계 인증을 사용 하도록 설정한 Lync 사용자는 실제 또는 가상 스마트 카드와 유효한 PIN을 사용 하 여 누적 업데이트를 사용한 Lync 2013을 사용 하 여 로그인 해야 합니다 (예: 7 2013 월 클라이언트).</span><span class="sxs-lookup"><span data-stu-id="eb00a-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="eb00a-106">고객은 서비스 수준에서 등록자 및 웹 서비스에 대해 수동 인증을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="eb00a-107">전역 수준에서 등록자 및 웹 서비스에 대해 수동 인증을 사용 하도록 설정 하는 경우, 누적 업데이트를 사용 하 여 Lync 2013을 사용 하 여 로그인 하지 않은 사용자에 대 한 조직 전체 인증 오류가 발생할 수 있습니다 (예: 2013 클라이언트 데스크톱 클라이언트).</span><span class="sxs-lookup"><span data-stu-id="eb00a-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="eb00a-108">웹 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="eb00a-108">Web Service Configuration</span></span>

<span data-ttu-id="eb00a-109">다음 단계에서는 수동 인증을 사용 하도록 설정 되는 디렉터, 엔터프라이즈 풀 및 Standard Edition server에 대 한 사용자 지정 웹 서비스 구성을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="eb00a-110">**사용자 지정 웹 서비스 구성을 만들려면**</span><span class="sxs-lookup"><span data-stu-id="eb00a-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="eb00a-111">Lync 관리자 계정을 사용 하 여 Lync Server 2013에 누적 업데이트: 7 월 2013 프런트 엔드 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="eb00a-112">Lync Server 2013 관리 셸을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="eb00a-113">Lync Server 관리 셸 명령줄에서 다음 명령을 실행 하 여 수동 인증을 사용 하도록 설정 될 각 디렉터, 엔터프라이즈 풀 및 Standard Edition Server에 대 한 새 웹 서비스 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="eb00a-114">WsFedPassiveMetadataUri FQDN의 값은 AD FS 2.0 서버의 페더레이션 서비스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="eb00a-115">페더레이션 서비스 이름 값은 탐색 창에서 <STRONG>서비스</STRONG> 를 마우스 오른쪽 단추로 클릭 하 고 <STRONG>페더레이션 서비스 속성 편집</STRONG>을 선택 하 여 AD FS 2.0 관리 콘솔에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="eb00a-116">다음 명령을 실행 하 여 UseWsFedPassiveAuth 및 WsFedPassiveMetadataUri 값이 올바르게 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="eb00a-117">클라이언트의 경우 wep 티켓 인증을 위해 기본 인증 방법이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="eb00a-118">수동 인증을 사용 하도록 설정 되는 모든 디렉터, Enterprise 풀 및 Standard Edition 서버에 대해 다음 명령을 실행 하 여 Lync 웹 서비스에서 다른 모든 인증 유형을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="eb00a-119">다음 명령을 실행 하 여 다른 모든 인증 유형이 사용 하지 않도록 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="eb00a-120">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="eb00a-120">Proxy Configuration</span></span>

<span data-ttu-id="eb00a-121">Lync 웹 서비스에 대해 인증서 인증을 사용 하지 않는 경우 Lync 클라이언트는 Kerberos 또는 NTLM과 같은 덜 기본 인증 유형을 사용 하 여 등록자 서비스에 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="eb00a-122">그러나 클라이언트에서 webticket을 검색할 수 있도록 하기 위해 인증서 인증은 여전히 필요 하지만, 등록자 서비스에 대해 Kerberos 및 NTLM을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="eb00a-123">다음 단계에서는 수동 인증을 사용 하도록 설정 되는에 지 풀, 엔터프라이즈 풀 및 Standard Edition server에 대 한 사용자 지정 프록시 구성을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="eb00a-124">**사용자 지정 프록시 구성을 만들려면**</span><span class="sxs-lookup"><span data-stu-id="eb00a-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="eb00a-125">Lync Server 관리 셸 명령줄에서 다음을 실행 하 여 수동 인증을 사용할 수 있는 누적 업데이트를 사용 하 여 각 Lync Server 2013에 대 한 새 프록시 구성 (예: 2013에 지 풀, 엔터프라이즈 풀 및 Standard Edition Server)을 만듭니다. 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="eb00a-126">다음 명령을 실행 하 여 다른 모든 프록시 인증 유형이 사용 하지 않도록 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb00a-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

