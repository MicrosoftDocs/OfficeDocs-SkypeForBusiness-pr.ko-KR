---
title: DNS SRV 레코드 업데이트
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 서버나 도메인에 로그온 해야 합니다.
ms.openlocfilehash: 5d506c3b2ff70ae776396e8d3a51e71360cdcc83
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241747"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="2db3d-103">DNS SRV 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="2db3d-103">Update DNS SRV records</span></span>

<span data-ttu-id="2db3d-104">이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 서버나 도메인에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="2db3d-105">이 항목에서는 비즈니스용 Skype 서버 2019으로 마이그레이션한 후 DNS (Domain Name System) 레코드를 업데이트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="2db3d-106">모든 사용자가 비즈니스용 Skype 서버 2019로 이동 했지만 레거시 풀 또는 디렉터를 해제 하기 전에 모든 SIP 도메인에 대 한 내부 DNS의 DNS SRV 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="2db3d-107">이 절차에서는 내부 DNS에 SIP 사용자 도메인에 대 한 영역이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="2db3d-108">DNS SRV 레코드를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="2db3d-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="2db3d-109">DNS 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **dns**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="2db3d-110">SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 하 고 비즈니스용 Skype 서버 2019이 설치 되어 있는 SIP 도메인을 확장 하 고 **_tcp** 설정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="2db3d-111">오른쪽 창에서 **_sipinternaltls** 를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="2db3d-112">**이 서비스를 제공**하는 호스트에서 비즈니스용 Skype 서버 2019 풀을 가리키도록 호스트 FQDN을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="2db3d-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="2db3d-114">프런트 엔드 풀 또는 Standard Edition 서버의 FQDN을 확인할 수 있는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="2db3d-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="2db3d-115">도메인의 클라이언트 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="2db3d-116">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="2db3d-117">**열기** 상자에 cmd를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="2db3d-118">명령 프롬프트에서 _ \<프런트 엔드 풀\> 의 nslookup fqdn_ 또는 _ \<Standard Edition server\>의 fqdn_을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="2db3d-119">FQDN에 대 한 적절 한 IP 주소로 확인 되는 회신을 수신 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db3d-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

