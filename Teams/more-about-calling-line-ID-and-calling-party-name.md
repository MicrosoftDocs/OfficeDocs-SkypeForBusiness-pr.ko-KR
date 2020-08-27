---
title: 전화 회선 ID 및 발신자 이름에 대한 자세한 정보
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 새 로컬 번호 포트 주문 마법사를 사용할 때 계정을 변경할 수 있는 권한이 있는 사용자를 추가 해야 하는 이유를 알아보세요.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255401"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="b8b68-103">전화 회선 ID 및 발신자 이름에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="b8b68-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="b8b68-104">일반적으로 참조 되는 CallerID는 다음과 같은 두 가지 사용자 연결 식별 가능 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="b8b68-105">전화 번호 (일반적으로 CLID 또는 통화 라인 ID 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="b8b68-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="b8b68-106">전화 파티 이름 (일반적으로 CNAM 이라고 함)은 최대 15 자까지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="b8b68-107">전화를 걸 때 CLID (전화 번호)는 목적지의 캐리어 (종료 통신 업체 라고도 함)로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="b8b68-108">통화에 대 한 CNAM 정보는 국가에서의 연결 상태 (모든 경우)에 따라 통화와 라우팅되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="b8b68-109">이 통화와의 CNAM 배달의 안정성은 중개 및/또는 종료 통신 사업자 중 해당 통화를 처리 하는 국가와 캐리어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="b8b68-110">CLID & CNAM 전송은 종료 캐리어가 CLID & CNAM 기능을 지원 해야 하 고 두 값에 대 한 최신 레코드를 제공 하는 것과 같은 종료 통신 회사 인의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="b8b68-111">Microsoft는 원래 호출할 때 CLID 값을 안정적으로 제공 하지만,이 값은 중간 통신 회사 또는 종료 통신 회사를 통과 하면 그대로 유지 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="b8b68-112">죄송 하지만, CLID 값이 중개 또는 종료 통신 회사에 의해 변경, 생략 또는 잘린 경우, Microsoft는 공개 전화 네트워크에서 이러한 문제를 해결 하는 recourse 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="b8b68-113">CNAM의 불일치는 미국에 따라 신뢰할 수 있는 데이터베이스에서 CNAM 정보를 새로 고침 하는 중간 또는 종료 통신의 지연으로 인해 발생 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="b8b68-114">CNAM에 대 한 신뢰할 수 있는 데이터베이스가 없는 국가에서는 각 통신 회사에서 CNAM 정보를 통화에 그대로 도착 해도 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="b8b68-115">현재 Microsoft는 미국 이외의 국가에서는 원래 CNAM 정보를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b68-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8b68-116">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b8b68-116">Related topics</span></span>


