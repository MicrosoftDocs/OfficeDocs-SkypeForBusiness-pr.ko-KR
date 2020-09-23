---
title: 단순 URL 추가
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
- ms.lync.tb.AddSimpleUrlPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 202b9fa2-41ab-4c86-a283-ebc8dece7ddf
description: 배포 정의에 다른 단순 Url을 추가 하려면 새 단순 URL의 URL을 지정 합니다.
ms.openlocfilehash: 243dae47571286e60deb4ecdfc61beb7f175eb95
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216389"
---
# <a name="add-simple-url"></a><span data-ttu-id="4281b-103">단순 URL 추가</span><span class="sxs-lookup"><span data-stu-id="4281b-103">Add Simple URL</span></span>
 
<span data-ttu-id="4281b-104">배포 정의에 다른 단순 Url을 추가 하려면 새 단순 URL의 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4281b-104">To add additional simple URLs to the definition of the deployment, specify the URL of the new simple URL.</span></span> <span data-ttu-id="4281b-105">URL의 형식은 _http://입니다 \<simple URL type\> . \<domain name\> _</span><span class="sxs-lookup"><span data-stu-id="4281b-105">The format of the URL is  _http://\<simple URL type\>.\<domain name\>_</span></span> <span data-ttu-id="4281b-106">다음은 단순 URL 유형이 다음 중 하나에 해당 하는 _http:// \<domain name\> / \<simple URL type\> _입니다.</span><span class="sxs-lookup"><span data-stu-id="4281b-106">or _http://\<domain name\>/\<simple URL type\>_, where the simple URL type is one of the following:</span></span>
  
- <span data-ttu-id="4281b-107">조건</span><span class="sxs-lookup"><span data-stu-id="4281b-107">Meet</span></span>
    
- <span data-ttu-id="4281b-108">전화 접속</span><span class="sxs-lookup"><span data-stu-id="4281b-108">Dial in</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="4281b-109">한 번에 하나의 전화 걸기가 단순 URL에 연결 되 고 한 회의에 대 한 단순 URL 하나가 활성화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4281b-109">You can have one Dial in simple URL and one Meet simple URL active at any time.</span></span> <span data-ttu-id="4281b-110">새 단순 URL을 추가하고 해당 URL을 활성 URL로 설정하면 이후의 모든 요청이 새 단순 URL을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4281b-110">Adding a new simple URL and making it the active URL will set all future requests to use the new simple URL.</span></span> <span data-ttu-id="4281b-111">이전 단순 URL이 활성 상태일 때 작성 된 회의 및 기타 요청을 처리 하기 위해 nonactive 단순 URL을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4281b-111">You leave the nonactive simple URL to handle conferences and other requests that were made when the older simple URL was active.</span></span> 
  
<span data-ttu-id="4281b-112">단순 URL을 추가 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015의 단순 url에 대 한 DNS 요구 사항을](../../plan-your-deployment/network-requirements/simple-urls.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4281b-112">For more details about adding a simple URL, see [DNS requirements for simple URLs in Skype for Business Server 2015](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>
  

