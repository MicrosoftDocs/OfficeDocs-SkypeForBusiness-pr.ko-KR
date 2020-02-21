---
title: 'Lync Server 2013: 프런트 엔드 풀 연결 데이터 보안'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 503a5a02d4412fe2bbbf5f1882e3d7d117640576
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="4df26-102">Lync Server 2013의 프런트 엔드 풀 연결 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="4df26-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4df26-103">_**마지막으로 수정 된 항목:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="4df26-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="4df26-104">백업 서비스는 재해 복구를 위해 두 개의 쌍으로 연결 된 프런트 엔드 풀 사이에 사용자 데이터 및 전화 회의 콘텐츠를 지속적으로 전송 하는 Lync Server 2013에 도입 되는 데이터 복제 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="4df26-105">사용자 데이터에는 사용자 SIP Uri 뿐 아니라 대화 상대 목록 및 설정도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="4df26-106">회의 콘텐츠에는 Microsoft PowerPoint 2010 업로드 뿐 아니라 회의에 사용 되는 화이트 보드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="4df26-107">원본 풀에서 사용자 데이터 및 회의 콘텐츠는 대상 풀로 전송 되는 로컬 저장소에서 내보내집니다 (압축을 푼 후 로컬 저장소로 가져옴).</span><span class="sxs-lookup"><span data-stu-id="4df26-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="4df26-108">백업 서비스에서는 두 데이터 센터 간의 통신 링크가 인터넷에서 보호 되는 회사 네트워크 내에 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="4df26-109">두 데이터 센터 간에 전송 된 데이터는 암호화 되지 않으며 HTTPS와 같은 보안 프로토콜 내에서 고유 하 게 캡슐화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="4df26-110">따라서 회사 네트워크 내에서 내부 담당자의 중간자가 중간에 침입을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="4df26-111">보안 위험 평가</span><span class="sxs-lookup"><span data-stu-id="4df26-111">Evaluating Security Risks</span></span>

<span data-ttu-id="4df26-112">여러 데이터 센터에 Lync Server 2013을 배포 하 고 재해 복구 기능을 사용 하는 모든 엔터프라이즈는 회사 인트라넷에서 데이터 센터 트래픽이 보호 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="4df26-113">내부 공격 보호에 주의를 기울여야 하는 기업은 데이터 센터 간의 통신 연결을 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="4df26-114">기업의 데이터 센터가 회사 인트라넷에서 보호 되는 표준은 표준 이라는 가정입니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="4df26-115">이러한 데이터 센터 간에 전송 되는 회사의 중요 한 데이터에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="4df26-116">엔터프라이즈의 IT 인프라는 이러한 크로스 데이터 센터 링크가 보호 되지 않는 dire 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="4df26-117">회사 네트워크 내에서 중간자 (man-in-the-middle) 공격의 위험은 인터넷에 트래픽을 노출 하는 것과 비교 하 여 상대적으로 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="4df26-118">특히, 백업 서비스 (예: SIP Uri)가 제공 하는 사용자 데이터는 일반적으로 회사 내의 모든 직원이 Exchange 또는 기타 디렉터리 소프트웨어용 글로벌 주소록과 같은 다른 수단을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="4df26-119">따라서 백업 서비스가 두 개의 연결 된 풀 간에 데이터를 복사 하는 데 사용 되는 경우 두 데이터 센터 간의 WAN 보안에 중점을 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="4df26-120">보안 위험 완화</span><span class="sxs-lookup"><span data-stu-id="4df26-120">Mitigating Security Risks</span></span>

<span data-ttu-id="4df26-121">데이터 센터에 대 한 액세스 제한에서 두 데이터 센터 간의 WAN 전송 보안을 보호 하는 것과 같은 다양 한 방법으로 백업 서비스 트래픽에 대 한 보안 보호를 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="4df26-122">대부분의 경우 기업이 Lync Server 2013를 배포 하는 데 필요한 보안 인프라가 이미 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="4df26-123">지침을 찾는 엔터프라이즈의 경우 Microsoft는 보안 IT 인프라를 구축 하는 방법의 예제로 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="4df26-124">그러나이는 유일한 해결책이 아니며 Lync Server에 대 한 기본 솔루션 이라고 암시 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="4df26-125">기업 고객이 IT 보안 인프라 및 요구 사항에 따라 특정 요구 사항에 맞는 솔루션을 선택 하는 것이 좋습니다. 예제 Microsoft 솔루션은 서버 및 도메인 격리를 위해 IPSec 및 그룹 정책을 채택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="4df26-126">자세한 내용은를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544)하세요.</span><span class="sxs-lookup"><span data-stu-id="4df26-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="4df26-127">질문과 의견에 대해서는 secwish@microsoft.com에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4df26-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="4df26-128">또 다른 가능한 해결 방법은 백업 서비스 자체가 전송 하는 데이터를 보호 하기 위해 IPSec을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="4df26-129">이 방법을 선택 하는 경우 다음과 같은 서버에 대 한 SMB 프로토콜에 대해 IPSec 규칙을 구성 해야 하며, 여기서 풀 A와 풀 B는 두 개의 쌍으로 된 프런트 엔드 풀에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="4df26-130">풀 A의 각 프런트 엔드 서버에서 풀 B에 사용 되는 파일 저장소 까지의 SMB 서비스 (TCP/445)</span><span class="sxs-lookup"><span data-stu-id="4df26-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="4df26-131">풀 B의 각 프런트 엔드 서버에서 풀 A에 사용 되는 파일 저장소로의 SMB 서비스 (TCP/445)</span><span class="sxs-lookup"><span data-stu-id="4df26-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4df26-132">IPsec은 SSL/TLS와 같은 응용 프로그램 수준 보안을 대체 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="4df26-133">IPsec을 사용 하는 경우의 한 가지 이점은 기존 응용 프로그램에 대 한 네트워크 트래픽 보안을 변경할 필요 없이 제공할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="4df26-134">두 데이터 센터 간의 전송을 안전 하 게 보호 하려는 기업에서는 공급 업체 장비를 사용 하 여 보안 WAN 연결을 설정 하는 방법에 대 한 각 네트워킹 하드웨어 공급 업체에 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df26-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

