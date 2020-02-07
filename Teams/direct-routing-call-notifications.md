---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 다이렉트 라우팅 통화 알림
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 3d53245d241435e869dbdbeb15dcb1c81e18ff96
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837598"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="093e1-103">통화 알림 관리</span><span class="sxs-lookup"><span data-stu-id="093e1-103">Manage call notifications</span></span>

<span data-ttu-id="093e1-104">이 문서에서는 사용자에 대 한 통화 알림을 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="093e1-105">통화 끝점을 팀과 타사의 PBX (개인 분기 교환) 또는 SBC (세션 경계 컨트롤러) 모두로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="093e1-106">이 방법은 사용자의 휴대폰 및 일반 전화기로 전화를 걸 때와 같이 동시에 통화를 보내는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="093e1-107">다음 다이어그램에서 사용자 Irena는 두 개의 끝점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="093e1-108">팀 끝점</span><span class="sxs-lookup"><span data-stu-id="093e1-108">A Teams endpoint</span></span>
- <span data-ttu-id="093e1-109">타사 SBC에 연결 된 SIP 전화</span><span class="sxs-lookup"><span data-stu-id="093e1-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="093e1-110">통화가 도착 하면 SBC는 전화 시스템 다이렉트 라우팅과 타사 SBC 간의 통화를 포크 합니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![분기 팀 끝점을 보여 주는 다이어그램](media/direct-routing-call-notification-1.png)

<span data-ttu-id="093e1-112">타사 SBC의 포크 2에서 통화를 허용 하는 경우 팀에서 "부재 중 통화" 알림을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="093e1-113">다음과 같이 포크 1에 취소를 보내도록 SBC를 구성 하 여 "부재 중 전화" 알림을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="093e1-114">이유: SIP 원인 = 200; 텍스트 "통화가 다른 곳에 완료 됨"</span><span class="sxs-lookup"><span data-stu-id="093e1-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="093e1-115">통화는 전화를 걸어 Microsoft 전화 시스템의 통화 정보 레코드에 등록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="093e1-116">통화는 최종 SIP 코드 "487", 최종 Microsoft 하위 코드 "540200" 및 최종 SIP 코드 구 "통화를 다른 곳에서 완료 됨"으로 "시도" 하 여 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>   <span data-ttu-id="093e1-117">(통화 정보 레코드를 보려면 팀 관리 포털, 분석 및 보고서, 사용 현황 보고서, PSTN 사용을 선택 하세요.)</span><span class="sxs-lookup"><span data-stu-id="093e1-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="093e1-118">아래 다이어그램은 포크 1에 대 한 SIP 사다리와 통화 흐름에 대 한 설명과 취소 메시지의 예상 되는 이유를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="093e1-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![분기 팀 끝점을 보여 주는 다이어그램](media/direct-routing-call-notification-2.png)
