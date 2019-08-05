---
title: 비즈니스용 Skype 서버의 영구 채팅 서버 준수 테이블 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 영구 채팅 준수 데이터베이스 스키마는 다음 테이블로 구성 됩니다.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196662"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="e6caa-103">비즈니스용 Skype 서버의 영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="e6caa-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="e6caa-104">영구 채팅 준수 데이터베이스 스키마는 다음 테이블로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="e6caa-105">영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="e6caa-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="e6caa-106">**테이블로**</span><span class="sxs-lookup"><span data-stu-id="e6caa-106">**Table**</span></span>|<span data-ttu-id="e6caa-107">**설명**</span><span class="sxs-lookup"><span data-stu-id="e6caa-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e6caa-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="e6caa-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="e6caa-109">구성 된 어댑터에서 아직 처리 하지 않은 준수 이벤트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="e6caa-110">이 표에는 채팅 메시지 및 파일 다운로드와 같은 지속적인 채팅 관련 이벤트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="e6caa-111">(참가자 이벤트는 tblComplianceParticipant 테이블에서 추적 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="e6caa-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="e6caa-112">(이 테이블의 이벤트를 처리 하는 서버는 tblComplianceFanout 테이블에 나열 되어 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="e6caa-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="e6caa-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="e6caa-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="e6caa-114">규정 준수 이벤트를 처리 한 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="e6caa-115">이 표는 tblComplianceData 테이블과 밀접 하 게 결합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="e6caa-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="e6caa-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="e6caa-117">채팅 서비스 및 서버 별로 현재 참가자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="e6caa-118">영구 채팅 서비스에서 받은 참가 및 파트 규정 준수 이벤트에 따라 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="e6caa-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="e6caa-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="e6caa-120">풀 전체의 준수 상태 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6caa-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

