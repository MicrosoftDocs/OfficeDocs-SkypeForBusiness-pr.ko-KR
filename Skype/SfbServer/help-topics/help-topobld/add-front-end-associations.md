---
title: 프런트 엔드 연결 추가
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
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 지금 서버 역할과 프런트 엔드 풀을 연결하여 다른 서버 배포가 필요한 특정 기능에 대한 지원을 사용하도록 설정할 수 있습니다. 또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다. 프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.
ms.openlocfilehash: 13d796bd5c33b0f56ebc43ba11f82a188cce0c76
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218389"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="91c83-105">프런트 엔드 연결 추가</span><span class="sxs-lookup"><span data-stu-id="91c83-105">Add Front End Associations</span></span>

<span data-ttu-id="91c83-p102">지금 서버 역할과 프런트 엔드 풀을 연결하여 다른 서버 배포가 필요한 특정 기능에 대한 지원을 사용하도록 설정할 수 있습니다. 또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다. 프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91c83-p102">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now. You can also associate server roles with the Front End pool at a later time. The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="91c83-109">A/V 에지 서버.</span><span class="sxs-lookup"><span data-stu-id="91c83-109">A/V Edge Server.</span></span> <span data-ttu-id="91c83-110">A/V 에지 서버 구현에 대한 자세한 내용은 계획 설명서에서 [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="91c83-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91c83-111">지금 이러한 기능 중 원하는 기능에 대한 지원을 사용하도록 설정하는 경우 게시하는 토폴로지 디자인에 선택한 각 기능의 구현에 필요한 서버 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91c83-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="91c83-112">토폴로지를 오류 없이 성공적으로 게시하려면 물리적 컴퓨터를 도메인에 가입시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c83-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="91c83-113">예를 들어 지금 보관을 지원 하도록 설정 하는 경우 조직에 대 한 보관 통신을 시작 하기 전에 보관 서버를 배포 하 고 적절 한 보관 옵션을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c83-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>


