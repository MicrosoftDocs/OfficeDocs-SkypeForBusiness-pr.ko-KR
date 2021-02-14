---
title: 프런트 엔드 연결 2010 추가
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
- ms.lync.tb.AddFrontEndAssociationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a01dff6c-50cc-463d-ac08-9f22e044bdc8
description: 현재 서버 역할을 프런트 엔드 풀과 연결하여 다른 서버를 배포해야 하는 특정 기능에 대한 지원을 사용하도록 설정할 수 있습니다. 또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다. 프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.
ms.openlocfilehash: 237c6df4455032789d0416ffd6f3b1ad4af848b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824198"
---
# <a name="add-front-end-associations-2010"></a><span data-ttu-id="1855f-105">프런트 엔드 연결 2010 추가</span><span class="sxs-lookup"><span data-stu-id="1855f-105">Add Front End Associations 2010</span></span>

<span data-ttu-id="1855f-106">현재 서버 역할을 프런트 엔드 풀과 연결하여 다른 서버를 배포해야 하는 특정 기능에 대한 지원을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1855f-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool at this time.</span></span> <span data-ttu-id="1855f-107">또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1855f-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="1855f-108">프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1855f-108">The server roles that can be associated with a Front End pool include the following:</span></span>

1. <span data-ttu-id="1855f-109">보관 서버.</span><span class="sxs-lookup"><span data-stu-id="1855f-109">Archiving Server.</span></span> <span data-ttu-id="1855f-110">보관 지원을 계획 및 구현하는 방법에 대한 자세한 내용은 계획 설명서의 [Defining Your Organization's Requirements for Archiving](https://technet.microsoft.com/library/ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a.aspx)와 배포 설명서의 [Define and Configure a Front End Pool or Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 및 [Deploying Archiving](https://technet.microsoft.com/library/a89edd16-12d5-4602-ad2f-194b47d1188e.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1855f-110">For details about planning and implementing archiving support, see [Defining Your Organization's Requirements for Archiving](https://technet.microsoft.com/library/ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a.aspx) in the Planning documentation and [Define and Configure a Front End Pool or Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) and [Deploying Archiving](https://technet.microsoft.com/library/a89edd16-12d5-4602-ad2f-194b47d1188e.aspx) in the Deployment documentation.</span></span>

2. <span data-ttu-id="1855f-111">모니터링 서버.</span><span class="sxs-lookup"><span data-stu-id="1855f-111">Monitoring Server.</span></span> <span data-ttu-id="1855f-112">모니터링 지원을 구현하는 방법에 대한 자세한 내용은 계획 설명서의 [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)과 배포 설명서의 [Define and Configure a Front End Pool or Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 및 [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1855f-112">For details about implementing monitoring support, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [Define and Configure a Front End Pool or Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx) in the Deployment documentation.</span></span>

3. <span data-ttu-id="1855f-113">A/V 에지 서비스.</span><span class="sxs-lookup"><span data-stu-id="1855f-113">A/V Edge service.</span></span> <span data-ttu-id="1855f-114">A/V 에지 서비스 구현에 대한 자세한 내용은 외부 사용자 액세스 [개요를 참조하십시오.](https://technet.microsoft.com/library/97aded6c-5fa3-4225-95a6-9ad094d61654.aspx)</span><span class="sxs-lookup"><span data-stu-id="1855f-114">For details about implementing an A/V Edge service, see [Overview of External User Access](https://technet.microsoft.com/library/97aded6c-5fa3-4225-95a6-9ad094d61654.aspx).</span></span>


