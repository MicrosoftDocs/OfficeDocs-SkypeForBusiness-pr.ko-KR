---
title: 직접 라우팅 세션 테두리 컨트롤러 연결을 테스트하는 PowerShell 스크립트
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트 샘플을 사용하여 Microsoft Teams에서 직접 라우팅 세션 테두리 컨트롤러 연결을 테스트합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834278"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="c4beb-103">직접 라우팅 세션 테두리 컨트롤러 연결을 테스트하는 PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="c4beb-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="c4beb-104">SIP 테스터 클라이언트는 Microsoft Teams에서 직접 라우팅 세션 테두리 컨트롤러(SBC) 연결을 테스트하는 데 사용할 수 있는 샘플 PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="c4beb-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="c4beb-105">이 스크립트는 직접 라우팅을 사용하여 고객 쌍의 SIP(세션 시작 프로토콜) 트렁크의 기본 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c4beb-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="c4beb-106">스크립트는 테스트 러너에 SIP 테스트를 제출하고 결과를 기다렸다가 사람이 읽을 수 있는 형식으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4beb-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="c4beb-107">이 스크립트를 사용하여 다음 시나리오를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4beb-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="c4beb-108">아웃바운드 및 인바운드 호출</span><span class="sxs-lookup"><span data-stu-id="c4beb-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="c4beb-109">동시 링</span><span class="sxs-lookup"><span data-stu-id="c4beb-109">Simultaneous ring</span></span>
- <span data-ttu-id="c4beb-110">미디어 에스컬레이터</span><span class="sxs-lookup"><span data-stu-id="c4beb-110">Media escalation</span></span>
- <span data-ttu-id="c4beb-111">컨설팅 전송</span><span class="sxs-lookup"><span data-stu-id="c4beb-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="c4beb-112">스크립트 및 설명서 다운로드</span><span class="sxs-lookup"><span data-stu-id="c4beb-112">Download the script and documentation</span></span>

<span data-ttu-id="c4beb-113">[SIP 테스터 클라이언트 스크립트 및 설명서를 다운로드합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c4beb-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c4beb-114">SIP 테스터 클라이언트 스크립트는 adal.ps 버전 3.19.8.1만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4beb-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="c4beb-115">오류가 반환되는 오류는 이후 버전의 adal.ps 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4beb-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
