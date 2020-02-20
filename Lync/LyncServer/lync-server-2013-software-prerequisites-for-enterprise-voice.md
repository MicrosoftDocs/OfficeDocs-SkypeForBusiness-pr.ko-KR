---
title: 'Lync Server 2013: Enterprise Voice에 대 한 소프트웨어 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36ec427751fc6593f03af11bfecddf3bd0bb6280
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="76a71-102">Lync Server 2013의 Enterprise Voice에 대 한 소프트웨어 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="76a71-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76a71-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="76a71-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="76a71-104">Enterprise Voice를 배포하려는 인프라가 다음의 소프트웨어 필수 구성 요소를 충족하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="76a71-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="76a71-105">Lync Server 2013 Standard Edition 또는 Enterprise Edition이 설치 되어 있고 네트워크에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="76a71-106">모든에 지 서버는 액세스에 지 서비스를 실행 하는에 지 서버, A/V에 지 서비스, 웹 회의에 지 서비스 및 역방향 프록시를 포함 하는 경계 네트워크에서 배포 및 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="76a71-107">Microsoft Exchange server 2007 SP3 (서비스 팩 3), microsoft exchange server 2010 또는 Microsoft Exchange Server 2013은 Exchange 통합 메시징을 Lync Server와 통합 하 고 자세한 알림을 제공 하 고 다음에 대 한 로그 정보를 호출 하는 데 필요 합니다. Lync 끝점</span><span class="sxs-lookup"><span data-stu-id="76a71-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="76a71-108">Lync Server에 대해 하나 이상의 사용자를 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="76a71-109">Lync 클라이언트 및 장치를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="76a71-110">토폴로지 작성기가 네트워크의 서버에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="76a71-111">다음 단계: 보안 및 구성 필수 구성 요소 확인</span><span class="sxs-lookup"><span data-stu-id="76a71-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="76a71-112">Enterprise Voice에 대한 소프트웨어 필수 구성 요소를 확인한 후에는 설명서를 사용하여 Enterprise Voice 배포 준비를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="76a71-113">[Lync Server 2013의 Enterprise Voice에 대 한 보안 및 구성 선행 조건](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)environmental prerequisites for에 설명 된 대로 보안, 사용자 구성 및 하드웨어를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="76a71-114">배치 된 때 중재 서버가 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치 된 경우에만, 독립 실행형 중재 서버 또는 풀을 배포 하려는 경우에 *만* [2013](lync-server-2013-install-the-files-for-mediation-server.md)에 설명 된 대로 중재 서버를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="76a71-115">[Lync Server 2013에서 트렁크을 구성](lync-server-2013-configuring-trunks.md)하는 방법에 설명 된 대로 사용자에 게 PSTN 연결을 제공 하도록 트렁크 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a71-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

