---
title: 비즈니스용 Skype 서버에서 진단 보고서로 전화 걸기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
description: '요약: 비즈니스용 Skype 서버에서 사용 되는 다중 사용자 통화 진단 보고서에 대해 알아봅니다.'
ms.openlocfilehash: dc27972836ec78b20276e91ce8bb35d17a95842f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818129"
---
# <a name="call-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="cf4ce-103">비즈니스용 Skype 서버에서 진단 보고서로 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="cf4ce-103">Call Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="cf4ce-104">**요약:** 비즈니스용 Skype 서버에서 사용 되는 다중 사용자 통화 진단 보고서에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-104">**Summary:** Learn about the multi-user Call Diagnostic Reports used in Skype for Business Server.</span></span>
  
<span data-ttu-id="cf4ce-105">통화 진단 보고서는 실패 한 피어 투 피어 및 회의 세션에 대 한 요약 정보 및 진단 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-105">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="cf4ce-106">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="cf4ce-106">In this section</span></span>

- <span data-ttu-id="cf4ce-107">[비즈니스용 Skype 서버의 전화 진단 요약 보고서](summary-report.md) 실패 한 피어 투 피어 세션 및 회의 세션에 대 한 전반적인 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-107">[Call Diagnostic Summary Report in Skype for Business Server](summary-report.md) Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="cf4ce-108">피어 투 피어 세션은 두 명의 참가자만 포함 하는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-108">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="cf4ce-109">회의 세션에는 세 명 이상의 참가자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-109">Conferencing sessions involve three or more participants.</span></span>
    
- <span data-ttu-id="cf4ce-110">[비즈니스용 Skype 서버의 피어 투 피어 작업 진단 보고서](peer-to-peer-activity-diagnostic-report.md) 실패 한 피어 투 피어 세션의 전체 추세 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-110">[Peer-to-Peer Activity Diagnostic Report in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="cf4ce-111">피어 투 피어 세션에는 참가자가 두 개만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-111">A peer-to-peer session involves just two participants.</span></span>
    
- <span data-ttu-id="cf4ce-112">[비즈니스용 Skype 서버의 컨퍼런스 진단 보고서](conference-diagnostic-report.md) 각 회의의 모달에 대 한 실패 한 회의 세션 및 추세 보기의 전체 추세 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-112">[Conference Diagnostic Report in Skype for Business Server](conference-diagnostic-report.md) Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="cf4ce-113">회의 세션에는 참가자가 세 명 이상 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-113">Conferencing sessions involve at least three participants.</span></span>
    
- <span data-ttu-id="cf4ce-114">[비즈니스용 Skype 서버의 상위 오류 보고서](top-failures-report.md) 가장 자주 발생 하는 오류의 목록과 시간에 따른 추세를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-114">[Top Failures Report in Skype for Business Server](top-failures-report.md) Provides a list of the most frequent failures and their trends over time.</span></span>
    
- <span data-ttu-id="cf4ce-115">[비즈니스용 Skype 서버의 실패 한 배포 보고서](failure-distribution-report.md) 실패 한 세션에 대 한 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-115">[Failure Distribution Report in Skype for Business Server](failure-distribution-report.md) Provides an analysis of failed sessions.</span></span>
    
- <span data-ttu-id="cf4ce-116">[비즈니스용 Skype 서버의 오류 목록 보고서](failure-list-report.md) 장애가 있는 회의에 참여 한 개별 참가자에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-116">[Failure List Report in Skype for Business Server](failure-list-report.md) Provides detailed information about the individual participants involved in a failed conference.</span></span>
    
- <span data-ttu-id="cf4ce-117">[비즈니스용 Skype 서버의 진단 보고서](diagnostic-report.md) 실패 한 세션에 대 한 진단 및 문제 해결 정보 (SIP 응답 코드, 진단 헤더 및 Id 포함)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-117">[Diagnostic Report in Skype for Business Server](diagnostic-report.md) Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>
    

