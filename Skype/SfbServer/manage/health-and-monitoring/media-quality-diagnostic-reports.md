---
title: 비즈니스용 Skype 서버의 미디어 품질 진단 보고서
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: '요약: 비즈니스용 Skype 서버의 미디어 품질 진단 보고서에 대해 자세히 알아보습니다.'
ms.openlocfilehash: a00084605941af80435dd5da73efbfea89a6272f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827838"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="c715c-103">비즈니스용 Skype 서버의 미디어 품질 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="c715c-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="c715c-104">**요약:** 비즈니스용 Skype 서버의 미디어 품질 진단 보고서에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="c715c-105">미디어 품질 진단 보고서는 통화 품질에 대한 정보와 실패한 통화에 대한 진단 및 문제 해결 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c715c-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="c715c-106">In this section</span></span>

- <span data-ttu-id="c715c-107">[비즈니스용 Skype](summary.md) 서버의 미디어 품질 요약 보고서 피어 투 피어 Enterprise Voice 통화, Enterprise Voice PSTN(전화망)에 부분적으로 종사하는 통화를 포함하여 여러 끝점 유형에 대한 전체 품질 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="c715c-108">[비즈니스용 Skype](comparison.md) 서버의 미디어 품질 비교 보고서 다양한 유형의 오디오 통화(예: 무선 네트워크를 통해 걸은 통화와 유선 연결을 통해 걸은 통화)에 대한 통화 품질 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="c715c-109">[비즈니스용 Skype 서버의 서버 성능 보고서](server-performance.md) 저하, 패킷 손실 및 지터와 같은 주요 품질 메트릭의 측정값에 따라 가장 많은 문제가 발생한 서버를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="c715c-110">[비즈니스용 Skype 서버의 위치 보고서](location-report.md) 네트워크 위치 목록과 각 위치에서 발생하는 통화의 미디어 품질 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="c715c-111">이 보고서의 목적을 위해 위치는 IP 서브넷을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="c715c-112">[비즈니스용 Skype 서버의 장치 보고서](device-report.md) 전화 통화에 사용되는 장치 요약을 Enterprise Voice 장치당 평균 미디어 품질을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="c715c-113">[비즈니스용 Skype 서버의 통화 목록 보고서](call-list-report-0.md) 조직 내에서 걸거나 받은 전화 통화에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="c715c-114">[비즈니스용 Skype 서버의 통화 정보 보고서](call-detail-report.md) 조직 내에서 걸거나 받은 전화 통화에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="c715c-115">[비즈니스용 Skype](server-media-quality-trend-report.md) 서버의 서버 미디어 품질 추세 보고서 통화량, 불량 통화율, 패킷 손실, 지터 등 체감 품질 메트릭에서 최대 5대의 서버를 그래픽으로 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="c715c-116">[비즈니스용 Skype](media-quality-metrics-distribution-report.md) 서버의 미디어 품질 메트릭 배포 보고서 지터 또는 패킷 손실과 같은 품질 메트릭에 대한 배포 값을 보여 주며 그래프를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="c715c-117">[비즈니스용 Skype 서버의 위치 추세 보고서](location-trend-report.md) 네트워크 위치에 대한 통화 품질 추세 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c715c-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

