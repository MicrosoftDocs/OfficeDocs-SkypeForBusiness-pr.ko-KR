---
title: 프런트 엔드 웹 서비스 2010 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이면 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824028"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="7f883-104">프런트 엔드 웹 서비스 2010 추가</span><span class="sxs-lookup"><span data-stu-id="7f883-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="7f883-105">기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="7f883-106">예를 들어 풀의 웹 서비스에 대한 전체 URL이면 기본 https://pool01.contoso.net URL은 pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="7f883-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="7f883-107">Standard Edition Server에 대한 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 다시 구성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="7f883-108">Enterprise Edition 프런트 엔드 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 풀 FQDN과 달라야 하며 내부와 같은 다른 내부 기본 URL을 지정할 수 있습니다. \<your base URL\></span><span class="sxs-lookup"><span data-stu-id="7f883-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="7f883-109">도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="7f883-110">내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="7f883-111">이 경우 contoso.com 도메인 이름을 사용하여 외부 기본 URL을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="7f883-112">이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="7f883-113">외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="7f883-114">인스턴트 메시징 및 현재 상태는 프런트 엔드 풀에 대한 HTTP 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7f883-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

