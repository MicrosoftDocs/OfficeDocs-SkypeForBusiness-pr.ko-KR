---
title: 경계 네트워크에 서버 설치 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a392cba4c6f955a166e93f93518faba540c1d9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="fccc8-102">Lync Server 2013에 대 한 경계 네트워크에 서버 설치 준비</span><span class="sxs-lookup"><span data-stu-id="fccc8-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fccc8-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="fccc8-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="fccc8-104">에지 서버 구성 요소를 설정하기 전에 설정 대상 컴퓨터가 시스템 요구 사항을 충족하는지 확인하고, 에지 서버 구성 요소 배포에 필요한 기타 필수 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fccc8-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="fccc8-105">시작하기 전에 계획 설명서의 다음 항목에서 배포하려는 참조 아키텍처에 대한 세부 정보를 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="fccc8-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="fccc8-106">Lync Server 2013의 개인 IP 주소 및 NAT를 포함 하는 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="fccc8-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="fccc8-107">Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="fccc8-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="fccc8-108">Lync Server 2013의 확장 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="fccc8-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="fccc8-109">Lync Server 2013의 확장 된 통합에 지, 공용 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="fccc8-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="fccc8-110">Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="fccc8-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="fccc8-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fccc8-111">In This Section</span></span>

  - [<span data-ttu-id="fccc8-112">Lync Server 2013에서에 지 지원에 대 한 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="fccc8-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="fccc8-113">Lync Server 2013에서 확장 된에 지 토폴로지에 대 한 하드웨어 부하 분산 장치 설정</span><span class="sxs-lookup"><span data-stu-id="fccc8-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="fccc8-114">Lync Server 2013에서 외부 사용자 액세스에 대 한 방화벽 및 포트 구성</span><span class="sxs-lookup"><span data-stu-id="fccc8-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="fccc8-115">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="fccc8-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="fccc8-116">Lync Server 2013의에 지 구성 요소에 대 한 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="fccc8-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

