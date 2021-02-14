---
title: 프런트 엔드와 에지 연결
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: '각 프런트 엔드 풀에는 연결된 에지 서버 또는 에지 풀이 하나만 있습니다. 사이트에 대해 외부 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자에 대한 지원을 제공할 수 있습니다. 특정 공용 IM(인스턴트 메시징) 연결 공급자(예: Windows Live)의 사용자에 대한 지원과 익명 사용자에 대한 지원을 포함할 수 있는 페더된 사용자에 대한 지원을 사용하도록 설정할 수도 있습니다.'
ms.openlocfilehash: 57f8a7d2a62f1246ac74931491b9244f3aca0a0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811338"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="32851-105">프런트 엔드와 에지 연결</span><span class="sxs-lookup"><span data-stu-id="32851-105">Associate Front End With Edge</span></span>

<span data-ttu-id="32851-106">각 프런트 엔드 풀에는 연결된 에지 서버 또는 에지 풀이 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="32851-107">사이트에 대해 외부 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자에 대한 지원을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="32851-108">특정 공용 IM(인스턴트 메시징) 연결 공급자(예: Windows Live)의 사용자에 대한 지원과 익명 사용자에 대한 지원을 포함할 수 있는 페더된 사용자에 대한 지원을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="32851-109">사이트의 모든 풀과 여러 중앙 사이트의 풀은 사용량이 에지 서버의 용량을 초과하지 않는 경우 동일한 에지 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="32851-110">확장을 비롯한 모니터링에 대한 자세한 내용은 계획 설명서의 [외부 사용자 액세스 계획](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="32851-110">For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation.</span></span> <span data-ttu-id="32851-111">외부 사용자 액세스를 지원하도록 토폴로지를 설계하는 방법에 대한 자세한 내용은 배포 설명서의 [에지 토폴로지 정의](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="32851-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


