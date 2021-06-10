---
title: 연산자 커넥트
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 요구 사항 및 배포 계획과 커넥트 운영자에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694543"
---
# <a name="plan-for-operator-connect"></a><span data-ttu-id="6c647-103">연산자에 대한 커넥트</span><span class="sxs-lookup"><span data-stu-id="6c647-103">Plan for Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="6c647-104">연산자 커넥트 현재 공개 미리 보기에서만 **사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6c647-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="6c647-105">공개 미리 보기를 사용하면 예정된 기능을 테스트하고 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="6c647-106">공개 미리 보기에 포함된 기능은 완료되지 않을 수 있으며, 변경이 진행될 수 있으며, 클라우드에서 지원되지 Office 365 Government 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Cloud.</span></span>

<span data-ttu-id="6c647-107">운영자 커넥트 는 PSTN(공용 전환 전화 네트워크)에 연결 및 연결과 연결 Teams 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="6c647-107">Operator Connect is another option for providing Public Switched Telephone Network (PSTN) connectivity with Teams and Phone System.</span></span>  

<span data-ttu-id="6c647-108">이 문서에서는 이점 및 요구 사항을 설명하고 운영자 프로그램에 참여하는 커넥트 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-108">This article describes benefits and requirements, and lists the operators participating in the Operator Connect Program.</span></span>  <span data-ttu-id="6c647-109">운영자 커넥트 조직에 적합한 솔루션으로 결정한 경우 이 문서를 [읽은](operator-connect-configure.md)후 연산자 커넥트.</span><span class="sxs-lookup"><span data-stu-id="6c647-109">If you decide Operator Connect is the right solution for your organization, after reading this article, see [Configure Operator Connect](operator-connect-configure.md).</span></span>  

## <a name="benefits"></a><span data-ttu-id="6c647-110">이점</span><span class="sxs-lookup"><span data-stu-id="6c647-110">Benefits</span></span>

<span data-ttu-id="6c647-111">연산자 커넥트 경우 기존 연산자가 Microsoft Operator 커넥트 프로그램에 참여하는 경우 PSTN 호출을 사용자에 가져오기 위한 서비스를 관리할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="6c647-111">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="6c647-112">연산자 커넥트 프로그램은 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-112">The Operator Connect program provides the following benefits:</span></span>

- <span data-ttu-id="6c647-113">**기존 계약을 활용하거나 새 연산자를 찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="6c647-113">**Leverage existing contracts, or find a new operator.**</span></span> <span data-ttu-id="6c647-114">원하는 운영자 및 계약을 유지하거나, 비즈니스 요구 사항을 충족하기 위해 참여 연산자의 선택에서 새 연산자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-114">You keep your preferred operator and contracts, or choose a new one from a selection of participating operators to meet your business needs.</span></span>

- <span data-ttu-id="6c647-115">**운영자 관리 인프라입니다.**</span><span class="sxs-lookup"><span data-stu-id="6c647-115">**Operator-managed infrastructure.**</span></span> <span data-ttu-id="6c647-116">운영자는 PSTN 호출 서비스 및 SBC(세션 테두리 컨트롤러)를 관리하므로 하드웨어 구매 및 관리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-116">Your operator manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

- <span data-ttu-id="6c647-117">**더 빠르고 쉽게 배포할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6c647-117">**Faster, easier deployment.**</span></span> <span data-ttu-id="6c647-118">운영자에 빠르게 연결하고 사용자에 전화 번호를 할당할 수 있습니다. 모든 관리 센터에서 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-118">You can quickly connect to your operator and assign phone numbers to users -– all from the Teams Admin Center.</span></span>

- <span data-ttu-id="6c647-119">**향상된 지원 및 안정성.**</span><span class="sxs-lookup"><span data-stu-id="6c647-119">**Enhanced support and reliability.**</span></span> <span data-ttu-id="6c647-120">운영자는 지원 서비스를 개선하기 위해 기술 지원 및 공유 서비스 수준 계약을 제공하고, Azure에서 제공하는 직접 피어링은 향상된 안정성을 위해 일대일 네트워크 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-120">Operators provide technical support and shared service level agreements to improve support service, while direct peering powered by Azure creates a one-to-one network connection for enhanced reliability.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c647-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c647-121">Requirements</span></span>

 <span data-ttu-id="6c647-122">운영자는 커넥트 경우 조직에 적합한 솔루션일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-122">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="6c647-123">Microsoft 통화 요금제는 지리적 위치에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-123">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="6c647-124">기본 설정 연산자는 Microsoft 연산자 커넥트 참여자입니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-124">Your preferred operator is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="6c647-125">새 연산자를 찾아 통화에서 Teams.</span><span class="sxs-lookup"><span data-stu-id="6c647-125">You want to find a new operator to enable calling in Teams.</span></span>

