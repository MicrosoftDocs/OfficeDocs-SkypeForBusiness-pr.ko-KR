---
title: 레거시 병합
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: 웹 회의 외부 FQDN은 외부 사용자가 온-프레미스 모임에 참가할 수 있도록 허용합니다. 레거시 에지 서버의 웹 회의 외부 인터페이스 FQDN(정규화된 도메인 이름)을 입력합니다.
ms.openlocfilehash: bd259179ea61e20efec2fca81bddd40b0c53f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805708"
---
# <a name="legacy-merge"></a><span data-ttu-id="6b3f6-104">레거시 병합</span><span class="sxs-lookup"><span data-stu-id="6b3f6-104">Legacy Merge</span></span>

<span data-ttu-id="6b3f6-p102">**웹 회의 외부 FQDN** 은 외부 사용자가 온-프레미스 모임에 참가할 수 있도록 허용합니다. 레거시 에지 서버의 웹 회의 외부 인터페이스 FQDN(정규화된 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3f6-p102">The **Web Conferencing external FQDN** permits external users to join on-premises meetings. Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="6b3f6-p103">**외부 웹 회의 외부 포트** 값 **443** 은 회의 클라이언트에 대해 구성된 기본 TCP(Transmission Control Protocol) SIP(Session Initiation Protocol) 포트입니다. 기본값이 사용되지 않으면 **외부 웹 회의 외부 포트** 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3f6-p103">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients. If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="6b3f6-109">이 에지 서버를 페더레이션에 사용하려면 **이 에지 풀은 페더레이션 및 공용 IM 연결에 사용됩니다** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3f6-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="6b3f6-110">에지 서버가 여러 대 배포되어 있으면 이 중 한 대만 페더레이션에 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3f6-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="6b3f6-111">이 확인란을 선택하지 않고 나중에 페더레이션을 사용하도록 설정하려는 경우 토폴로지를 게시하고 토폴로지 작성기 병합 마법사를 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3f6-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="6b3f6-112">자세한 내용은 [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b3f6-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


