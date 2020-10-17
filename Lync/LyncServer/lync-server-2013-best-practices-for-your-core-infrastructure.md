---
title: 'Lync Server 2013: 핵심 인프라에 대 한 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 087cfed02e3b28df88508446c57e451f42ef067c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513005"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="a8bce-102">Lync Server 2013의 핵심 인프라에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="a8bce-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8bce-103">_**마지막으로 수정 된 항목:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="a8bce-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="a8bce-104">하드웨어 중복성을 보장하거나 전력 손실에 대비하거나 보안 업데이트 및 바이러스 백신 수단을 정기적으로 설치하거나 서버 활동을 모니터링하는 등의 방법을 사용하여 시스템에서 내결함성을 설계하기 위한 조치를 이미 수행했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="a8bce-105">이러한 방법은 Microsoft Lync Server 2013 인프라 뿐 아니라 전체 네트워크에도 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="a8bce-106">이러한 방법을 구현 하지 않은 경우 Lync Server 2013을 배포 하기 전에 먼저 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="a8bce-107">Lync Server 2013 배포의 서버가 가동 중지 시간을 일으킬 수 있는 우발적 이거나 고의적 피해 로부터 보호 하려면 다음과 같은 예방 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="a8bce-108">보안 업데이트를 사용하여 서버를 최신 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="a8bce-109">Microsoft Security Notification Service를 구독하면 Microsoft 제품의 보안 게시판 릴리스에 대한 알림을 즉각적으로 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="a8bce-110">구독 하려면에서 Microsoft 기술 보안 알림 웹 사이트로 이동 [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-110">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="a8bce-111">액세스 권한이 올바르게 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="a8bce-p103">실제 환경에서 서버에 무단으로 액세스하지 못하도록 관리합니다. 모든 서버에 적절한 바이러스 백신 소프트웨어가 설치되어 있는지 확인합니다. 소프트웨어를 최신 상태로 유지하고 바이러스 서명 파일이 최신 버전인지 확인합니다. 바이러스 백신 응용 프로그램의 자동 업데이트 기능을 사용하여 바이러스 서명을 최신 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="a8bce-116">Lync Server 2013을 설치 하는 컴퓨터에는 필요 하지 않은 Windows Server 운영 체제 서비스를 사용 하지 않도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="a8bce-117">서버에 대한 지속적이고 완전한 제어, 완벽한 물리적 격리 및 교체 또는 장애가 발생한 디스크 드라이브에 대한 적절하고 안전한 해제를 보장할 수 있지 않은 한 전체 볼륨 암호화 시스템에서 데이터가 저장되는 운영 체제 및 디스크 드라이브를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="a8bce-118">서버에 대한 물리적 액세스를 매우 긴밀하게 제어할 수 있도록 보장하지 않는 한 서버의 모든 외부 DMA(Direct Memory Access) 포트를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="a8bce-119">상당히 쉽게 개시할 수 있는 DMA 기반 공격은 개인 암호화 키와 같은 매우 민감한 정보를 노출시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8bce-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

