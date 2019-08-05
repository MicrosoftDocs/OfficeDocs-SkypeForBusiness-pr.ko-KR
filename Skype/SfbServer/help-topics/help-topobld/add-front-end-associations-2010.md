---
title: 프런트 엔드 연결 2010 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndAssociationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a01dff6c-50cc-463d-ac08-9f22e044bdc8
description: 이 시점에 서버 역할을 프런트 엔드 풀에 연결 하 여 다른 서버의 배포를 필요로 하는 특정 기능에 대 한 지원을 설정할 수 있습니다. 또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다. 프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.
ms.openlocfilehash: e2cc5e724ceae7a00f790c9ebf7d6a38b99dddb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196981"
---
# <a name="add-front-end-associations-2010"></a><span data-ttu-id="814ac-105">프런트 엔드 연결 2010 추가</span><span class="sxs-lookup"><span data-stu-id="814ac-105">Add Front End Associations 2010</span></span>

<span data-ttu-id="814ac-106">이 시점에 서버 역할을 프런트 엔드 풀에 연결 하 여 다른 서버의 배포를 필요로 하는 특정 기능에 대 한 지원을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814ac-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool at this time.</span></span> <span data-ttu-id="814ac-107">또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814ac-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="814ac-108">프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="814ac-108">The server roles that can be associated with a Front End pool include the following:</span></span>

1. <span data-ttu-id="814ac-109">보관 서버.</span><span class="sxs-lookup"><span data-stu-id="814ac-109">Archiving Server.</span></span> <span data-ttu-id="814ac-110">보관 지원을 계획 하 고 구현 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [보관을 위한 조직의 요구 사항 정의](https://technet.microsoft.com/library/ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a.aspx) 및 [프런트 엔드 풀 또는 Standard Edition 서버를 정의 및 구성](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 하 고 배포 하는 방법에 대해 알아보세요. [ ](https://technet.microsoft.com/library/a89edd16-12d5-4602-ad2f-194b47d1188e.aspx)배포 설명서에서 보관</span><span class="sxs-lookup"><span data-stu-id="814ac-110">For details about planning and implementing archiving support, see [Defining Your Organization's Requirements for Archiving](https://technet.microsoft.com/library/ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a.aspx) in the Planning documentation and [Define and Configure a Front End Pool or Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) and [Deploying Archiving](https://technet.microsoft.com/library/a89edd16-12d5-4602-ad2f-194b47d1188e.aspx) in the Deployment documentation.</span></span>

2. <span data-ttu-id="814ac-111">모니터링 서버.</span><span class="sxs-lookup"><span data-stu-id="814ac-111">Monitoring Server.</span></span> <span data-ttu-id="814ac-112">모니터링 지원을 구현 하는 방법에 대 한 자세한 내용은 계획 설명서의 [모니터링 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 및 [프런트 엔드 풀 또는 스탠더드 버전 서버 정의 및 구성](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 및 배포에서 [모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx) 를 참조 하세요. 참조.</span><span class="sxs-lookup"><span data-stu-id="814ac-112">For details about implementing monitoring support, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [Define and Configure a Front End Pool or Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx) in the Deployment documentation.</span></span>

3. <span data-ttu-id="814ac-113">A/V에 지 서비스.</span><span class="sxs-lookup"><span data-stu-id="814ac-113">A/V Edge service.</span></span> <span data-ttu-id="814ac-114">A/V Edge 서비스 구현에 대 한 자세한 내용은 [외부 사용자 액세스 개요](https://technet.microsoft.com/library/97aded6c-5fa3-4225-95a6-9ad094d61654.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="814ac-114">For details about implementing an A/V Edge service, see [Overview of External User Access](https://technet.microsoft.com/library/97aded6c-5fa3-4225-95a6-9ad094d61654.aspx).</span></span>


