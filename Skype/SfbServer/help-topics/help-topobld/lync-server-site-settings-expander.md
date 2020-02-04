---
title: Lync 서버 사이트 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 기존 사이트의 속성을 편집 하려면 다음을 수행 합니다.
ms.openlocfilehash: edbc1df57334e8485d844cfa0ac978d0a5b0e15c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697063"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="3696b-103">Lync 서버 사이트 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="3696b-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="3696b-104">기존 사이트의 속성을 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="3696b-105">사이트 속성</span><span class="sxs-lookup"><span data-stu-id="3696b-105">Site properties</span></span>

<span data-ttu-id="3696b-106">사이트 속성에서 사이트 이름 (필수), 설명 (선택 사항), 도시 (선택 사항), 시/도 (선택 사항), 국가/지역 코드 (선택 사항)를 변경 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="3696b-107">사이트 속성에 대 한 자세한 내용은 [토폴로지에 분기 사이트 추가](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3696b-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="3696b-108">페더레이션 경로 속성</span><span class="sxs-lookup"><span data-stu-id="3696b-108">Federation Route properties</span></span>

<span data-ttu-id="3696b-109">사이트 페더레이션 경로 할당을 설정 하려면 먼저 Edge 서버 또는 Edge 서버 풀에 페더레이션이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="3696b-110">Edge 서버 또는 풀에서 페더레이션을 사용할 수 없는 경우에는 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="3696b-111">Edge 서버 또는 풀의 페더레이션 설정이 구성 된 경우 사이트 수준에서 **사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="3696b-112">그런 다음, 페더레이션 경로로 설정할 드롭다운 목록에서 모서리나 디렉터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="3696b-113">이 설정은 모든 사이트에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-113">This setting will affect all sites.</span></span> <span data-ttu-id="3696b-114">이 사이트에서 구성 하는 설정이 모든 사이트에 적합 한지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3696b-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="3696b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3696b-115">See also</span></span>

<span data-ttu-id="3696b-116">자세한 내용은 [외부 사용자 액세스의 토폴로지](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3696b-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


