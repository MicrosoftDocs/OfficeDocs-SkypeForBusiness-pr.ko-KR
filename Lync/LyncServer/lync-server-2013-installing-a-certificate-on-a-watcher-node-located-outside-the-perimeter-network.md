---
title: 'Lync Server 2013: 경계 네트워크 외부에 있는 감시자 노드에 인증서 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4704cc5284b6923967e530492edf2a07054a2a19
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="0391d-102">Lync Server 2013의 경계 네트워크 외부에 있는 감시자 노드에 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="0391d-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0391d-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0391d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0391d-104">주변 네트워크 (예: Lync Server에 지 서버)에서 실행 되는 System Center Operations Manager 에이전트 (예: 외부 가상 트랜잭션 감시자 노드 등) 또는 Active Directory 도메인 서비스 트러스트 경계를 넘어 작업을 수행 해야 할 수 있습니다. System Center Operations Manager 게이트웨이 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0391d-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="0391d-105">이 서버 역할을 통해 루트 관리 서버와의 트러스트 관계가 없는 에이전트가 알림을 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0391d-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="0391d-106">자세한 내용은 System Center Operations Manager TechNet 라이브러리의 "Operations Manager에서 게이트웨이 서버 관리 2007"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span><span class="sxs-lookup"><span data-stu-id="0391d-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="0391d-107">이러한 위치 중 하나에 에이전트를 배포 하는 경우에는 감시자 노드가 System Center Operations Manager에 알림을 보낼 수 있도록 하는 인증서도 요청 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0391d-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="0391d-108">이 프로세스를 간소화하기 위해 Operations Manager 팀은 감시자 노드 컴퓨터에 올바른 유형의 인증서를 요청하고 설치할 수 있게 해주는 유틸리티 집합을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="0391d-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="0391d-109">자세한 내용을 확인 하 고 이러한 유틸리티를 다운로드 하려면에서 [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421)블로그 문서를 사용 하 여 쉽게 사용할 수 있는 비도메인 구독 에이전트에 대 한 인증서 얻기 "를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0391d-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

