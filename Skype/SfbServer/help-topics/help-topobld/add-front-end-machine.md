---
title: 프론트 엔드 컴퓨터 추가
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
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 이 풀에 프런트 엔드 서버로 추가할 각 컴퓨터의 FQDN(정규화된 도메인 이름)을 지정합니다. 목록에 컴퓨터를 추가한 후 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 해당 컴퓨터를 제거할 수 있습니다. 토폴로지를 게시한 후 FQDN을 변경하려면 토폴로지 작성기에서 서버를 삭제한 다음 풀에 새 FQDN으로 새 서버를 추가해야 합니다. 토폴로지에 프런트 엔드 풀을 추가 하는 방법에 대 한 자세한 내용은 배포 설명서에서 Define and Configure a Front End Pool을 참조 하십시오.
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218319"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="7dd23-106">프론트 엔드 컴퓨터 추가</span><span class="sxs-lookup"><span data-stu-id="7dd23-106">Add Front End Machine</span></span>

<span data-ttu-id="7dd23-107">이 풀에 프런트 엔드 서버로 추가할 각 컴퓨터의 FQDN(정규화된 도메인 이름)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dd23-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="7dd23-108">목록에 컴퓨터를 추가한 후 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 해당 컴퓨터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dd23-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="7dd23-109">토폴로지를 게시한 후 FQDN을 변경하려면 토폴로지 작성기에서 서버를 삭제한 다음 풀에 새 FQDN으로 새 서버를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dd23-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="7dd23-110">토폴로지에 프런트 엔드 풀을 추가 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Define And Configure a Front End pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7dd23-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dd23-111">토폴로지 작성기는 풀에 프런트 엔드 서버를 최대 20 개까지 포함할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7dd23-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="7dd23-112">지원 되는 최대 서버 수는 12입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd23-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="7dd23-113">패브릭에서 최대 20 개의 statefull 서버를 정의할 수 있으며, 여기서 12 개는 언제 든 지 활성 및 온라인 상태가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dd23-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


