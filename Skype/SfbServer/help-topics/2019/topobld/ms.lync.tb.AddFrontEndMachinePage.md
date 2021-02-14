---
title: 프론트 엔드 컴퓨터 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: 이 풀에 프런트 엔드 서버로 추가할 각 컴퓨터의 FQDN(정규화된 도메인 이름)을 지정합니다. 목록에 컴퓨터를 추가한 후 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 해당 컴퓨터를 제거할 수 있습니다. 토폴로지를 게시한 후 FQDN을 변경하려면 토폴로지 작성기에서 서버를 삭제한 다음 풀에 새 FQDN으로 새 서버를 추가해야 합니다. 토폴로지에 프런트 엔드 풀을 추가하는 데 대한 자세한 내용은 배포 설명서에서 프런트 엔드 풀 정의 및 구성을 참조하십시오.
ms.openlocfilehash: f0336e6e1561a9a5bc4de80d7058bf99c5fb6092
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811698"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="4f965-106">프론트 엔드 컴퓨터 추가</span><span class="sxs-lookup"><span data-stu-id="4f965-106">Add Front End Machine</span></span>

<span data-ttu-id="4f965-107">이 풀에 프런트 엔드 서버로 추가할 각 컴퓨터의 FQDN(정규화된 도메인 이름)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f965-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="4f965-108">목록에 컴퓨터를 추가한 후 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 해당 컴퓨터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f965-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="4f965-109">토폴로지를 게시한 후 FQDN을 변경하려면 토폴로지 작성기에서 서버를 삭제한 다음 풀에 새 FQDN으로 새 서버를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f965-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="4f965-110">토폴로지에 프런트 엔드 풀을 추가하는 [](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 데 대한 자세한 내용은 배포 설명서에서 프런트 엔드 풀 정의 및 구성을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f965-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f965-111">토폴로지 작성기에서는 풀에 최대 20대의 프런트 엔드 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f965-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="4f965-112">지원되는 최대 서버 수는 12개입니다.</span><span class="sxs-lookup"><span data-stu-id="4f965-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="4f965-113">패브릭에 정의된 상태 저장 서버는 최대 20개까지 있으며, 이 중 12대는 한 번씩 활성 상태 및 온라인 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f965-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


