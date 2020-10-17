---
title: 'Lync Server 2013: 자동 검색을 위한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502115"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="cbaa9-102">Lync Server 2013에서 자동 검색에 대 한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="cbaa9-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbaa9-103">_**마지막으로 수정 된 항목:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="cbaa9-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="cbaa9-104">디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 인증서에는 Lync 클라이언트와의 보안 연결을 지원 하기 위한 추가 주체 대체 이름 항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cbaa9-105"><STRONG>Get-CsCertificate</STRONG> cmdlet을 사용하여 현재 지정된 인증서에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="cbaa9-106">하지만 기본 보기에서는 인증서의 속성이 잘려서 표시되므로 SubjectAlternativeNames 속성의 모든 값이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="cbaa9-107"><STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate 및 <STRONG>Set-CsCertificate</STRONG> cmdlet을 사용하면 일부 정보를 보고 인증서를 요청 및 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="cbaa9-108">하지만 현재 인증서에 있는 SAN(주체 대체 이름)의 속성이 확실하지 않을 때는 최선의 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="cbaa9-109">인증서 및 모든 속성 구성원을 보려면 <EM>MMC (Microsoft Management Console)</EM> 에서 인증서 스냅인을 사용 하거나 Lync Server 배포 마법사를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="cbaa9-110">Lync Server 배포 마법사에서 인증서 마법사를 사용 하 여 인증서 속성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="cbaa9-111">Lync Server 관리 셸 및 <EM>MMC (Microsoft Management Console)</EM> 를 사용 하 여 인증서를 보거나 요청 하 고 할당 하는 절차는 다음 절차에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="cbaa9-112">Lync Server 배포 마법사를 사용 하려면 자세한 내용은 여기에서 추가 디렉터 또는 디렉터 풀을 배포한 경우 ( <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013에서 디렉터에 대 한 인증서 구성</A>)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="cbaa9-113">프런트 엔드 서버 또는 프런트 엔드 풀에 대 한 자세한 내용은 <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013에서 서버에 대 한 인증서 구성</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="cbaa9-114">이 절차의 시작 단계는 현재 인증서가 수행하는 역할을 확인하는 준비 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="cbaa9-115">기본적으로 인증서에는 lyncdiscover가 포함 되지 않습니다. &lt; microsoft.rtc.management.xds.sipdomain object &gt; 또는 lyncdiscoverinternal &lt; &gt; 이전에 모바일 서비스를 설치 하지 않았거나 인증서를 미리 준비 하지 않은 경우 내부 도메인 이름 항목</span><span class="sxs-lookup"><span data-stu-id="cbaa9-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="cbaa9-116">이 절차에서는 예제 SIP 도메인 이름 'contoso.com' 및 예제 내부 도메인 이름 'contoso.net'을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="cbaa9-117">Lync Server 2013 및 Lync Server 2010에 대 한 기본 인증서 구성은 용도 기본값 (웹 서비스를 제외한 모든 용도), WebServicesExternal 및 Web서비스 내부를 사용 하 여 단일 인증서 (이름이 ' Default ' 인 ' 기본값 ')를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="cbaa9-118">선택적인 구성은 각 용도에 대해 별도의 인증서를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="cbaa9-119">Lync Server 관리 셸 및 Windows PowerShell cmdlet을 사용 하거나 Lync Server 배포 마법사에서 인증서 마법사를 사용 하 여 인증서를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="cbaa9-120">Lync Server 관리 셸을 사용 하 여 새 주체 대체 이름을 사용 하 여 인증서를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="cbaa9-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="cbaa9-121">로컬 관리자 권한이 있는 계정을 사용하여 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="cbaa9-122">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cbaa9-p104">서버에 지정된 인증서 및 인증서를 사용할 유형을 확인합니다. 다음 단계에서 업데이트된 인증서를 지정하려면 이 정보가 필요합니다. 정보를 확인하려면 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="cbaa9-p105">이전 단계의 출력에서 단일 인증서가 여러 용도로 지정되어 있는지 또는 각 용도에 따라 서로 다른 인증서가 지정되어 있는지를 확인합니다. 또한 Use 매개 변수에서 인증서 사용 방법을 확인하고, 표시된 인증서의 Thumbprint 매개 변수를 비교해 같은 인증서가 여러 용도로 사용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="cbaa9-p106">명령줄에 다음을 입력하여 인증서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="cbaa9-131">예를 들어 **Get-CsCertificate** cmdlet을 실행한 결과 용도가 각각 Default, WebServicesInternal, WebServicesExternal인 인증서가 표시되었는데 이들 인증서의 Thumbprint 값은 모두 같은 경우에는 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="cbaa9-132">**중요:**</span><span class="sxs-lookup"><span data-stu-id="cbaa9-132">**Important:**</span></span>
    
    <span data-ttu-id="cbaa9-133">각 사용에 대해 별도의 인증서가 할당 된 경우 (각 인증서에 대해 손도장 값이 다른 경우) **set-cscertificate** cmdlet을 여러 형식으로 실행 하지 않는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="cbaa9-134">이 경우 각 사용에 대해 **set-cscertificate** cmdlet을 개별적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="cbaa9-135">예제:</span><span class="sxs-lookup"><span data-stu-id="cbaa9-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="cbaa9-p108">인증서를 보려면 **시작**, **실행…** 을 차례로 클릭하고 MMC를 입력해서 Microsoft Management Console을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="cbaa9-p109">MMC 메뉴에서 **파일**, **프로그램 스냅인 추가/제거…**, 인증서를 차례로 선택하고 **추가**를 클릭합니다. 프롬프트가 표시되면 **컴퓨터 계정**을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="cbaa9-141">인증서가이 컴퓨터에 있는 경우 **로컬 컴퓨터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="cbaa9-142">인증서가 다른 컴퓨터에 있는 경우 **다른 컴퓨터**를 선택 하 고 컴퓨터의 정규화 된 도메인 이름을 입력 하거나 **찾아보기를** 클릭 **하 여 선택할 개체 이름을 입력**합니다 .에서 컴퓨터의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="cbaa9-143">**이름 확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-143">Click **Check Names**.</span></span> <span data-ttu-id="cbaa9-144">컴퓨터 이름이 확인 되 면 밑줄이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="cbaa9-145">**확인**을 클릭 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="cbaa9-146">**확인** 을 클릭 하 여 선택 항목을 커밋하고 **스냅인 추가/제거** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cbaa9-147">인증서가 콘솔에 표시 되지 않으면 사용자 또는 서비스를 선택 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="cbaa9-148">컴퓨터를 선택 해야 하며, 그렇지 않으면 probper 인증서를 찾을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="cbaa9-p112">인증서의 속성을 보려면 **인증서**, **개인**을 차례로 확장하고 **인증서**를 선택합니다. 보려는 인증서를 선택하고 인증서를 마우스 오른쪽 단추로 클릭한 후 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="cbaa9-p113">**인증서** 보기에서 **자세히**를 선택합니다. 여기에서는 **주체**를 선택하여 인증서 주체 이름을 선택할 수 있고 지정된 주체 이름 및 연결된 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="cbaa9-153">지정된 주체 대체 이름을 보려면 **주체 대체 이름**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="cbaa9-154">지정된 모든 주체 대체 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="cbaa9-155">속성에서 발견되는 주체 대체 이름은 기본적으로 **DNS 이름** 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="cbaa9-156">다음과 같은 멤버가 표시됩니다(모든 멤버가 DNS 호스트(A 또는 IPv6인 경우 AAAA) 레코드에 표시된 대로 정규화된 도메인 이름으로 표시됨).</span><span class="sxs-lookup"><span data-stu-id="cbaa9-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="cbaa9-157">이 풀의 풀 이름 또는 단일 서버 이름(풀이 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="cbaa9-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="cbaa9-158">인증서가 지정된 서버 이름</span><span class="sxs-lookup"><span data-stu-id="cbaa9-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="cbaa9-159">단순 URL 레코드(일반적으로 meet 및 dialin)</span><span class="sxs-lookup"><span data-stu-id="cbaa9-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="cbaa9-160">웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의를 사용한 웹 서비스 선택에 대 한 선택 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="cbaa9-161">이미 지정 된 경우 lyncdiscover입니다.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="cbaa9-161">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="cbaa9-162">및 lyncdiscoverinternal입니다.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="cbaa9-162">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="cbaa9-163">레코드.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-163">records.</span></span>
    
    <span data-ttu-id="cbaa9-164">lyncdiscover 및 lyncdiscoverinternal SAN 항목이 있는 경우 마지막 항목이 가장 중요한 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-164">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="cbaa9-165">이러한 정보를 준비했으면 인증서 보기 및 MMC를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-165">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="cbaa9-166">자동 검색 서비스인 경우 lyncdiscover를 의미 합니다. \> 도메인 이름 \> 및 lyncdiscoverinternal.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="cbaa9-166">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\></span></span> <span data-ttu-id="cbaa9-167">(외부 또는 내부 인증서 인지에 따름) 주체 대체 이름이 누락 되었고 기본, Web서비스 내부 및 WebServiceExternal 형식에 대해 단일 기본 인증서를 사용 하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-167">(based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="cbaa9-168">Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-168">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="cbaa9-169">SIP 도메인이 많은 경우에는 새 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-169">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="cbaa9-170">대신, DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-170">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="cbaa9-171">DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover record에 대해 FQDN을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-171">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="cbaa9-172">예제:</span><span class="sxs-lookup"><span data-stu-id="cbaa9-172">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="cbaa9-173">인증서를 지정하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-173">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="cbaa9-174">"Thumbprint"는 새로 발급된 인증서에 표시되는 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-174">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="cbaa9-175">기본, WebServicesInternal 및 WebServicesExternal에 대해 개별 인증서를 사용할 때 내부 자동 검색 주체 대체 이름이 누락된 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-175">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="cbaa9-176">Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-176">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="cbaa9-p118">SIP 도메인이 여러 개인 경우 새 AllSipDomain 매개 변수는 사용할 수 없으며 대신 DomainName 매개 변수를 사용해야 합니다. DomainName 매개 변수를 사용할 때는 SIP 도메인 FQDN에 대해 적절한 접두사를 사용해야 합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p118">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="cbaa9-181">누락된 외부 자동 검색 주체 대체 이름에 대해 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-181">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="cbaa9-p119">SIP 도메인이 여러 개인 경우 새 AllSipDomain 매개 변수는 사용할 수 없으며 대신 DomainName 매개 변수를 사용해야 합니다. DomainName 매개 변수를 사용할 때는 SIP 도메인 FQDN에 대해 적절한 접두사를 사용해야 합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-p119">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="cbaa9-186">개별 인증서 유형을 지정하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-186">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="cbaa9-187">"Thumbprint"는 새로 발급된 인증서에 표시되는 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaa9-187">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

