---
title: 등록자 SBA 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 탄성에 대한 설정을 편집하고 다음 속성을 구성합니다.
ms.openlocfilehash: 6424b43ea7c56760bb8d58ee35d9804c49c435dd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217219"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="09e24-103">등록자 SBA 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="09e24-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="09e24-104">**탄성**에 대한 설정을 편집하고 다음 속성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="09e24-105">목록에서 **연결 된 사용자 서비스 및 백업 등록자 풀** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="09e24-106">원하는 경우 **자동 음성 장애 조치(failover) 및 장애 복구(failback)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="09e24-p101">**음성 실패 검색 간격(초)** 및 **음성 장애 복구(failback) 간격(초)** 을 구성합니다. 기본적으로 음성 실패 검색 간격은 120초이고 음성 장애 복구(failback) 간격은 240초입니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="09e24-p102">장애 조치(failover) 및 장애 복구(failback) 간격에 대해 정의하는 시간(초)은 면밀하게 테스트하여 탄성이 예상대로 작동하는지를 확인해야 합니다. 간격을 낮게(120초 미만으로) 설정하거나 장애 조치(failover) 및 장애 복구(failback)를 너무 가깝게 설정하면 실제 장애 조치(failover) 및 장애 복구(failback)가 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="09e24-111">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="09e24-112">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="09e24-113">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="09e24-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="09e24-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09e24-114">See also</span></span>

[<span data-ttu-id="09e24-115">Enterprise Voice 복구 계획</span><span class="sxs-lookup"><span data-stu-id="09e24-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
