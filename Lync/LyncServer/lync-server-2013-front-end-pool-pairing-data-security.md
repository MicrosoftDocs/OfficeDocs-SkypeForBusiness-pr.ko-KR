---
title: 'Lync Server 2013: 프런트 엔드 풀 연결 데이터 보안'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1a408aecedc14162271d5def1adc2bcebdfd82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="c86a1-102">Lync Server 2013의 프런트 엔드 풀 연결 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="c86a1-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c86a1-103">_**마지막으로 수정한 주제:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="c86a1-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="c86a1-104">백업 서비스는 재해 복구용으로 두 개의 연결 된 프런트 엔드 풀 간에 사용자 데이터 및 회의 콘텐츠를 지속적으로 전송 하는 Lync Server 2013에 도입 되는 데이터 복제 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="c86a1-105">사용자 데이터에는 사용자 SIP Uri 및 연락처 목록 및 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="c86a1-106">회의 내용에는 Microsoft PowerPoint 2010 업로드와 회의에 사용 되는 화이트 보드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="c86a1-107">원본 풀에서 사용자 데이터 및 회의 콘텐츠는 대상 풀로 전송 되는 로컬 저장소의 압축으로 내보내지고 로컬 저장소로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="c86a1-108">백업 서비스는 두 데이터 센터 간의 통신 연결이 인터넷에서 보호 되는 회사 네트워크 내에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="c86a1-109">두 데이터 센터 간에 전송 된 데이터를 암호화 하지 않으며 HTTPS와 같은 보안 프로토콜 내에서 기본적으로 캡슐화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="c86a1-110">따라서 회사 네트워크 내에서 내부 담당자의 중간자 공격이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="c86a1-111">보안 위험 평가</span><span class="sxs-lookup"><span data-stu-id="c86a1-111">Evaluating Security Risks</span></span>

<span data-ttu-id="c86a1-112">여러 데이터 센터에서 Lync Server 2013을 배포 하 고 재해 복구 기능을 사용 하는 모든 엔터프라이즈는 교차 데이터 센터 트래픽이 해당 회사 인트라넷으로 보호 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="c86a1-113">내부 공격 보호에 대해 주의를 기울여야 하는 기업은 데이터 센터 간의 통신 연결을 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="c86a1-114">기업의 데이터 센터가 회사 인트라넷 뒤에서 보호 되는 것으로 가정 하면 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="c86a1-115">이러한 데이터 센터 간에 전송 되는 회사의 민감한 데이터에는 여러 가지 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="c86a1-116">엔터프라이즈의 IT 인프라는 이러한 교차 데이터 센터 링크가 보호 되지 않는 경우 아무리 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="c86a1-117">회사 네트워크 내에서 중간자 공격으로 인 한 공격의 위험은 인터넷에 소통량을 노출 하는 것과 비교 하 여 상대적으로 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="c86a1-118">특히, 백업 서비스 (예: SIP Uri)가 제공 하는 사용자 데이터는 일반적으로 Exchange 또는 기타 디렉터리 소프트웨어의 글로벌 주소록과 같은 다른 수단을 통해 회사 내의 모든 직원에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="c86a1-119">따라서 두 개의 연결 된 풀 간에 데이터를 복사 하는 데 백업 서비스를 사용 하는 경우 두 데이터 센터 간의 WAN 보안에 중점을 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="c86a1-120">보안 위험 경감</span><span class="sxs-lookup"><span data-stu-id="c86a1-120">Mitigating Security Risks</span></span>

<span data-ttu-id="c86a1-121">데이터 센터에 대 한 액세스를 제한 하 고 두 데이터 센터 간의 WAN 전송 보안을 유지 하는 것에 이르기까지 백업 서비스 트래픽에 대 한 보안 보호를 향상 시킬 수 있는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="c86a1-122">대부분의 경우, Lync Server 2013를 배포 하는 기업은 이미 필요한 보안 인프라를 보유 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="c86a1-123">지침을 찾는 엔터프라이즈의 경우 Microsoft는 보안 IT 인프라를 구축 하는 방법의 예로 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="c86a1-124">그러나이 솔루션이 유일한 솔루션 이라고 의미 하는 것은 아니며 Lync Server의 기본 설정 솔루션 이라고 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="c86a1-125">기업 고객은 IT 보안 인프라 및 요구 사항에 따라 특정 요구 사항에 맞는 솔루션을 선택 하는 것이 좋습니다. 예제 Microsoft 솔루션은 서버 및 도메인 격리를 위해 IPSec 및 그룹 정책을 채택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="c86a1-126">자세한 내용은을 참조 [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)하세요.</span><span class="sxs-lookup"><span data-stu-id="c86a1-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="c86a1-127">질문과 설명은 secwish@microsoft.com에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="c86a1-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="c86a1-128">또 다른 문제 해결 방법은 백업 서비스 자체에서 보내는 데이터를 보호 하기 위해 IPSec을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="c86a1-129">이 방법을 선택 하는 경우 다음 서버에 대해 SMB 프로토콜에 대 한 IPSec 규칙을 구성 해야 하며, 여기에서 풀 A 및 풀 B는 2 쌍의 프런트 엔드 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="c86a1-130">풀 A의 각 프런트 엔드 서버에서 풀 B에 사용 되는 파일 저장소 까지의 SMB 서비스 (TCP/445)</span><span class="sxs-lookup"><span data-stu-id="c86a1-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="c86a1-131">풀 B의 각 프런트 엔드 서버에서 풀 A에 사용 되는 파일 저장소로 SMB 서비스 (TCP/445).</span><span class="sxs-lookup"><span data-stu-id="c86a1-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c86a1-132">IPsec는 SSL/TLS와 같은 응용 프로그램 수준의 보안을 대체 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="c86a1-133">IPsec을 사용할 때의 이점 중 하나는 기존 응용 프로그램에 대 한 네트워크 트래픽 보안을 변경할 필요 없이 제공할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="c86a1-134">두 데이터 센터 간의 전송을 안전 하 게 보호 하려는 기업은 해당 네트워킹 하드웨어 공급 업체에 문의 하 여 공급 업체 장비를 사용 하 여 보안 WAN 연결을 설정 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c86a1-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

