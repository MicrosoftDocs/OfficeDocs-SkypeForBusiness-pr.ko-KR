---
title: 'Lync Server 2013: 핵심 인프라에 대 한 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="83d51-102">Lync Server 2013의 핵심 인프라에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="83d51-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83d51-103">_**마지막으로 수정한 주제:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="83d51-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="83d51-104">하드웨어 중복성 보장, 정전 으로부터 보호, 보안 업데이트 및 바이러스 백신 조치, 서버 활동 모니터링 등의 방법을 사용 하 여 시스템에서 내결함성 설계 단계를 이미 수행 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="83d51-105">이러한 방법을 통해 Microsoft Lync Server 2013 인프라 뿐 아니라 전체 네트워크도 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="83d51-106">이러한 방법을 구현 하지 않은 경우 Lync Server 2013를 배포 하기 전에이 방법을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="83d51-107">Lync Server 2013 배포의 서버에서 가동 중지 시간이 발생할 수 있는 우발적 이거나 체계적 손상 으로부터 보호 하기 위해 다음과 같은 예방 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="83d51-108">보안 업데이트를 사용 하 여 서버를 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="83d51-109">Microsoft 보안 알림 서비스에 가입 하면 Microsoft 제품에 대 한 보안 공지 릴리스 알림을 즉시 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="83d51-110">구독 하려면 Microsoft 기술 보안 알림 웹 사이트를 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span><span class="sxs-lookup"><span data-stu-id="83d51-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="83d51-111">액세스 권한이 올바르게 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="83d51-112">무단 액세스를 방지 하는 물리적 환경에서 서버를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-112">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="83d51-113">모든 서버에 적절 한 바이러스 백신 소프트웨어가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-113">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="83d51-114">최신 바이러스 서명 파일을 사용 하 여 소프트웨어를 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-114">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="83d51-115">바이러스 백신 응용 프로그램의 자동 업데이트 기능을 사용 하 여 바이러스 서명을 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-115">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="83d51-116">Lync Server 2013을 설치 하는 컴퓨터에서는 필요 하지 않은 Windows Server 운영 체제 서비스를 사용 하지 않도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="83d51-117">서버를 일관 되 게 제어 하 고 완전 한 격리, 대체 또는 실패 한 디스크의 적절 하 고 안전 하 게 폐기 하지 않는 한, 전체 볼륨 암호화 시스템을 사용 하 여 데이터가 저장 되는 운영 체제와 디스크 드라이브를 암호화 합니다. 드라이브나.</span><span class="sxs-lookup"><span data-stu-id="83d51-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="83d51-118">서버에 대 한 물리적 액세스를 매우 엄격 하 게 제어할 수 있는 경우가 아니면 서버의 모든 외부 직접 메모리 액세스 (DMA) 포트를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="83d51-119">비교적 쉽게 초기화할 수 있는 DMA 기반 공격으로, 개인 암호화 키와 같은 중요 한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d51-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

