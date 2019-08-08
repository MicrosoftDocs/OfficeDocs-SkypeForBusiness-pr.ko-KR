---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: '요약: 중앙 사이트의 비즈니스용 Skype Server에 대 한 엔터프라이즈 음성을 배포 하는 방법을 알아봅니다.'
ms.openlocfilehash: 3e85ac96415788e8e15ba1ed11786864b6fc3124
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245776"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="8b217-103">비즈니스용 Skype 서버에서 엔터프라이즈 음성 배포</span><span class="sxs-lookup"><span data-stu-id="8b217-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="8b217-104">**요약:** 중앙 사이트의 비즈니스용 Skype 서버에 엔터프라이즈 음성을 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8b217-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="8b217-105">이 항목을 사용 하 여 중앙 사이트에서 엔터프라이즈 음성을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b217-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="8b217-106">지점 사이트에서 엔터프라이즈 음성을 배포 하려면 [분기 사이트 배포](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)로 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="8b217-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="8b217-107">이 섹션에는 각 프런트 엔드 서버 또는 스탠더드 버전 서버에서 중재 서버를 collocated 하는 배포에 대 한 절차와 함께, 독립 실행형 중재 서버 풀을 사용 하 여 배포 하기 위한 절차가 포함 되어 있습니다. 배포 마법사가 각 프런트 엔드 서버 또는 Standard Edition 서버에서 중재 서버를 찾는 토폴로지를 정의 하 고 게시 하는 경우 다음 콘텐츠를 건너뛸 수 있습니다. 프런트 엔드 서버 풀 또는 Standard Edition Server 용 파일을 설치할 때 중재 서버:</span><span class="sxs-lookup"><span data-stu-id="8b217-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="8b217-108">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="8b217-108">In this section</span></span>

- [<span data-ttu-id="8b217-109">비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건</span><span class="sxs-lookup"><span data-stu-id="8b217-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="8b217-110">비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버 배포</span><span class="sxs-lookup"><span data-stu-id="8b217-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="8b217-111">비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="8b217-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="8b217-112">비즈니스용 Skype 서버의 토폴로지 작성기에 추가 trunks 정의</span><span class="sxs-lookup"><span data-stu-id="8b217-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="8b217-113">비즈니스용 Skype 서버에서 중재 서버용 파일 설치</span><span class="sxs-lookup"><span data-stu-id="8b217-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="8b217-114">비즈니스용 Skype 서버에서 trunks 구성</span><span class="sxs-lookup"><span data-stu-id="8b217-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="8b217-115">비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션의 번역 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8b217-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="8b217-116">비즈니스용 Skype 서버에서 호출 된 ID 프레젠테이션에 대 한 번역 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8b217-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="8b217-117">비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8b217-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="8b217-118">비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8b217-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="8b217-119">비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="8b217-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="8b217-120">비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화</span><span class="sxs-lookup"><span data-stu-id="8b217-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="8b217-121">비즈니스용 Skype 서버에서 고급 엔터프라이즈 음성 기능 배포</span><span class="sxs-lookup"><span data-stu-id="8b217-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="8b217-122">비즈니스용 Skype에서 통화 관리 기능 배포</span><span class="sxs-lookup"><span data-stu-id="8b217-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="8b217-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b217-123">See also</span></span>

[<span data-ttu-id="8b217-124">비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="8b217-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

