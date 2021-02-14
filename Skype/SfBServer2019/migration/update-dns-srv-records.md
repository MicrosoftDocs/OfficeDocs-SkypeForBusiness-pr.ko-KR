---
title: DNS SRV 레코드 업데이트
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753270"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="5d255-103">DNS SRV 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="5d255-103">Update DNS SRV records</span></span>

<span data-ttu-id="5d255-104">이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="5d255-105">이 항목에서는 비즈니스용 Skype 서버 2019로 마이그레이션한 후 DNS(Domain Name System) 레코드를 업데이트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="5d255-106">모든 사용자를 비즈니스용 Skype 서버 2019로 이동한 후 레거시 풀 또는 디렉터가 해제되기 전에 모든 SIP 도메인에 대해 내부 DNS의 DNS SRV 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="5d255-107">이 절차에서는 내부 DNS에 SIP 사용자 도메인의 영역이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="5d255-108">DNS SRV 레코드를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="5d255-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="5d255-109">DNS 서버에서 **시작**, **관리 도구** 를 차례로 클릭한 다음 **DNS** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="5d255-110">SIP 도메인의 콘솔 **트리에서** 정방 검색 영역, 비즈니스용 Skype 서버 2019가 설치된 SIP 도메인을 확장하고, _tcp 설정으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="5d255-111">오른쪽 창에서 마우스 오른쪽 단추로 _sipinternaltls **속성을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d255-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="5d255-112">이 **서비스를 제공하는 호스트에서** 호스트 FQDN이 비즈니스용 Skype 서버 2019 풀을 지점으로 하여 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="5d255-113">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="5d255-114">프런트 엔드 풀 또는 Standard Edition Server의 FQDN을 확인할 수 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="5d255-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="5d255-115">도메인의 클라이언트 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="5d255-116">**시작** 을 클릭한 다음 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="5d255-117">열기 **상자에** cmd를 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d255-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5d255-118">명령 프롬프트에 nslookup 또는 nslookup을 입력한 다음 _\<FQDN of the Front End pool\>_  _\<FQDN of the Standard Edition server\>_ Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="5d255-119">FQDN에 대해 적절한 IP 주소로 확인되는 응답이 수신되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5d255-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

