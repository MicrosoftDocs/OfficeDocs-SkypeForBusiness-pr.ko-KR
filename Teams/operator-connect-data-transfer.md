---
title: 통신사와 운영자용 Microsoft 간에 데이터 커넥트
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: alaina, creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 통신사와 Microsoft 간에 데이터 또는 정보의 전송과 관련된 특정 개인 정보, 특히 운영자 커넥트.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78f602fcacf6ee2f9a29393aa9a4d6b860251e2d
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694570"
---
# <a name="data-transfers-between-carriers-and-microsoft-for-operator-connect"></a><span data-ttu-id="c2f47-103">통신사와 운영자용 Microsoft 간에 데이터 커넥트</span><span class="sxs-lookup"><span data-stu-id="c2f47-103">Data transfers between carriers and Microsoft for Operator Connect</span></span>

## <a name="provisioned-and-assigned-numbers"></a><span data-ttu-id="c2f47-104">프로비전된 번호 및 할당된 번호</span><span class="sxs-lookup"><span data-stu-id="c2f47-104">Provisioned and Assigned Numbers</span></span>

<span data-ttu-id="c2f47-105">운영자 커넥트 프로그램의 적절한 작동을 보장하기 위해 Microsoft는 해당 전화 번호의 SIP URI(세션 시작 프로토콜 균일한 리소스 식별자)뿐만 아니라 통신업체의 전화 번호가 Teams 관리 센터 내에 할당된 API를 통해 각 참여 통신사에 알릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2f47-105">To ensure the proper functioning of the Operator Connect program, Microsoft will inform each participating carrier, through an API, which of the carrier’s phone numbers have been assigned within the Teams admin center, as well as the SIP URI (Session Initiation Protocol Uniform Resource Identifiers) of that phone number.</span></span>

## <a name="call-detail-records-and-quality-data"></a><span data-ttu-id="c2f47-106">통화 세부 정보 레코드 및 품질 데이터</span><span class="sxs-lookup"><span data-stu-id="c2f47-106">Call Detail Records and Quality Data</span></span>

<span data-ttu-id="c2f47-107">Microsoft는 API를 통해 참여하는 각 통신사에 통화 세부 정보 레코드 및 품질 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f47-107">Microsoft will provide call detail records and quality data to each participating carrier through an API.</span></span> <span data-ttu-id="c2f47-108">Microsoft와 통신사가 문제 해결을 수행하고 서비스의 적절한 작동을 보장하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f47-108">This is necessary for Microsoft and the carrier to perform troubleshooting and ensure the proper functioning of the service.</span></span>

## <a name="call-duration-data"></a><span data-ttu-id="c2f47-109">통화 기간 데이터</span><span class="sxs-lookup"><span data-stu-id="c2f47-109">Call Duration Data</span></span>

<span data-ttu-id="c2f47-110">각 통신사는 API를 통해 Microsoft에 서비스를 사용하여 고객이 호출한 기간을 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2f47-110">Each carrier will provide to Microsoft, through an API, the duration of calls placed by their customers using Microsoft Teams.</span></span> <span data-ttu-id="c2f47-111">Microsoft는 이러한 레코드를 사용하여 고객에게 사용 현황 정보를 제공하고 레코드가 통신사와 일치하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f47-111">Microsoft will use these records to provide customers with usage information and to ensure our records are consistent with that of the carrier.</span></span> <span data-ttu-id="c2f47-112">Microsoft는 해당 법률 및 규정 및 Microsoft 개인 정보 취급 방침을 준수하여 이러한 레코드를 저장하고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f47-112">Microsoft will store and process these records in compliance with applicable laws and regulations, as well as the Microsoft Privacy Statement.</span></span>

<span data-ttu-id="c2f47-113">자세한 내용은 경력 [코치를 구매,](career-coach.md) 구성 및 사용하도록 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c2f47-113">For more information: [Purchase, configure, and enable Career Coach for Microsoft Teams](career-coach.md)</span></span>
