---
title: 외부 응용 프로그램 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 이미 정의 된 신뢰할 수 있는 응용 프로그램 서버의 속성을 편집 하려면 다음 지침을 따릅니다.
ms.openlocfilehash: 56e8fb02039fec31da3303c1d357f176ddcb8d51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189972"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="813c7-103">외부 응용 프로그램 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="813c7-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="813c7-104">이미 정의 된 신뢰할 수 있는 응용 프로그램 서버의 속성을 편집 하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="813c7-105">다음과 같은 두 가지 섹션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="813c7-106">일반 설정</span><span class="sxs-lookup"><span data-stu-id="813c7-106">General settings</span></span>
> 
> <span data-ttu-id="813c7-107">다음 홉 설정</span><span class="sxs-lookup"><span data-stu-id="813c7-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="813c7-108">일반 설정</span><span class="sxs-lookup"><span data-stu-id="813c7-108">General Settings</span></span>

<span data-ttu-id="813c7-109">신뢰 된 응용 프로그램 서버 풀의 현재 FQDN (정규화 된 도메인 이름)을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="813c7-110">풀 FQDN의 이름을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="813c7-111">새 항목에 대해 DNS (Domain Name System) 호스트 (A) 레코드가 있어야 클라이언트나 서버가 새 풀 이름에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="813c7-112">구성 데이터를이 풀로 복제 해야 하는 경우 **이 풀로 구성 데이터 복제 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="813c7-113">구성 데이터를 복제 하지 않으려면 확인 표시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="813c7-114">다음 홉 설정</span><span class="sxs-lookup"><span data-stu-id="813c7-114">Next Hop Settings</span></span>

<span data-ttu-id="813c7-115">드롭다운 목록에서 정의 된 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 선택 하 여 신뢰할 수 있는 응용 프로그램 서버 풀의 다음 홉 서버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="813c7-116">디렉터 또는 디렉터 풀은 다음 홉에 대 한 올바른 선택이 아니므로 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="813c7-117">**확인** 을 클릭 하 여 변경 내용을 적용 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="813c7-118">변경 내용을 취소하고 속성 페이지를 끝내려면 **취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="813c7-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

