---
title: 프런트 엔드와 AV MCU 연결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
description: A/V 회의는 사용자 간에 실시간 오디오 및 비디오 통신을 가능 하 게 합니다 (즉, 오디오 회의를 위한 헤드셋과 같은 적절 한 클라이언트 장치를 보유 하 고 영상 컨퍼런스 용 웹캠). 배포에서 회의를 지원 하 고 웹 회의와 A/V 회의를 모두 사용 하는 경우 프런트 엔드 서버를 사용 하 여 A/V 회의 서버를 collocate 하거나 하나 이상의 독립 실행형 A/V 회의 서버 (A/V 회의 풀)를 배포할 수 있습니다. 독립 실행형 A/V 회의 서버를 배포 하는 옵션을 선택 하는 경우 토폴로지 작성기에서 정의 해야 합니다.
ms.openlocfilehash: 49d76b6b14bc2a61b771341f24832b3b10e59919
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697773"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="d252a-105">프런트 엔드와 AV MCU 연결</span><span class="sxs-lookup"><span data-stu-id="d252a-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="d252a-106">A/V 회의는 사용자 간에 실시간 오디오 및 비디오 통신을 가능 하 게 합니다 (즉, 오디오 회의를 위한 헤드셋과 같은 적절 한 클라이언트 장치를 보유 하 고 영상 컨퍼런스 용 웹캠).</span><span class="sxs-lookup"><span data-stu-id="d252a-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="d252a-107">배포에서 회의를 지원 하 고 웹 회의와 A/V 회의를 모두 사용 하는 경우 프런트 엔드 서버를 사용 하 여 A/V 회의 서버를 collocate 하거나 하나 이상의 독립 실행형 A/V 회의 서버 (A/V 회의 풀)를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d252a-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="d252a-108">독립 실행형 A/V 회의 서버를 배포 하는 옵션을 선택 하는 경우 토폴로지 작성기에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d252a-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="d252a-109">사용이 A/V 회의 서버의 용량을 초과 하지 않는 경우 사이트의 모든 풀 및 여러 중앙 사이트의 풀은 동일한 A/V 회의 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d252a-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

