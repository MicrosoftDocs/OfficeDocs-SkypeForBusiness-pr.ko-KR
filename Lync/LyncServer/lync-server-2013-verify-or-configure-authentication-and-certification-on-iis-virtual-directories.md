---
title: 'Lync Server 2013: IIS 가상 디렉터리에 대한 인증 확인 또는 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="1f738-102">Lync Server 2013에서 IIS 가상 디렉터리에 대한 인증 확인 또는 구성</span><span class="sxs-lookup"><span data-stu-id="1f738-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f738-103">_**마지막으로 수정한 주제:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="1f738-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="1f738-104">IIS (인터넷 정보 서비스) 가상 디렉터리에서 인증서를 구성 하거나 인증서가 올바르게 구성 되었는지 확인 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="1f738-105">내부 Lync Server 풀과 선택적 디렉터 또는 디렉터 풀 서버에서 IIS를 실행 하는 각 서버에 대해 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f738-106">다음 절차에서는 IIS의 모든 용도 Lync Server, 내부 웹 사이트 및 외부 웹 사이트에 사용 되는 조합 된 인증서를 요청 하는 절차를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="1f738-107">Lync Server 2010에서 인증서 요청, 가져오기, 할당을&nbsp;관리 하는 express 목적을 위한 Lync Server 관리 셸 Windows PowerShell cmdlet 집합을 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="1f738-108">이 절차에서는 요청을 처리할 수 있는 내부적으로 배포 된 CA (인증 기관)가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="1f738-109">Lync Server 목적으로 공용 인증서를 사용 하거나 CA에 오프 라인 요청이 필요한 경우 – Output 매개 변수에 대 한 자세한 내용은이 항목의 자세한 구문을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f738-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="1f738-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">요청-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="1f738-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="1f738-111">IIS 가상 디렉터리에 대 한 인증 및 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="1f738-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="1f738-112">다음을 성공적으로 완료 하려면 웹 서비스가 설치 된 컴퓨터 (프런트 엔드 서버 또는 디렉터)에 로그온 하 여 로컬 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="1f738-113">인증 기관이 조직의 인증 기관에 해당 하는 경우 인증서를 요청할 인증 기관에 대 한 **읽기** 및 **등록** 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="1f738-114">오프 라인 인증서 요청을 구성 하 고 보내는 경우에는 인증 기관에 대 한 사용 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="1f738-115">**시작**을 클릭 하 고 **모든 프로그램**을 선택한 다음 **관리 도구**를 선택 하 고 **IIS (인터넷 정보 서비스) 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="1f738-116">**IIS (인터넷 정보 서비스) 관리자**에서 **ServerName**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="1f738-117">**기능 보기**에서 **서버 인증서**를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **기능 열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1f738-118">서버 인증서 기능 보기에서 서버에 할당 된 인증서가 있는 경우 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="1f738-119">IIS에서 외부 웹 사이트의 요구 사항과 일치 하는 인증서가 있는 경우 해당 인증서를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="1f738-120">인증서를 보려면 인증서를 마우스 오른쪽 단추로 클릭 하 고 <STRONG>보기 ...</STRONG> 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="1f738-121">인증서를 요청 하는 프런트 엔드 서버 또는 디렉터에서 **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft lync server 2013**을 차례로 선택한 다음 **Lync server Management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="1f738-122">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="1f738-123">출력은 컴퓨터 개인 인증서 저장소에서 현재 서버에 있는 인증서의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="1f738-124">조합 된 인증서 (즉, 기본 웹 서비스 내부 및 웹 서비스 외부에 동일한 인증서를 사용 하는 경우)에는 Use 속성이 기본 인 Web서비스 내부 및 Webservice외부 Nal으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="1f738-125">또한 손도장 속성은 각 사용 유형에 대해 동일 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="1f738-126">이 예제에는 Get-CsCertificate의 예제 출력이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="1f738-127">현재 ![scert 상태에 대 한 CsCertificate 정보]가져오기-(images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "CsCertificate 정보 (현재 scert 상태)")</span><span class="sxs-lookup"><span data-stu-id="1f738-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="1f738-128">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="1f738-129">예를 들어 다음 예제와 같이 전체 명령이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1f738-130">기본적으로 CsCertificate에서는 주체 이름을 서버 또는 풀 이름으로 채우고, 주체 대체 이름의 항목을 서버 FQDN, 풀 FQDN, 간단한 URL Fqdn, 내부 및 외부 웹 서비스 Fqdn으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="1f738-131">이는 배포의 토폴로지 문서를 참조 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="1f738-132">누락 된 값이 있고 – Verbose 매개 변수를 지정한 경우 대체 이름에 대 한 계산 된 값과 실제 값이 서로 다르지만 사용자에 게 어떤 값이 누락 되지 않았음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="1f738-133">Cmdlet이 참조 하는 계산 된 전체 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="1f738-134">출력에 계산 된 대체 이름 문자열을 사용 하 여 모든 값을 포함할 새 인증서를 다시 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="1f738-135">(images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "요청-CsCertifica를 사용 하 여 인증서 요청의 CsCertifica 출력을") ![사용 하 여 인증서 요청의 출력]</span><span class="sxs-lookup"><span data-stu-id="1f738-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="1f738-136">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="1f738-137">예를 들어 다음 예제와 같이 전체 명령이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="1f738-138">CsCertificate cmdlet의 출력은 기본, Webservice외부의 Nal 및 Web서비스 내부 사용에 대해 동일한 인증서 (인증서의 손도장으로 식별 됨)를 할당 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="1f738-139">(images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Iis WebExt에서 CsCertificate") 의 ![iis webext 출력에 대 한 Set CsCertificate의 출력]</span><span class="sxs-lookup"><span data-stu-id="1f738-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="1f738-140">IIS 가상 디렉터리에서 인증 및 인증서를 확인 하거나 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="1f738-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="1f738-141">**시작**을 클릭 하 고 **모든 프로그램**을 선택한 다음 **관리 도구**를 선택 하 고 **IIS (인터넷 정보 서비스) 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="1f738-142">**IIS (인터넷 정보 서비스) 관리자**에서 **ServerName**을 확장 한 다음 **사이트**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="1f738-143">**Lync Server 외부 웹 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **바인딩 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="1f738-144">Https가 포트 4443와 연결 되어 있는지 확인 한 다음 **https**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="1f738-145">HTTPS 항목을 선택 하 고 **편집**을 클릭 한 다음 Lync Server WebServicesExternalCertificate이이 프로토콜에 바인딩되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="1f738-146">CsCertificate cmdlet의 지문을 비교 하 여 필요한 인증서가 HTTPS 바인딩과 올바르게 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f738-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f738-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f738-147">See Also</span></span>


[<span data-ttu-id="1f738-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1f738-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="1f738-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1f738-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

