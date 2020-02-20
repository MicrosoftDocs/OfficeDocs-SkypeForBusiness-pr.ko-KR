---
title: 'Lync Server 2013: 사전 인증서 요청 (선택 사항)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd3bda5e7ea4169af0abb173befc9b91ccfb7c22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="c2489-102">Lync Server 2013에 대해 사전 인증서 요청 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c2489-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2489-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c2489-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c2489-104">각 Enterprise Edition 프런트 엔드 서버, Standard Edition Server, 디렉터,에 지 서버 및 독립 실행형 중재 서버를 포함 하 여 Lync Server 2013을 실행 하는 모든 내부 서버에 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="c2489-105">내부 서버에는 내부 엔터프라이즈 CA(인증 기관)를 사용하는 것이 좋지만 공용 CA를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="c2489-106">인증서 요구 사항 및 공용 CA 사용에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2489-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="c2489-107">Lync Server 2013 설치 프로그램에는 배포 중에 인증서를 요청, 할당 및 설치 하는 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="c2489-108">서버를 설치 하기 전에 인증서를 요청 하려는 경우 (예를 들어 서버를 실제 배포 하는 동안 시간을 절약 하기 위해) Lync Server 2013 관리 도구를 설치 하거나 인증서 요청을 사용 하 여 컴퓨터를 사용 하 여이 작업을 수행할 수 있습니다. 인증서가 내보낼 수 있고 필요한 모든 주체 대체 이름을 포함 하 고 있는지 확인 하는 경우 조직에 정의 된 절차</span><span class="sxs-lookup"><span data-stu-id="c2489-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="c2489-109">사전에 인증서를 요청 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="c2489-110">이를 사전에 요청 하지 않으면 인증서가 필요한 각 서버 설정의 일부로 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="c2489-111">이 배포 설명서에서는이 배포 설명서의 lync server [2013에서 서버에 대](lync-server-2013-configure-certificates-for-servers.md)한 인증서 구성, lync [Server 2013의 디렉터에 대 한 인증서 구성](lync-server-2013-configure-certificates-for-the-director.md), [중재 2013 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md) 의 설명에 따라 인증서 마법사를 사용 하 여 인증서를 설치 프로세스의 일부로 요청 하는 절차를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="c2489-112">인증서를 사전에 요청하려면 배포 시 인증서를 요청하는 대신 인증서를 가져오고 할당하는 관련 섹션에서 인증서 배포 절차를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2489-113">Lync Server 2013에는 Windows Vista, Windows Server&nbsp;2008, windows server&nbsp;2008&nbsp;R2 및 Windows 7 운영 체제 및 Lync Phone Edition을 실행 하는 클라이언트의 연결에 대 한 SHA-256 인증서에 대 한 지원이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="c2489-114">SHA-256을 사용한 외부 액세스를 지원하기 위해 SHA-256을 사용하여 공용 CA에서 외부 인증서가 발급됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2489-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