<span data-ttu-id="6c647-126">연산자에서 전화 번호 할당을 사용하도록 설정하려면 커넥트 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-126">To enable phone number assignments with Operator Connect, make sure your users are:</span></span>

- <span data-ttu-id="6c647-127">Teams 전화 라이선스가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-127">Teams Phone licensed.</span></span> <span data-ttu-id="6c647-128">자세한 내용은 사용자에 대한 추가 [전화 시스템?](what-is-phone-system-in-office-365.md) 및 Teams 추가 기능 라이선스 할당 을 [참조하세요.](teams-add-on-licensing/assign-teams-add-on-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="6c647-128">To learn more, see [What is Phone System?](what-is-phone-system-in-office-365.md) and [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
- <span data-ttu-id="6c647-129">TeamsOnly 모드에서.</span><span class="sxs-lookup"><span data-stu-id="6c647-129">In TeamsOnly mode.</span></span> <span data-ttu-id="6c647-130">자세한 내용은 공존 및 상호 Microsoft Teams 비즈니스용 Skype 이해를 [참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6c647-130">To learn more, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

## <a name="available-operators"></a><span data-ttu-id="6c647-131">사용 가능한 연산자</span><span class="sxs-lookup"><span data-stu-id="6c647-131">Available Operators</span></span>

<span data-ttu-id="6c647-132">다음 연산자는 Microsoft Operator 커넥트 참여자입니다.</span><span class="sxs-lookup"><span data-stu-id="6c647-132">The following operators are participants in the Microsoft Operator Connect program:</span></span>

| <span data-ttu-id="6c647-133">연산자</span><span class="sxs-lookup"><span data-stu-id="6c647-133">Operator</span></span> | <span data-ttu-id="6c647-134">기능</span><span class="sxs-lookup"><span data-stu-id="6c647-134">Capability</span></span> | <span data-ttu-id="6c647-135">국가 범위</span><span class="sxs-lookup"><span data-stu-id="6c647-135">Country coverage</span></span> |
| --- | --- | --- |
| `BT`  | <span data-ttu-id="6c647-136">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-136">Calling</span></span> | <span data-ttu-id="6c647-137">벨기에, 덴마크, 핀란드, 프랑스, 독일, 아일랜드, 이탈리아, 룩셈부르크, 네덜란드, 노르웨이, 폴란드, 남아프리카, 스페인, 스웨덴, 스위스, 영국</span><span class="sxs-lookup"><span data-stu-id="6c647-137">Belgium, Denmark, Finland, France, Germany, Ireland, Italy, Luxembourg, Netherlands, Norway, Poland, South Africa, Spain, Sweden, Switzerland, United Kingdom</span></span> |
| `Intrado` | <span data-ttu-id="6c647-138">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-138">Calling</span></span> | <span data-ttu-id="6c647-139">벨기에, 캐나다, 덴마크, 프랑스, 독일, 아일랜드, 룩셈부르크, 네덜란드, 스페인, 스웨덴, 영국, 미국</span><span class="sxs-lookup"><span data-stu-id="6c647-139">Belgium, Canada, Denmark, France, Germany, Ireland, Luxembourg, Netherlands, Spain, Sweden, United Kingdom, United States</span></span>  |
| `NTT`  | <span data-ttu-id="6c647-140">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-140">Calling</span></span> | <span data-ttu-id="6c647-141">오스트리아, 벨기에, 브라질, 캐나다, 체코, 덴마크, 핀란드, 프랑스, 독일, 아일랜드, 이탈리아, 룩셈부르크, 멕시코, 네덜란드, 노르웨이, 폴란드, 포르투갈, 푸에르토리코, 루마니아, 남아프리카, 스페인, 스웨덴, 스위스, 영국, 미국</span><span class="sxs-lookup"><span data-stu-id="6c647-141">Austria, Belgium, Brazil, Canada, Czechia, Denmark, Finland,  France, Germany, Ireland, Italy, Luxembourg, Mexico, Netherlands, Norway, Poland, Portugal, Puerto Rico, Romania, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span> |
| `NuWave` | <span data-ttu-id="6c647-142">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-142">Calling</span></span> | <span data-ttu-id="6c647-143">오스트리아, 벨기에, 캐나다, 덴마크, 프랑스, 독일, 아일랜드, 이탈리아, 네덜란드, 포르투갈, 스페인, 스웨덴, 스위스, 영국, 미국</span><span class="sxs-lookup"><span data-stu-id="6c647-143">Austria, Belgium, Canada, Denmark, France, Germany, Ireland, Italy, Netherlands, Portugal, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>   |
| `Orange Business Services` | <span data-ttu-id="6c647-144">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-144">Calling</span></span> | <span data-ttu-id="6c647-145">오스트리아, 벨기에, 체코, 덴마크, 핀란드, 프랑스, 프랑스령 기아나, 독일, 과들루페, 아일랜드, 이탈리아, 룩셈부르크, 마르티니크, 마요테, 네덜란드, 노르웨이, 폴란드, 포르투갈, 레위니온, 세인트 바르테레미, 세인트 마틴, 스페인, 스발바르, 스웨덴, 스위스, 영국</span><span class="sxs-lookup"><span data-stu-id="6c647-145">Austria, Belgium, Czechia, Denmark, Finland, France, French Guiana, Germany, Guadeloupe, Ireland, Italy, Luxembourg, Martinique, Mayotte, Netherlands, Norway, Poland, Portugal, Réunion, Saint Barthélemy, Saint Martin, Spain, Svalbard, Sweden, Switzerland, United Kingdom</span></span>  |
| `Pure IP` | <span data-ttu-id="6c647-146">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-146">Calling</span></span> | <span data-ttu-id="6c647-147">오스트레일리아, 오스트리아, 벨기에, 브라질, 불가리아, 캐나다, 칠레, 콜롬비아, 크로아티아, 키프로스, 체코, 덴마크, 핀란드, 프랑스, 독일, 그리스, 홍콩 S.A.R., 아일랜드, 이탈리아, 일본, 리투아니아, 룩셈부르크, 말레이시아, 멕시코, 네덜란드, 뉴질랜드, 노르웨이, 파나마, 폴란드, 포르투갈, 푸에르토리코, 루마니아, 싱가포르, 슬로바키아, 슬로베니아, 남아프리카, 스페인, 스웨덴, 스위스, 영국, 미국</span><span class="sxs-lookup"><span data-stu-id="6c647-147">Australia, Austria, Belgium, Brazil, Bulgaria, Canada, Chile, Colombia, Croatia, Cyprus, Czechia, Denmark, Finland, France, Germany, Greece, Hong Kong S.A.R., Ireland, Italy, Japan, Lithuania, Luxembourg, Malaysia, Mexico, Netherlands, New Zealand, Norway, Panama, Poland, Portugal, Puerto Rico, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>  |
| `Rogers Business` | <span data-ttu-id="6c647-148">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-148">Calling</span></span> | <span data-ttu-id="6c647-149">캐나다</span><span class="sxs-lookup"><span data-stu-id="6c647-149">Canada</span></span>  |
| `TATA Communications` | <span data-ttu-id="6c647-150">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-150">Calling</span></span> | <span data-ttu-id="6c647-151">오스트레일리아, 오스트리아, 벨기에, 캐나다, 체코, 덴마크, 프랑스, 독일, 홍콩 S.A.R., 헝가리, 아일랜드, 이탈리아, 말레이시아, 멕시코, 네덜란드, 뉴질랜드, 폴란드, 포르투갈, 루마니아, 싱가포르, 대한민국, 스페인, 스웨덴, 스위스, 태국, 영국, 미국</span><span class="sxs-lookup"><span data-stu-id="6c647-151">Australia, Austria, Belgium, Canada, Czechia, Denmark, France, Germany, Hong Kong S.A.R., Hungary, Ireland, Italy, Malaysia, Mexico, Netherlands, New Zealand, Poland, Portugal, Romania, Singapore, South Korea, Spain, Sweden, Switzerland, Thailand, United Kingdom, United States</span></span> |
| `Telekom Deutschland` | <span data-ttu-id="6c647-152">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-152">Calling</span></span> | <span data-ttu-id="6c647-153">독일</span><span class="sxs-lookup"><span data-stu-id="6c647-153">Germany</span></span>  |
| `Telenor` | <span data-ttu-id="6c647-154">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-154">Calling</span></span> | <span data-ttu-id="6c647-155">덴마크, 핀란드, 노르웨이, 스웨덴</span><span class="sxs-lookup"><span data-stu-id="6c647-155">Denmark, Finland, Norway, Sweden</span></span>  |
| `Verizon` | <span data-ttu-id="6c647-156">통화</span><span class="sxs-lookup"><span data-stu-id="6c647-156">Calling</span></span> | <span data-ttu-id="6c647-157">미국</span><span class="sxs-lookup"><span data-stu-id="6c647-157">United States</span></span> |
