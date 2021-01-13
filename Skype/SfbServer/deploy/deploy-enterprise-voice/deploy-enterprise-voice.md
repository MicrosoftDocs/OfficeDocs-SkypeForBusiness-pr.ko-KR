---
title: 비즈니스용 Skype Enterprise Voice 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: '요약: 중앙 사이트에서 비즈니스용 Skype Enterprise Voice 서버를 배포하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 246c1e5c03401b885b297ada08677fb40faad60d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812498"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="8188f-103">비즈니스용 Skype Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="8188f-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="8188f-104">**요약:** 중앙 사이트에서 비즈니스용 Skype Enterprise Voice 배포하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="8188f-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="8188f-105">이 항목을 사용하여 중앙 Enterprise Voice 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8188f-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="8188f-106">분기 사이트에 Enterprise Voice 배포하기 위해 분기 사이트 [배포로 건너뜁니 다.](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)</span><span class="sxs-lookup"><span data-stu-id="8188f-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="8188f-107">이 섹션에는 중재 서버가 권장되는 각 프런트 엔드 서버 또는 Standard Edition 서버에 배치되는 배포 절차와 독립 실행형 중재 서버 풀이 있는 배포에 대한 절차가 포함되어 있습니다. 배포 마법사가 프런트 엔드 서버 풀 또는 Standard Edition Server용 파일을 설치할 때 중재 서버용 파일이 이미 자동으로 설치되어 있기 때문에 토폴로지 작성기에서 중재 서버를 각 프런트 엔드 서버 또는 Standard Edition 서버에 배치하는 토폴로지 정의 및 게시를 수행한 경우 다음 콘텐츠를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8188f-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="8188f-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8188f-108">In this section</span></span>

- [<span data-ttu-id="8188f-109">비즈니스용 Skype 서버의 보안 및 Enterprise Voice 구성 선행 요구</span><span class="sxs-lookup"><span data-stu-id="8188f-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="8188f-110">비즈니스용 Skype 서버에서 토폴로지 작성기에서 중재 서버 배포</span><span class="sxs-lookup"><span data-stu-id="8188f-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="8188f-111">비즈니스용 Skype 서버에서 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="8188f-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="8188f-112">비즈니스용 Skype 서버에서 토폴로지 작성기에서 추가 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="8188f-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="8188f-113">비즈니스용 Skype 서버에 중재 서버용 파일 설치</span><span class="sxs-lookup"><span data-stu-id="8188f-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="8188f-114">비즈니스용 Skype 서버에서 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="8188f-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="8188f-115">비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8188f-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="8188f-116">비즈니스용 Skype 서버에서 호출된 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8188f-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="8188f-117">비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8188f-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="8188f-118">비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8188f-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="8188f-119">비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="8188f-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="8188f-120">사용자가 비즈니스용 Skype Enterprise Voice 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8188f-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="8188f-121">비즈니스용 Skype Enterprise Voice 고급 관리 기능 배포</span><span class="sxs-lookup"><span data-stu-id="8188f-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="8188f-122">비즈니스용 Skype에서 통화 관리 기능 배포</span><span class="sxs-lookup"><span data-stu-id="8188f-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="8188f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8188f-123">See also</span></span>

[<span data-ttu-id="8188f-124">비즈니스용 Skype Enterprise Voice 계획</span><span class="sxs-lookup"><span data-stu-id="8188f-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

