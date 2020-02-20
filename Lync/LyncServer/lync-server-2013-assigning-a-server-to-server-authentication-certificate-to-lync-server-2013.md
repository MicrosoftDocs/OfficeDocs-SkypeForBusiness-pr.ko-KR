---
title: Lync Server 2013에 서버 간 인증 인증서 할당
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d82974f45ab06024f2834609403ed6604067bb2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="d829f-102">Microsoft Lync Server 2013에 서버 간 인증 인증서 할당</span><span class="sxs-lookup"><span data-stu-id="d829f-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d829f-103">_**마지막으로 수정 된 항목:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="d829f-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="d829f-104">서버 간 인증 인증서가 Microsoft Lync Server 2013에 이미 할당 되어 있는지 여부를 확인 하려면 Lync Server 2013 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="d829f-105">반환되는 인증서 정보가 없으면 토큰 발급자 인증서를 먼저 할당해야 서버 간 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="d829f-106">일반적으로 모든 Lync Server 2013 인증서는 OAuthTokenIssuer 인증서로 사용할 수 있습니다. 예를 들어 Lync Server 2013 기본 인증서는 OAuthTokenIssuer 인증서로도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="d829f-107">(OAUthTokenIssuer 인증서는 주체 필드에 SIP 도메인 이름을 포함 하는 모든 웹 서버 인증서 일 수도 있습니다.) 서버 간 인증에 사용 되는 인증서에 대 한 주요 두 가지 요구 사항은 다음과 같습니다. 1) 모든 프런트 엔드 서버에서 동일한 인증서를 OAuthTokenIssuer 인증서로 구성 해야 합니다. 2) 인증서는 최소 2048 비트 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="d829f-p102">서버 간 인증에 사용할 수 있는 인증서가 없는 경우 새로운 인증서를 받아 가져온 다음 서버 간 인증의 인증서로 사용해야 합니다. 새 인증서를 요청하여 받으면 새 인증서로 프런트 엔드 서버 중 하나에 로그온할 수 있으며, 다음과 유사한 Windows PowerShell 명령을 사용하여 인증서를 가져오고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="d829f-p103">이전 명령에서 Path 매개 변수는 인증서 파일의 전체 경로를 나타내고 Password 매개 변수는 인증서에 할당된 암호를 나타냅니다. 이러한 절차는 단 한 번만 실행해야 합니다. Lync Server의 복제 서비스를 통해 인증서를 모든 프런트 엔드 서버에 배포하고 해독하는 예약 작업이 자동으로 만들어지기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-p103">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate. This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="d829f-p104">또는, 기존 인증서를 서버 간 인증 인증서로 사용할 수 있습니다. 앞에서 언급한 것과 같이 기본 인증서도 서버 간 인증 인증서로 사용할 수 있습니다. 다음 Windows PowerShell 명령 쌍을 실행하면 기본 인증서의 Thumbprint 속성 값을 검색한 후 해당 값을 사용하여 기본 인증서를 서버 간 인증 인증서로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="d829f-p105">이전 명령에서 검색된 인증서는 전역 서버 간 인증 인증서 역할을 하도록 구성됩니다. 즉, 인증서가 모든 프런트 엔드 서버에 복제되어 사용된다는 의미입니다. 다시 강조하자면 이 명령은 프런트 엔드 서버 중 하나에서 단 한 번만 실행해야 합니다. 모든 프런트 엔드 서버에서 동일한 인증서를 사용해야 하지만 각 프런트 엔드 서버에서 OAuthTokenIssuer 인증서를 구성해서는 안 됩니다. 대신, 인증서 하나를 구성하고 Lync Server의 복제 서버를 통해 각 서버로 해당 인증서가 자동 복사되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-p105">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers. Again, this command should only be run one time, and only on one of your Front End Servers. Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server. Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="d829f-118">Set-cscertificate cmdlet은 해당 인증서를 즉시 가져와서 현재 OAuthTokenIssuer 인증서로 작동 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="d829f-119">(Lync Server 2013에서는 현재 인증서와 이전 인증서의 두 복사본을 유지 합니다.) 새 인증서가 OAuthTokenIssuer 인증서 역할을 즉시 시작 해야 하는 경우 Set-cscertificate cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="d829f-p107">또한 Set-CsCertificate cmdlet을 사용하여 새 인증서를 "롤링"할 수 있습니다. 인증서를 "롤링"한다는 것은 단순히, 지정된 시점에 새 인증서를 현재 OAuthTokenIssuer 인증서로 사용하도록 구성한다는 의미입니다. 예를 들어 다음 명령을 실행하면 기본 인증서가 검색된 후 해당 인증서가 2012년 7월 1일을 기준으로 현재 OAuthTokenIssuer 인증서로 사용되도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="d829f-123">2012년 7월 1일에 새 인증서는 현재 OAuthTokenIssuer 인증서로 구성되고 "기존" OAuthTokenIssuer 인증서는 이전 인증서로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="d829f-p108">Windows PowerShell을 사용하지 않으려는 경우 인증서 MMC 콘솔을 사용하여 인증서를 단일 프런트 엔드 서버에서 내보내어 동일한 인증서를 다른 모든 프런트 엔드 서버로 가져올 수도 있습니다. 이를 수행하는 경우 반드시 인증서 자체와 함께 개인 키를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="d829f-126">이러한 경우 절차는 각 프런트 엔드 서버에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="d829f-127">이 방식으로 인증서를 내보내고 가져올 때 Lync Server 2013에서는 해당 인증서를 각 프런트 엔드 서버로 복제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="d829f-128">모든 프런트 엔드 서버로 인증서를 가져온 후에는 Windows PowerShell 대신 Lync Server 배포 마법사를 사용 하 여 해당 인증서를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="d829f-129">배포 마법사를 사용하여 인증서를 할당하려면 배포 마법사가 설치된 컴퓨터에서 다음 단계를 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="d829f-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="d829f-130">시작, 모든 프로그램, **Microsoft Lync server 2013**, **Lync server 배포 마법사**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="d829f-131">배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="d829f-132">Microsoft Lync Server 2013 페이지에서 제목 **3 단계: 인증서 요청, 설치 또는 할당**에서 **실행** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="d829f-133">참고: 이 컴퓨터에서 인증서를 이미 설치한 경우 **실행** 단추 대신 **다시 실행**이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="d829f-134">인증서 마법사에서 **OAuthTokenIssuer** 인증서를 선택한 후 **지정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="d829f-135">인증서 할당 마법사의 **인증서 할당** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="d829f-136">**인증서 저장소** 페이지에서 서버 간 인증에 사용할 인증서를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="d829f-137">인증서 할당 요약 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="d829f-138">명령 실행 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="d829f-139">인증서 마법사와 배포 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d829f-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

