---
title: 레거시 병합
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: 외부 사용자는 웹 회의 외부 FQDN을 사용 하 여 온-프레미스 모임에 참가할 수 있습니다. 레거시 Edge 서버의 웹 회의 외부 인터페이스의 FQDN (정규화 된 도메인 이름)을 입력 합니다.
ms.openlocfilehash: b1d0211c51864b55a81b7c648d84402a44300f2a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189804"
---
# <a name="legacy-merge"></a><span data-ttu-id="cf9df-104">레거시 병합</span><span class="sxs-lookup"><span data-stu-id="cf9df-104">Legacy Merge</span></span>

<span data-ttu-id="cf9df-105">외부 사용자는 **웹 회의 외부 FQDN** 을 사용 하 여 온-프레미스 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9df-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="cf9df-106">레거시 Edge 서버의 웹 회의 외부 인터페이스의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9df-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="cf9df-107">**443** 의 **외부 웹 회의 외부 포트** 값은 회의 클라이언트에 대해 구성 된 TCP (전송 제어 프로토콜)의 기본 SIP (세션 초기화 프로토콜) 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf9df-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="cf9df-108">기본값을 사용 하지 않은 경우 **외부 웹 회의 외부 포트** 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9df-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="cf9df-109">이 Edge 서버를 페더레이션에 사용할 계획인 경우 **이 edge 풀을 페더레이션 및 공용 메신저 연결에 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9df-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="cf9df-110">여러 개의 Edge 서버가 배포 된 경우 페더레이션에 대 한 서버 중 하나만 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf9df-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="cf9df-111">이 확인란을 선택 하지 않고 나중에 페더레이션을 사용 하기로 결정 한 경우에는 토폴로지 작성기 병합 마법사를 다시 실행 하 고 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9df-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="cf9df-112">자세한 내용은 [4 단계: 병합 토폴로지](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf9df-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


