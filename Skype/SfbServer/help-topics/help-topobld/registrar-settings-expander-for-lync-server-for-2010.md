---
title: 2010 용 Lync Server 용 등록자 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 복원에 대 한 설정을 편집 하 고 다음 속성을 구성 합니다.
ms.openlocfilehash: 5ed1311e73ea035b7672ba75bab337c9212e8816
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189438"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="83db2-103">2010 용 Lync Server 용 등록자 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="83db2-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="83db2-104">**복원** 에 대 한 설정을 편집 하 고 다음 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="83db2-105">목록에서 **연결 된 백업 등록자 풀** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="83db2-106">선택적으로 **음성 장애 조치 및 자동 복구 (failback** ) 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="83db2-107">**보이스 오류 검색 간격 (초)** 및 **음성 장애 복구 간격 (초)** 을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="83db2-108">기본적으로 음성 오류 감지 및 음성 장애 복구 시 240 초 동안 간격은 120 초입니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="83db2-109">장애 조치 및 장애 복구 간격에 대해 정의 하는 시간 (초)을 테스트 하 여 복원성이 예상 대로 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="83db2-110">간격을 낮음으로 설정 하는 경우 (즉, 120 초 미만) 또는 장애 조치 (failover) 및 장애 복구 (failback)가 너무 자세히 설정 되 면 실제 장애 조치 및 장애 복구가 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="83db2-111">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="83db2-112">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="83db2-113">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="83db2-113">**Help** Displays this help screen.</span></span>
  

