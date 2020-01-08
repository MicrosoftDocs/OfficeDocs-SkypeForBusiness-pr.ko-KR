---
title: 'Lync Server 2013: 사전 인증서 요청(선택 사항)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6b376a2c1652dcaf255e39f6d112568b7c3bf31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="32136-102">Lync Server 2013에 대한 사전 인증서 요청(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="32136-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32136-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="32136-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="32136-104">각 Enterprise Edition 프런트 엔드 서버, Standard Edition Server, 디렉터, Edge 서버 및 독립 실행형 조정 서버를 포함 하 여 Lync Server 2013을 실행 하는 모든 내부 서버에 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="32136-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="32136-105">내부 서버에는 내부 엔터프라이즈 CA (인증 기관)가 권장 되지만 공용 CA를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32136-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="32136-106">인증서 요구 사항과 공개 CA 사용에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32136-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="32136-107">Lync Server 2013 설정에는 배포 중에 인증서 요청, 할당, 설치 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32136-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="32136-108">서버를 설치 하기 전에 인증서를 요청 하는 경우 (예를 들어 서버를 실제 배포 하는 동안 시간을 절약 하려면) Lync Server 2013 관리 도구가 설치 된 컴퓨터를 사용 하거나 인증서 요청을 사용 하 여 수행할 수 있습니다. 인증서를 내보낼 수 있고 필요한 모든 주체 대체 이름을 포함 하 고 있는지 확인 하는 경우 조직에 정의 된 절차</span><span class="sxs-lookup"><span data-stu-id="32136-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="32136-109">미리 인증서 요청은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="32136-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="32136-110">미리 요청 하지 않으면 인증서를 필요로 하는 각 서버 설정의 일부로 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32136-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="32136-111">이 배포 설명서에서는 인증서 마법사를 사용 하 여 설치 프로세스의 일부로 인증서를 요청 하는 절차를 제공 합니다. [Lync server 2013에서 서버의 인증서 구성](lync-server-2013-configure-certificates-for-servers.md), [lync Server 2013에서 디렉터에 대 한 인증서 구성](lync-server-2013-configure-certificates-for-the-director.md),이 배포 설명서의 [Lync server 2013에서 중재 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32136-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="32136-112">인증서를 미리 요청 하는 경우 배포 시 요청 하는 대신 해당 섹션의 인증서 배포 절차를 적절 하 게 수정 하 여 인증서를 가져오고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32136-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32136-113">Lync Server 2013에는 Windows Vista, Windows Server&nbsp;2008, windows server&nbsp;2008&nbsp;R2, Windows 7 운영 체제, Lync Phone Edition을 실행 하는 클라이언트의 연결에 대 한 SHA-256 인증서 지원이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32136-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="32136-114">SHA-256를 사용 하 여 외부 액세스를 지원 하기 위해 외부 인증서는 SHA-256를 사용 하 여 공용 CA에서 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="32136-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

