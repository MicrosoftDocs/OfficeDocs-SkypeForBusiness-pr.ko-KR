---
title: 프런트 엔드와 Edge 연결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: '각 프런트 엔드 풀에는 연결 된 하나의에 지 서버 또는에 지 풀만 있을 수 있습니다. 사이트에 대 한 외부 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자에 대 한 지원을 제공할 수 있습니다. 또한 특정 공용 IM (인스턴트 메시징) 연결 공급자 (예: Windows Live)에 대 한 지원을 포함 하 고 익명 사용자에 대 한 지원을 포함할 수 있는 페더레이션 사용자에 대 한 지원을 사용 하도록 설정할 수 있습니다.'
ms.openlocfilehash: cc804ed9a21b81ce0315664bcb1b3530e8087584
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217759"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="cf5f8-105">프런트 엔드와 Edge 연결</span><span class="sxs-lookup"><span data-stu-id="cf5f8-105">Associate Front End With Edge</span></span>

<span data-ttu-id="cf5f8-106">각 프런트 엔드 풀에는 연결 된 하나의에 지 서버 또는에 지 풀만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5f8-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="cf5f8-107">사이트에 대 한 외부 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자에 대 한 지원을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5f8-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="cf5f8-108">또한 특정 공용 IM (인스턴트 메시징) 연결 공급자 (예: Windows Live)에 대 한 지원을 포함 하 고 익명 사용자에 대 한 지원을 포함할 수 있는 페더레이션 사용자에 대 한 지원을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5f8-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="cf5f8-109">사이트의 모든 풀 및 여러 중앙 사이트의 풀은 사용량이에 지 서버의 용량을 초과 하지 않는 경우 동일한에 지 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5f8-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="cf5f8-110">확장을 비롯한 모니터링에 대한 자세한 내용은 계획 설명서의 [외부 사용자 액세스 계획](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf5f8-110">For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation.</span></span> <span data-ttu-id="cf5f8-111">외부 사용자 액세스를 지원하도록 토폴로지를 설계하는 방법에 대한 자세한 내용은 배포 설명서의 [에지 토폴로지 정의](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf5f8-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


