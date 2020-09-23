---
title: Lync Server 2010에 대한 에지 설정 편집 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 다음 속성을 구성 하 여에 지 서버 또는에 지 풀에 대 한 설정을 편집할 수 있습니다.
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216119"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="850a4-103">Lync Server 2010에 대한 에지 설정 편집 확장기</span><span class="sxs-lookup"><span data-stu-id="850a4-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="850a4-104">다음 속성을 구성 하 여에 지 서버 또는에 지 풀에 대 한 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="850a4-105">**일반**</span><span class="sxs-lookup"><span data-stu-id="850a4-105">**General**</span></span>
  
- <span data-ttu-id="850a4-106">**내부 풀 FQDN**: 내부 풀 정규화 된 도메인 이름은 DNS (domain name system) 호스트 (A 또는 i p v 6 용 AAAA) 레코드에서 정의 된에 지 서버 또는에 지 풀의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="850a4-107">다른 세션 시작 프로토콜 파트너와의 페더레이션을 위해에 지 서버 또는에 지 풀을 사용 하도록 설정 하려면 **이에 지 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="850a4-108">페더레이션에 대 한 단일에 지 서버 또는에 지 풀을 적극적으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="850a4-109">연결 된 스크린샷에 표시 된 구성은 다른에 지 서버 또는에 지 풀이 페더레이션에 대해 이미 구성 되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="850a4-110">페더레이션에 대 한 외부 DNS SRV 레코드 (_sipfederationtls _tcp \<external domain name\> )는 페더레이션에 대 한에 지 서버 또는에 지 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="850a4-111">TCP 포트 4443에서 기본적으로 **내부 구성 복제 포트 (HTTPS)** 는 중앙 관리 저장소의 로컬 (즉,에 지 서버에서 로컬) 복사본을 복제 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="850a4-112">중앙 관리 저장소의 로컬 복사본은 각 컴퓨터의 SQL Server에 있는 **RTCLOCAL** 데이터베이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="850a4-113">이 복제는 중앙 관리 서버 (또는 중앙 관리 서버 역할을 보유 하는 프런트 엔드 서버 또는 프런트 엔드 풀)에서에 지 서버에 대 한 단방향으로 시작 되며 내부 인터페이스 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="850a4-114">**다음 홉 선택**</span><span class="sxs-lookup"><span data-stu-id="850a4-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="850a4-115">목록에서 **다음 홉 풀**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="850a4-116">디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀을 정의 하 여이 역할을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="850a4-117">다음 홉 풀은에 지 서버 또는에 지 풀 내부 인터페이스에서 인바운드 SIP 메시지를 수락 하 고 아웃 바운드 SIP를에 지 내부 인터페이스로 보내는 서버 또는 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="850a4-118">디렉터는 선택적 역할 이며 디렉터를 배포 하지 않기로 결정 한 경우 프런트 엔드 서버 (단일 컴퓨터 또는 풀)가 디렉터 역할을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="850a4-119">**외부 설정**</span><span class="sxs-lookup"><span data-stu-id="850a4-119">**External settings**</span></span>
  
<span data-ttu-id="850a4-120">속성의이 섹션을 사용 하 여에 지 서버 또는에 지 풀의 외부 설정에 대 한 속성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="850a4-121">편집 가능한 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="850a4-122">각에 지 서버 서비스에 고유한 IP 주소 및 정규화 된 도메인 이름을 할당 하려면 **웹 회의 및 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="850a4-123">확인란을 선택하지 않는 경우 각 에지 서비스에 대해 별도의 포트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="850a4-124">각에 지 서비스는 액세스에 지 서비스에 대해 정의 된 FQDN을 공유 하므로 같은 IP 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="850a4-125">각 에지 서비스는 고유한 IP 주소 및 같은 포트나 같은 IP 주소 및 고유한 포트 값에 의해 고유하게 식별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="850a4-126">A/v에 지 서비스는 nat (network address translation) 장치 뒤에 숨겨지는 개인 주소 또는 기타 주소를 사용 하도록 구성 하려는 경우 **nat-t 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="850a4-127">**액세스에 지 서비스**를 편집 하려면 호스트에 의해 DNS에 정의 된 액세스에 지 서비스에 대 한 **풀 FQDN** (A, IPv6이 사용 되는 경우 AAAA) 레코드 및 포트 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="850a4-128">**웹 회의에 지 서비스**를 편집 하려면 호스트에서 DNS에 정의한 웹 회의에 지 서비스에 대 한 **풀 FQDN** 을 정의 하 고 (i p v 6을 사용 하는 경우 AAAA) 레코드와 포트 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="850a4-129">**A/v에 지 서비스**를 편집 하려면 호스트에 의해 DNS에 정의 된 a/v에 지 서비스에 대 한 **풀 FQDN** 을 정의 하 고 (i p v 6을 사용 하는 경우 AAAA) 레코드와 포트 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="850a4-130">**웹 회의 및 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택한 경우에는 액세스에 지 서비스 풀 FQDN만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="850a4-131">세 개의 각 에지 서비스에 대해 고유한 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="850a4-132">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="850a4-133">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="850a4-134">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="850a4-134">**Help** Displays this help screen.</span></span>
  

