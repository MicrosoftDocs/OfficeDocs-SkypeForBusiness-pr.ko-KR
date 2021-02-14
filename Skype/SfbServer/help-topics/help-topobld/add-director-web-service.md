---
title: 디렉터 웹 서비스 추가
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이면 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
ms.openlocfilehash: aa3c96a6a47a35ae8c65b0a7a6bcb5df696bada4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828898"
---
# <a name="add-director-web-service"></a><span data-ttu-id="377de-104">디렉터 웹 서비스 추가</span><span class="sxs-lookup"><span data-stu-id="377de-104">Add Director Web Service</span></span>
 
<span data-ttu-id="377de-105">기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="377de-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="377de-106">예를 들어 풀의 웹 서비스에 대한 전체 URL이면 기본 https://pool01.contoso.net URL은 pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="377de-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="377de-107">디렉터를 하나만 배포하는 경우 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="377de-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="377de-108">Director 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 풀 FQDN과 달라야 하며 내부와 같은 다른 내부 기본 URL을 지정할 수 있습니다. \<your base URL\></span><span class="sxs-lookup"><span data-stu-id="377de-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="377de-p104">도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 예를 들어 내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우 contoso.com 도메인 이름을 사용하여 외부 기본 URL을 정의합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="377de-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

