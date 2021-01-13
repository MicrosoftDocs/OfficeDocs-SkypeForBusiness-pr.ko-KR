---
title: 디렉터 일반 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 다음 섹션에서 기존 디렉터의 설정을 편집할 수 있습니다.
ms.openlocfilehash: 62dc9b855937d360a975e5e4035d662da276ce02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822628"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="7041d-103">디렉터 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="7041d-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="7041d-104">다음 섹션에서 기존 디렉터의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="7041d-105">일반 설정</span><span class="sxs-lookup"><span data-stu-id="7041d-105">General settings</span></span>
    
- <span data-ttu-id="7041d-106">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="7041d-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="7041d-107">일반 설정</span><span class="sxs-lookup"><span data-stu-id="7041d-107">General settings</span></span>

<span data-ttu-id="7041d-p101">디렉터 풀의 FQDN(정규화된 도메인 이름). 값을 변경하려면 서버의 FQDN을 편집합니다. 새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="7041d-111">**연결** 에서는 다음을 편집하거나 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="7041d-112">디렉터 풀에서 사용할 파일 공유.</span><span class="sxs-lookup"><span data-stu-id="7041d-112">File share for the Director pool to use.</span></span> <span data-ttu-id="7041d-113">토폴로지 작성기에서 이미 정의된 기존 파일 공유를 선택하거나 새로 만들기를 클릭하여 새 파일 공유 정의를 만들 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="7041d-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="7041d-114">모니터링 SQL Server 저장소</span><span class="sxs-lookup"><span data-stu-id="7041d-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7041d-p103">새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다. 새 파일 공유를 만드는 경우 지정한 서버에서 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="7041d-117">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="7041d-117">Web services</span></span>

<span data-ttu-id="7041d-118">디렉터 풀의 웹 서비스에 대한 추가 설정을 편집하거나 지정하려면 내부 웹 서비스 및 외부 웹 서비스의 설정을 수정하거나 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="7041d-119">**내부 웹 서비스** 에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7041d-120">프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우 외부 웹 서비스 FQDN은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="7041d-121">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 pool01.contoso.com 다른 프런트  엔드 풀 또는 프런트 엔드 pool01.contoso.com 사용할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="7041d-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="7041d-122">또한 Director를 배포하는 경우 모든 Director 또는 Director 풀에 대해 정의된 외부 웹 서비스 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버뿐만 아니라 다른 모든 Director 또는 Director 풀에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="7041d-123">내부 웹 서비스를 자체 정의 FQDN으로 다시 정의하려면 각 FQDN이 다른 프런트 엔드 풀, Director 또는 Director 풀과 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="7041d-p105">FQDN 다시 정의를 선택하면 풀의 내부 웹 서비스 ID에 대해 다른 FQDN을 지정할 수 있습니다. 기본적으로 디렉터 풀에 정의된 현재 풀 이름이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="7041d-p106">배포에 필요한 HTTP 및 HTTPS용 수신 대기 포트 및 게시된 포트를 지정할 수 있습니다. 기본 설정(HTTP의 경우 포트 80, HTTPS의 경우 포트 443)은 가장 일반적인 설정이므로 조직 내에 특정 요구 사항이 있거나 인프라 디자인에 필요한 경우가 아니면 기본 설정을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="7041d-128">**외부 웹 서비스** 에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="7041d-p107">외부 웹 서비스의 FQDN을 정의할 수 있습니다. 여기에 지정되는 FQDN은 일반적으로 외부 연결 요구 사항(예: 역방향 프록시)에 따라 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="7041d-p108">배포에 필요한 HTTP 및 HTTPS용 수신 대기 포트 및 게시된 포트를 지정할 수 있습니다. 처음에는 HTTP의 경우 포트 8080, HTTPS의 경우 포트 4443이 기본 설정으로 정의됩니다. 수신 대기 포트의 이러한 설정은 역방향 프록시 및 외부 네트워크 요구 사항에 따라 변경할 수 있습니다. 게시된 포트는 기본적으로 HTTP의 경우 포트 80, HTTPS의 경우 포트 443으로 설정됩니다. 이러한 값에 따라 디렉터 풀 또는 디렉터 서버에서 들어오는 요청을 수신 대기할 포트가 결정됩니다. 일반적으로 풀에서 포트 요구 사항이 충돌하지 않는 한, 이러한 설정을 변경할 필요는 없습니다. 게시된 내부 및 외부 포트에서 동일한 포트 값을 사용하는 것은 이미 예상되는 상황입니다. 즉, 포트가 충돌하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7041d-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

