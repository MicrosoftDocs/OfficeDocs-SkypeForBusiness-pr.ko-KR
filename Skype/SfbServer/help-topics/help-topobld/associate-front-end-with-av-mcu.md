---
title: AV MCU와 프런트 엔드 연결
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
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
description: A/V 회의에서는 사용자 간의 실시간 오디오 및 비디오 통신이 가능합니다(사용자에게 오디오 회의를 위한 헤드셋, 비디오 회의를 위한 웹캠 등의 적절한 클라이언트 장치가 있는 경우). 배포에서 회의를 지원하고 사용자가 웹 회의 및 A/V 회의를 둘 다 사용하도록 설정하는 경우 프런트 엔드 서버와 함께 A/V 회의 서버를 배치하거나 하나 이상의 독립 실행형 A/V 회의 서버(A/V 회의 풀)를 배포할 수 있습니다. 독립 실행형 A/V 회의 서버를 배포하는 옵션을 선택하는 경우 토폴로지 작성기에서 정의해야 합니다.
ms.openlocfilehash: 247212a163535b6e8ab0124a68d95c938a6160da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818498"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="f454a-105">AV MCU와 프런트 엔드 연결</span><span class="sxs-lookup"><span data-stu-id="f454a-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="f454a-106">A/V 회의에서는 사용자 간의 실시간 오디오 및 비디오 통신이 가능합니다(사용자에게 오디오 회의를 위한 헤드셋, 비디오 회의를 위한 웹캠 등의 적절한 클라이언트 장치가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="f454a-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="f454a-107">배포에서 회의를 지원하고 사용자가 웹 회의 및 A/V 회의를 둘 다 사용하도록 설정하는 경우 프런트 엔드 서버와 함께 A/V 회의 서버를 배치하거나 하나 이상의 독립 실행형 A/V 회의 서버(A/V 회의 풀)를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f454a-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="f454a-108">독립 실행형 A/V 회의 서버를 배포하는 옵션을 선택하는 경우 토폴로지 작성기에서 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f454a-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="f454a-109">사이트의 모든 풀과 여러 중앙 사이트의 풀은 사용량이 A/V 회의 서버의 용량을 초과하지 않는 경우 동일한 A/V 회의 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f454a-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

