---
title: Director 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 기존 감독에 대 한 설정을 편집 하려면 다음 섹션이 표시 됩니다.
ms.openlocfilehash: 5b58f74d7d343f2a4b57074dbc041938247ddc1f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702383"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="39b15-103">Director 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="39b15-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="39b15-104">기존 감독에 대 한 설정을 편집 하려면 다음 섹션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="39b15-105">일반 설정</span><span class="sxs-lookup"><span data-stu-id="39b15-105">General settings</span></span>
    
- <span data-ttu-id="39b15-106">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="39b15-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="39b15-107">일반 설정</span><span class="sxs-lookup"><span data-stu-id="39b15-107">General settings</span></span>

<span data-ttu-id="39b15-108">디렉터 풀의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="39b15-109">값을 변경하려면 서버의 FQDN을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="39b15-110">새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="39b15-111">**연결**에서는 다음을 편집하거나 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="39b15-112">사용할 디렉터 풀에 대 한 파일 공유입니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-112">File share for the Director pool to use.</span></span> <span data-ttu-id="39b15-113">이미 토폴로지 작성기에 정의 된 기존 파일 공유를 선택 하거나 **새로** 만들기를 클릭 하 여 새 파일 공유 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="39b15-114">SQL Server 저장소 모니터링.</span><span class="sxs-lookup"><span data-stu-id="39b15-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="39b15-115">새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="39b15-116">새 파일 공유를 만든 경우 지정 하는 서버에서 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="39b15-117">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="39b15-117">Web services</span></span>

<span data-ttu-id="39b15-118">디렉터 풀의 웹 서비스에 대 한 추가 설정을 편집 하거나 지정 하려면 내부 웹 서비스 및 외부 웹 서비스에서 설정을 수정 하거나 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="39b15-119">**내부 웹 서비스** 의 경우 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="39b15-120">프런트 엔드 풀 또는 프런트 엔드 서버를 두 개 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="39b15-121">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 **pool01.contoso.com**로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 **pool01.contoso.com** 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="39b15-122">디렉터를 배포 하는 경우 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프론트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 모든 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="39b15-123">내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="39b15-124">FQDN 다시 정의를 선택하면 풀의 내부 웹 서비스 ID에 대해 다른 FQDN을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="39b15-125">기본적으로이 설정은 디렉터 풀에 대해 정의 된 현재 풀 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="39b15-126">배포에 필요한 HTTP 및 HTTPS에 대 한 수신 대기 및 게시 된 포트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="39b15-127">HTTP 및 HTTPS의 포트 443에 대 한 기본 80 설정은 가장 일반적인 설정이 며, 조직 및 인프라 디자인 내에 특정 요구 사항이 없다면 일반적으로 변경 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="39b15-128">**외부 웹 서비스**의 경우 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="39b15-129">외부 웹 서비스의 FQDN을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="39b15-130">여기에 지정되는 FQDN은 일반적으로 외부 연결 요구 사항(예: 역방향 프록시)에 따라 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="39b15-131">배포에 필요한 HTTP 및 HTTPS에 대 한 수신 대기 및 게시 된 포트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="39b15-132">처음에는 HTTP의 경우 포트 8080, HTTPS의 경우 포트 4443이 기본 설정으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="39b15-133">수신 대기 포트의 이러한 설정은 역방향 프록시 및 외부 네트워크 요구 사항에 따라 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="39b15-134">게시된 포트는 기본적으로 HTTP의 경우 포트 80, HTTPS의 경우 포트 443으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="39b15-135">이러한 값은 디렉터 풀 또는 디렉터 서버가 들어오는 요청을 수신 대기 하는 포트를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="39b15-136">일반적으로 풀의 포트 요구 사항 충돌이 없는 경우에는 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="39b15-137">동일한 포트 값을 사용 하는 내부 및 외부 게시 포트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="39b15-138">즉, 포트가 충돌하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="39b15-138">This is not a conflict.</span></span>
  

