---
title: 웹 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: 토폴로지 작성기 내에서 내부 및 외부 웹 서비스에 사용되는 포트 설정을 수정할 수 있습니다. 또한 DNS(Domain Name System) 부하 분산을 배포하는 경우 토폴로지 작성기에서 해당 풀에 있는 모든 서버의 실제 IP 주소로 확인되는 풀의 FQDN(FQDN)을 구성할 수 있습니다.
ms.openlocfilehash: 00fbf89b6e8121b5e2cd8d1b8d544531cc411e3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817818"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="17342-104">웹 서비스 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="17342-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="17342-105">토폴로지 작성기 내에서 내부 및 외부 웹 서비스에 사용되는 포트 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17342-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="17342-106">또한 DNS(Domain Name System) 부하 분산을 배포하는 경우 토폴로지 작성기에서 해당 풀에 있는 모든 서버의 실제 IP 주소로 확인되는 풀의 FQDN(FQDN)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17342-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="17342-107">웹 서비스 설정 편집</span><span class="sxs-lookup"><span data-stu-id="17342-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="17342-108">적절한 Standard Edition 프런트 엔드 서버 또는 적절한 Enterprise Edition 프런트 엔드 풀을 선택하고 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="17342-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="17342-109">**속성 편집** 대화 상자에서 **웹 서비스** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="17342-110">프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우 외부 웹 서비스 FQDN은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="17342-111">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 pool01.contoso.com 다른 프런트  엔드 풀 또는 프런트 엔드 pool01.contoso.com 사용할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="17342-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="17342-112">또한 Director를 배포하는 경우 모든 Director 또는 Director 풀에 대해 정의된 외부 웹 서비스 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버뿐만 아니라 다른 모든 Director 또는 Director 풀에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="17342-113">내부 웹 서비스를 자체 정의 FQDN으로 다시 정의하려면 각 FQDN이 다른 프런트 엔드 풀, Director 또는 Director 풀과 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="17342-114">Enterprise Edition 풀의 속성을 편집하는 경우 **FQDN** 다시 지정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17342-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="17342-115">이 옵션은 DNS(Domain Name System) 부하 분산을 사용하는 경우만 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="17342-116">DNS 부하 분산을 사용하는 경우 **FQDN 다시 정의** 를 선택한 다음 텍스트 상자에 풀에 있는 모든 서버의 물리적 IP 주소로 확인되는 해당 풀의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="17342-117">DNS 부하 분산을 사용하지 않는 경우 및 **FQDN 다시 정의** 를 선택하지 않는 경우 내부 웹 서비스 FQDN을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17342-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="17342-118">내부 웹 서비스 FQDN은 내부 사용자가 비즈니스용 Skype 서버에 연결하는 데 사용하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="17342-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="17342-p105">선택적으로 **수신 대기 포트** 및 **게시된 포트** 에 대한 새 HTTP, HTTPS 또는 HTTP 및 HTTPS 값을 입력합니다. 수신 대기 포트는 IIS(인터넷 정보 서비스)에서 들어오는 SIP(Session Initiation Protocol) 트래픽을 수신 대기하는 데 사용하는 포트이고, 게시된 포트는 부하 분산 장치 또는 역방향 프록시 서버에 구성된 포트로서 들어오는 SIP 트래픽을 수신 대기하는 데에도 사용됩니다. 기본적으로 HTTP 수신 대기 포트 및 HTTP 게시된 포트는 둘 다 포트 80으로 설정되고 해당 HTTPS 포트는 둘 다 443으로 설정됩니다. 두 HTTP 게시된 포트의 기본값은 8080이고 해당 HTTPS 포트는 4443으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="17342-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="17342-123">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-123">Click **OK**.</span></span>
    
<span data-ttu-id="17342-124">내부 FQDN 또는 수신 포트 할당을 수정하는 경우 변경 내용을 적용하려면 풀의 모든 서버에서 로컬 설정을 다시 로컬로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17342-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

