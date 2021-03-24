---
title: Lync Server 사이트 설정 확장기
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
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 기존 사이트의 속성을 편집하려면 다음을 수행합니다.
ms.openlocfilehash: aedb248bf229af754d2ef8eb9c5e3837c69c808d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104454"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="1e03a-103">Lync Server 사이트 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="1e03a-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="1e03a-104">기존 사이트의 속성을 편집하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e03a-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="1e03a-105">사이트 속성</span><span class="sxs-lookup"><span data-stu-id="1e03a-105">Site properties</span></span>

<span data-ttu-id="1e03a-106">사이트 속성에서 사이트 이름(필수), 설명(선택 사항), 구/군/시(선택 사항), 시/도(선택 사항) 및 국가/지역 코드(선택 사항)를 변경 또는 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e03a-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="1e03a-107">사이트 속성에 대한 자세한 내용은 [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e03a-107">For details about site properties, see [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="1e03a-108">페더레이션 경로 속성</span><span class="sxs-lookup"><span data-stu-id="1e03a-108">Federation Route properties</span></span>

<span data-ttu-id="1e03a-p101">사이트 페더레이션 경로 할당을 설정하려면 먼저 에지 서버 또는 에지 서버 풀에서 페더레이션을 사용하도록 설정해야 합니다. 에지 서버 또는 풀에서 페더레이션을 사용하도록 설정하지 않은 경우 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e03a-p101">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool. If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="1e03a-p102">에지 서버 또는 풀에서 페더레이션 설정을 구성한 경우 사이트 수준에서 **사용** 을 선택합니다. 그런 다음 드롭다운 목록에서 페더레이션 경로로 설정할 에지 또는 디렉터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e03a-p102">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level. Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="1e03a-p103">이 설정은 모든 사이트에 영향을 미칩니다. 이 사이트에서 구성하는 설정이 모든 사이트에 대해 적합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e03a-p103">This setting will affect all sites. Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e03a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e03a-115">See also</span></span>

<span data-ttu-id="1e03a-116">자세한 내용은 [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e03a-116">For details, see [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span></span>