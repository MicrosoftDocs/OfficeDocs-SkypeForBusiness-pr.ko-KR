---
title: 프런트 엔드 웹 서비스 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.
ms.openlocfilehash: 3317df51fcacd17de8c1ce3f40163f2ce63dc13f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187164"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="cb5a5-104">프런트 엔드 웹 서비스 추가</span><span class="sxs-lookup"><span data-stu-id="cb5a5-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="cb5a5-105">기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="cb5a5-106">예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="cb5a5-107">스탠더드 버전 서버에 대 한 내부 웹 서비스 풀의 FQDN (정규화 된 도메인 이름)을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="cb5a5-108">Enterprise Edition 프런트 엔드 풀에 대 한 DNS (Domain Name System) 부하 분산을 구성 하는 경우에는 풀 FQDN과는 다른 내부 기본 URL (예:\<기본 url\>)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="cb5a5-109">내부 기본 URL에서 다른 외부 기본 URL을 지정 하 여 도메인 명명을 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="cb5a5-110">예를 들어 내부 도메인은 contoso.net 외부 도메인 이름은 contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="cb5a5-111">Contoso.com 도메인 이름을 사용 하 여 외부 기본 URL을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="cb5a5-112">이는 edge 배포에 대 한 역방향 프록시 서버에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="cb5a5-113">외부 기본 URL 도메인 이름은 역방향 프록시의 FQDN에 대 한 도메인 이름과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="cb5a5-114">인스턴트 메시지 및 현재 상태에는 프런트 엔드 풀에 대 한 HTTP 액세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5a5-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

